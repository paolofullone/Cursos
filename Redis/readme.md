## Why use Redis

Porque é rápido!

O Redis tem uma estrutura muito mais simples que um banco de dados propositalmente para ser mais rápido:

<img src='./Readme/redis_structure.png'>

Motivos pelos quais o Redis é rápido:

<img src='./Readme/redis_fast.png'>

Criamos uma conta gratuita no redis.com usando a AWS como parceiro, no vídeo foi direto na aws mas quando criei tinha GCP e Azure também.

Usamos o site rbook.cloud que o professor criou para testar o redis.

Além dele temos outras opções:

<img src='./Readme/redis_setup.png'>

## Redis Notebook

https://rbook.cloud/sheets/7fc7830190a4a869

Conectei com a minha connection string:

redis://default:\*\*\*\*@redis-19423.c74.us-east-1-4.ec2.cloud.redislabs.com:19423

## Executando local:

Running RBook Locally
You can run RBook locally on your computer if you wish. This is 100% optional.

The upside to this is that your notebooks will be saved on your computer, which means backing them up is a lot easier.

To run RBook locally, you must have NodeJS installed. If you don't already have it, get an installer here: https://nodejs.org/en/download/

Then, at your terminal run npx rbook and navigate to http://localhost:3050

Any notebook you create will be saved into the same folder that you ran npx rbook in.

Again, this is 100% optional, you can complete the entire course using https://rbook.cloud

Não testei

## Comandos para salvar e recuperar dados

```bash
SET message "Hi There" # => "Ok"
GET message # => "Hi There"

```

Set e Get são usados para salvar e recuperar strings ou numeros.

Comandos Redis:

redis.io/commands

No comando GET, ele pega o valor anterior do que foi efetuado no SET:

<img src='./Readme/set_get.png'>

Primeiro retorna um red, depois na outra linha, sem setar de novo, já retorna o green.

O set com o xx só funciona se o valor já existir, se não existir ele retorna nullo:

<img src='./Readme/set_xx.png'>

Já o NX só funciona se o valor não existir, se existir ele retorna nullo:

<img src='./Readme/set_nx.png'>

## Expiration options

Apagando após 2 segundos.

```bash
SET color red EX 2 # => "Ok"
GET color # => "red"

# 2 segundos depois
GET color # => (null)
```

PX definimos em milisegundos, EX em segundos.
EXAT e PXAT definimos a data e hora que queremos que expire.
KEEPTTL keep any expiration that has already been applied to this key.

## Setting Multiple Keys

```bash
SETEX color 5 red # => "Ok" // 5 segundos depois apaga
SETNX color red # => (null) // seta color para red somente se color ainda não existir.
MSET color red shape square # => "Ok" // seta color para red e shape para square
```

## Geting Multiple Keys

```bash
SET color red shape square # => "Ok"
MGET color shape # => ["red", "square"]
```

## GetRange, SetRange and Strlen

```bash
DEL color # => (integer) 1
GET color # => (null)

SET numbers 123456789 # => "Ok"
GETRANGE numbers 0 3 # => "1234"

SETRANGE numbers 2 "HELLO" # => (integer) 9 // subsitui do 3 ao 7 por HELLO
GET numbers # => "12HELLO789"
```

## Example of a Redis Use Case

Mostrou um caso de uma fábrica de móveis por exemplo que tem um banco de dados com o index, nome dos produtos, cor, material:

| Index | Name  | Color | Material |
| ----- | ----- | ----- | -------- |
| 1     | Chair | Red   | Wood     |
| 2     | Table | Blue  | Plastic  |
| 3     | Bed   | Green | Metal    |

Porém imaginemos que são milhares de itens que mudam relativamente pouco, temos uns 100 materiais, 10 cores e 10 produtos, podemos realizar um encoding dos dados:

| Index | Name | Color | Material |
| ----- | ---- | ----- | -------- |
| 1     | c    | a     | f        |
| 2     | d    | b     | g        |
| 3     | e    | c     | h        |

Agora o Redis vai consultar menos dados, e vai ser mais rápido.

## Dealing with Numbers

temos os mesmos métodos de strings, SET, GET, MGET, MSET, DEL.

E alguns que só funcionam com números. DECR, INCR, INCRBY, DECRBY, INCRBYFLOAT.

Se tentar aplicar os comandos numéricos com strings ele vai dar erro.

Ao salvar um número no redis:

```bash
SET age 30 # => "Ok"
GET age # => "30"
```

o Redis vai salvar os números internamente como strings, porém ele vai entender que é um número e vai permitir que façamos operações matemáticas com eles.

Vamos ver alguns exemplos:

```bash
INCR age # => (integer) 31
DECR age # => (integer) 30
INCRBY age 10 # => (integer) 40
DECRBY age 5 # => (integer) 35
INCRBYFLOAT age 5.5 # => "40.5"
INCRBYFLOAT age -5.5 # => "35"
```

Para reduzir um número decimal, temos que usar o INCRBYFLOAT com um número negativo.

## Outro exemplo de caso de uso

Supondo que um blog tenha a opção de curtir os posts e tem muitos acessos, escrevemos uma função em uma api que recebe o id do post e incrementa o número de curtidas e atualiza no Redis.

Desta forma podemos ter um problema de concorrencia caso 2 ou mais votos fossem enviados no mesmo milisegundo.

Temos 3 possíveis soluções:

- Redis transaction com 'WATCH';
- Lock
- INCR

Neste momento vamos usar o INCR (depois veremos as outras)

No REDIS as operaçõe são todas processadas de forma SÍNCRONA. Então se 2 ou mais operações forem enviadas ao mesmo tempo, o Redis vai processar uma por vez.

No cenário anterior faríamos uma atualização e o redis retornaria uma response 'OK'. com o INCR, o redis responde o número de curtidas atualizado. se tivesse 1000 curtidas e recebesse 2 no mesmo instante, ele retornaria 1001 pra primeira instância da api e 1002 pra segunda.

## E-commerce app setup

Baixamos um repo com um front pronto, instalamos o node e configuramos as variáveis de ambiente com os dados da página do redis, host, porta e senha.

para executar:

```bash
npm install
npm run dev
```

Vai abrir um front na localhost:3000

## Instalando Redis

Installing on Windows
Below are instructions to run Redis locally on Windows.

You do not need to install Redis locally. You can complete the entire course using the Redis instance we already created on Redis Labs. These instructions are only here incase you want to run a copy on your own machine.

First, a few notes:

There are two different versions of Redis. They are called Redis and Redis Stack

Redis contains the core Redis database

Redis Stack contains the core Redis database and some additional modules that extend the functionality of Redis.

When we created an instance on Redis Labs, we got a copy of Redis Stack - it has these extra modules already installed.

Later sections in this course will require you to run Redis Stack, because we eventually use these extra modules

Installation Guide for Windows

These are the same install directions listed at https://redis.io/docs/stack/get-started/install/docker/

Install Docker Desktop for Windows from this page - https://docs.docker.com/desktop/windows/install/

At your terminal, run docker run -d --name redis-stack-server -p 6379:6379 redis/redis-stack-server:latest

To connect to your local Redis server and execute commands, run docker exec -it redis-stack-server redis-cli

If you want to connect the RBay e-commerce app to your local copy of Redis, update the .env file in the root project directory to the following:

REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_PW=

If you want to connect RBook to your local copy of Redis, you will need to run RBook locally.

To run RBook locally, run npx rbook at your terminal.

Navigate to localhost:3050

Open the connection settings window

Enter a host of 'localhost'

Enter a port of 6379

Leave the password blank

When running RBook locally, any notebooks you create will be added to the folder you ran npx rbook in.

## Hashes

Hash é uma collection de key value pairs.

```bash
HSET company name "Concrete Co" age 1915 industry materials # => (integer) 3
# quando adiciona mais um key value pair
HSET company name "Concrete Co" age 1915 industry materials revenue 5.3 # => (integer) 1

HGET company name # => "Concrete Co"
HGET company age # => "1915"

# volta um json na interface, mas se clicar no botão de "paint" volta uma raw response que é um array de strings.
HGETALL company # => 1) "name" 2) "Concrete Co" 3) "age" 4) "1915" 5) "industry" 6) "materials" 7) "revenue" 8) "5.3"

```

HExists

```bash
HSET company name "Concrete Co" age 1915 industry materials # => (integer) 3
HEXISTS company name # => (integer) 1
HEXISTS company address # => (integer) 0
```

Só retorna se o campo existe, name poderia ser uma string vazia, número, booleano que continuaria retornando 1.

DEL

```bash
HSET company name "Concrete Co" age 1915 industry materials # => (integer) 3
DEL company # => (integer) 1
HGETALL company # => (empty list or set)
```

HDEL deleta um campo específico

```bash
HSET company name "Concrete Co" age 1915 industry materials # => (integer) 3
HDEL company name # => (integer) 1
HGETALL company # => 1) "age" 2) "1915" 3) "industry" 4) "materials"
```

## Numbers with Hashes

```bash
HSET company name "Concrete Co" age 1915 industry materials # => (integer) 3
HINCRBY company age 10 # => (integer) 1925
HINCRBY company age -10 # => (integer) 1915
HINCRBYFLOAT company age 10.5 # => "1925.5"
HINCRBYFLOAT company age -10.5 # => "1915"
```

Se a key não existir ela é criada:

```bash
HSET company name "Concrete Co" age 1915 industry materials # => (integer) 3
HINCRBYFLOAT company revenue 10.5 # => "10.5"
HGET company revenue # => "10.5"
```

HSTRLEN

```bash
HSET company name "Concrete Co" age 1915 industry materials # => (integer) 3
HSTRLEN company name # => (integer) 11
```

HKEYS volta um array

```bash
HSET company name "Concrete Co" age 1915 industry materials # => (integer) 3
HKEYS company # => 1) "name" 2) "age" 3) "industry"
```

HVALS volta um array

```bash
HSET company name "Concrete Co" age 1915 industry materials # => (integer) 3
HVALS company # => 1) "Concrete Co" 2) "1915" 3) "materials"
```

## Sandbox

Tem um arquivo sandbox no projeto em sandbox/index.ts:

```javascript
import 'dotenv/config';
import { client } from '../src/services/redis';

const run = async () => {
  console.log('Running sandbox');
  await client.DEL('car');
  await client.hSet('car', {
    color: 'red',
    year: 1950,
    engine: { cylinders: 4 },
    owner: null,
    service: undefined,
  });
  const car = await client.hGetAll('car');
  console.log(car);
};
run();

// npm run sandbox
```

No começo estava dando um erro pois a chave car já existia, por isso criamos o .DEL('car') antes.

Esse código retorna um erro que não é possível converter null to string no campo owner.

Quando executar o tostring no engine:

```javascript
{ cylinders: 8}.toString() // "[object Object]"
```

Vai retornar um [object Object]

E quando tentar executar null.ToString() vai dar erro.

Esse problema é exclusivo do Node Redis. Para resolver vamos criar um || '' no toString:

```javascript
    owner: null || '',
    service: undefined || '',
```

Se tentarmos acessar uma key que não existe no redis, por exemplo:

```javascript
HGETALL cars#553 # => {}
```

O Redis devolve um objeto vazio caso procure por algo que não existe, no código não podemos esperar um null.

Esse código por ex. nunca vai entrar no if de car not found:

```javascript
import 'dotenv/config';
import { client } from '../src/services/redis';

const run = async () => {
  console.log('Running sandbox');
  await client.DEL('car');
  await client.hSet('car', {
    color: 'red',
    year: 1950,
  });
  const car = await client.hGetAll('car#54654654');
  if (!car) {
    return console.log('Car not found');
  }
  console.log(car);
};
run();

// npm run sandbox
```

Para resolver:

```javascript
if (Object.keys(car).length === 0) {
  return console.log('Car not found');
}
```

## Create User Implementation

Atualizamos o keys.js:

```javascript
export const pageCacheKey = (id: string) => `pagecache#${id}`;
export const usersKey = (userId: string) => `users#${userId}`;
```

E criamos a query do users:

```javascript
import type { CreateUserAttrs } from '$services/types';
import { genId } from '$services/utils';
import { client } from '$services/redis';
import { usersKey } from '$services/keys';

export const getUserByUsername = async (username: string) => {};

export const getUserById = async (id: string) => {
  const user = await client.hGetAll(usersKey(id));

  return deserialize(id, user);
};

export const createUser = async (attrs: CreateUserAttrs) => {
  const id = genId();

  await client.hSet(usersKey(id), serialize(attrs));

  return id;
};

const serialize = (user: CreateUserAttrs) => {
  return {
    username: user.username,
    password: user.password,
  };
};

const deserialize = (id: string, user: { [key: string]: string }) => {
  return {
    id,
    username: user.username,
    password: user.password,
  };
};
```

A função deserialize é usada para transformar o objeto que vem do redis em um objeto que a aplicação entende.

Essa linha:

```javascript
{ [key: string]: string }
```

Basicamente quer dizer que temos um objeto com várias keys em formato string e cada uma delas tem um valor em formato string.

## Implementing Sessions

Criamos o arquivo sessions.ts:

```javascript
import type { Session } from '$services/types';
import { sessionsKey } from '$services/keys';
import { client } from '$services/redis';

export const getSession = async (id: string) => {
  const session = await client.hGetAll(sessionsKey(id));

  if (Object.keys(session).length === 0) {
    return null;
  }

  return deserialize(id, session);
};

export const saveSession = async (session: Session) => {
  return client.hSet(sessionsKey(session.id), serialize(session));
};

const deserialize = (id: string, session: { [key: string]: string }) => {
  return {
    id,
    userId: session.userId,
    username: session.username,
  };
};

const serialize = (session: Session) => {
  return {
    userId: session.userId,
    username: session.username,
  };
};
```

## Dates

No Redis (não entendi se é só node) não consegue buscar por dadas nos formatos 1992-11-05T08:14:30-05:00 ou 'Thu Mar 17 1992 10:10:22 GMT -0500 (Eastern Standard Time)', mas no formato Unix Time Stamp consegue.

Criamos o arquivo serialize.ts e deserialize.ts:

```javascript
import type { CreateItemAttrs } from '$services/types';

export const serialize = (attrs: CreateItemAttrs) => {
  return {
    ...attrs,
    createdAt: attrs.createdAt.toMillis(),
    endingAt: attrs.endingAt.toMillis(),
  };
};
```

```javascript
import type { Item } from '$services/types';
import { DateTime } from 'luxon';

export const deserialize = (
  id: string,
  item: { [key: string]: string }
): Item => {
  return {
    id,
    name: item.name,
    description: item.description,
    imageUrl: item.imageUrl,
    highestBidUserId: item.highestBidUserId,
    ownerId: item.ownerId,
    createdAt: DateTime.fromMillis(parseInt(item.createdAt)),
    endingAt: DateTime.fromMillis(parseInt(item.endingAt)),
    views: parseInt(item.views),
    likes: parseInt(item.likes),
    bids: parseInt(item.bids),
    price: parseFloat(item.price),
  };
};
```

E usamos no item.ts:

```javascript
import type { CreateItemAttrs } from '$services/types';
import { client } from '$services/redis';
import { serialize } from './serialize';
import { genId } from '$services/utils';
import { itemsKey } from '$services/keys';
import { deserialize } from './deserialize';

export const getItem = async (id: string) => {
  const item = await client.hGetAll(itemsKey(id));

  if (Object.keys(item).length === 0) {
    return null;
  }

  return deserialize(id, item);
};

export const getItems = async (ids: string[]) => {};

export const createItem = async (attrs: CreateItemAttrs) => {
  const id = genId();

  const serialized = serialize(attrs);

  await client.hSet(itemsKey(id), serialized);

  return id;
};
```

E agora já conseguimos fazer o "sing up", vai dar erro mas aparece o nome na barra, podemos clicar em new e inserir um produto, o endereço na barra vai mudar para um endereço com o id do produto e podemos executar no rbook:

```bash
HGETALL items#2a62
```

E vai retornar o produto chair com suas propriedades.

## Pipeline

O pipeline é uma forma de enviar vários comandos para o redis ao invés de enviar um comando por vez.

Para exemplificar vamos no sandbox:

```javascript
import 'dotenv/config';
import { client } from '../src/services/redis';

const run = async () => {
  await client.hSet('car1', {
    color: 'red',
    year: 1950,
  });
  await client.hSet('car2', {
    color: 'green',
    year: 1955,
  });
  await client.hSet('car3', {
    color: 'blue',
    year: 1960,
  });

  const commands = [1, 2, 3].map((id) => {
    return client.hGetAll('car' + id);
  });

  // mesmo que a função acima:
  // const results = await Promise.all([
  //   client.hGetAll('car1'),
  //   client.hGetAll('car2'),
  //   client.hGetAll('car3'),
  //]);

  const results = await Promise.all(commands);

  console.log(results);
};
run();
```

No Node-Redis não tem uma função pronta para um pipeline, por isso usou a Promise.All. Em outras linguagens pode ter uma solução pronta, no C# por exemplo o código acima seria:

E implementamos a getItems:

```javascript
import type { CreateItemAttrs } from '$services/types';
import { client } from '$services/redis';
import { serialize } from './serialize';
import { genId } from '$services/utils';
import { itemsKey } from '$services/keys';
import { deserialize } from './deserialize';

export const getItem = async (id: string) => {
  const item = await client.hGetAll(itemsKey(id));

  if (Object.keys(item).length === 0) {
    return null;
  }

  return deserialize(id, item);
};

export const getItems = async (ids: string[]) => {
  const commands = ids.map((id) => {
    return client.hGetAll(itemsKey(id));
  });

  const results = await Promise.all(commands);

  return results.map((result, i) => {
    if (Object.keys(result).length === 0) {
      return null;
    }

    return deserialize(ids[i], result);
  });
};

export const createItem = async (attrs: CreateItemAttrs) => {
  const id = genId();

  const serialized = serialize(attrs);

  await client.hSet(itemsKey(id), serialized);

  return id;
};
```

## Sets

Criamos esse Notebook:

https://rbook.cloud/sheets/1add617177f31e30

```bash
SADD colors red blue green # => (integer) 3
SADD colors red # => (integer) 0
SADD colors yellow # => (integer) 1
SMEMBERS colors # => 1) "red" 2) "blue" 3) "green" 4) "yellow"
SISMEMBER colors red # => (integer) 1
SISMEMBER colors purple # => (integer) 0
SREM colors red # => (integer) 1
SREM colors purple # => (integer) 0
SMEMBERS colors # => 1) "blue" 2) "green" 3) "yellow"
```

Union of sets:

```bash
SADD colors red blue green # => (integer) 3
SADD colors2 red blue green yellow # => (integer) 4
SUNION colors colors2 # => 1) "red" 2) "blue" 3) "green" 4) "yellow"
```

Intersection of sets:

```bash
SADD colors red blue green # => (integer) 3
SADD colors2 red blue fucsia yellow # => (integer) 4
SINTER colors colors2 # => 1) "red" 2) "blue"
```

Difference of sets:

```bash
SADD colors red blue green # => (integer) 3
SADD colors2 red blue fucsia yellow # => (integer) 4
SDIFF colors colors2 # => 1) "green"
SDIFF colors2 colors # => 1) "fucsia" 2) "yellow"
```

SISMEMBER

```bash
SADD colors red blue green # => (integer) 3
SISMEMBER colors red # => (integer) 1
SISMEMBER colors purple # => (integer) 0
```

SCARD

```bash
SADD colors red blue green # => (integer) 3
SCARD colors # => (integer) 3
```

SSCAN

```bash
SADD colors red blue green # => (integer) 3
SSCAN colors 0 # => 1) "0" 2) 1) "red" 2) "blue" 3) "green"
SSCAN colors 1 # => 1) "0" 2) (empty list or set)
```

## Requiring Unique User Names

Atualizamos a função createUser:

```javascript
export const createUser = async (attrs: CreateUserAttrs) => {
  const id = genId();

  const exists = await client.sIsMember(usernamesUniqueKey(), attrs.username);
  if (exists) {
    throw new Error('Username is taken');
  }

  await client.hSet(usersKey(id), serialize(attrs));
  await client.sAdd(usernamesUniqueKey(), attrs.username);

  return id;
};
```

## Likes

Criamos o arquivo likes.ts:

```javascript
import { client } from '$services/redis';
import { userLikesKey, itemsKey } from '$services/keys';
import { getItems } from './items';

export const userLikesItem = async (itemId: string, userId: string) => {
  return client.sIsMember(userLikesKey(userId), itemId);
};

export const likedItems = async (userId: string) => {
  // Fetch all the item ID's from this user's liked set
  const ids = await client.sMembers(userLikesKey(userId));

  // Fetch all the item hashes with those ids and return as array
  return getItems(ids);
};

export const likeItem = async (itemId: string, userId: string) => {
  const inserted = await client.sAdd(userLikesKey(userId), itemId);

  // se conseguir inserir o item no set, incrementa o número de likes
  if (inserted) {
    return client.hIncrBy(itemsKey(itemId), 'likes', 1);
  }
};

export const unlikeItem = async (itemId: string, userId: string) => {
  const removed = await client.sRem(userLikesKey(userId), itemId);

  if (removed) {
    return client.hIncrBy(itemsKey(itemId), 'likes', -1);
  }
};

export const commonLikedItems = async (
  userOneId: string,
  userTwoId: string
) => {
  const ids = await client.sInter([
    userLikesKey(userOneId),
    userLikesKey(userTwoId),
  ]);

  return getItems(ids);
};
```

## Sorted Sets

ZADD, ZSCORE, ZREM

```bash
ZADD products 45 monitor # => (integer) 1
ZSCORE products monitor # => "45"
ZREM products monitor # => (integer) 1
ZSCORE products monitor # => (nil)
```

ZADD tem vários comandos complementares, NX, XX, CH, INCR, BYSCORE, BYLEX, REV, LIMIT, WITHSCORES.

Finding a range of scores:

```bash
ZADD products 45 monitor # => (integer) 1
ZADD products 50 keyboard # => (integer) 1
ZADD products 55 mouse # => (integer) 1
ZCARD products # => (integer) 3
ZCOUNT products 0 50 # => (integer) 2
ZCOUNT products 0 55 # => (integer) 3
ZCOUNT products (0 (55 # => (integer) 2 // greater than 0 and less than 55
ZCOUNT products -inf +inf # => (integer) 3
ZCOUNT products -inf 50 # => (integer) 2
```

Removal commands

```bash
ZADD products 45 monitor # => (integer) 1
ZADD products 50 keyboard # => (integer) 1
ZADD products 55 mouse # => (integer) 1
ZPOPMIN products 2 # => 1) "monitor" 2) "45" 3) "keyboard" 4) "50" // remove 2 items with the lowest score
```

```bash
ZADD products 45 monitor # => (integer) 1
ZADD products 50 keyboard # => (integer) 1
ZADD products 55 mouse # => (integer) 1
ZPOPMAX products 2 # => 1) "mouse" 2) "55" 3) "keyboard" 4) "50" // remove 2 items with the highest score
```

Updating Scores

```bash
ZADD products 5 monitor # => (integer) 1
ZADD products 50 keyboard # => (integer) 1
ZADD products 55 mouse # => (integer) 1
ZINCRBY products 10 monitor # => "15"
ZINCRBY products -10 keyboard # => "40"
```

Querying a sorted set:

```bash
ZADD products 5 monitor # => (integer) 1
ZADD products 45 keyboard # => (integer) 1
ZADD products 50 mouse # => (integer) 1
ZRANGE products 1 2 WITHSCORES # => 1) "keyboard" 2) "45" 3) "mouse" 4) "50"
ZRANGE products 1 2 # => 1) "keyboard" 2) "mouse"
ZRANGE products 0 48 BYSCORE WITHSCORES # => 1) "monitor" 2) "5" 3) "keyboard" 4) "45"
ZRANGE products 0 55 BYSCORE WITHSCORES # => 1) "monitor" 2) "5" 3) "keyboard" 4) "45" 5) "mouse" 6) "50"

```

Rev and Limit

```bash
ZADD products 5 monitor # => (integer) 1
ZADD products 45 keyboard # => (integer) 1
ZADD products 50 mouse # => (integer) 1

ZRANGE products 1 2 REV # => 1) "mouse" 2) "keyboard" // 1 e 2 são os índices. aqio retornados de forma reversa

```

O índice pode ser usado para paginar os resultados.
O limit pode ser usado para limitar a quantidade de resultados.

```bash
ZADD products 5 monitor # => (integer) 1
ZADD products 45 keyboard # => (integer) 1
ZADD products 50 mouse # => (integer) 1
ZRANGE products 0 60 BYSCORE LIMIT 0 1 # => 1) "monitor"
ZRANGE products 0 60 BYSCORE LIMIT 0 2 # => 1) "monitor" 2) "keyboard"
```

## Sorted Sets
