<details>
  <summary>Iniciando</summary>

# AZ-900

40 a 60 questões
85 minutos, em média 1 minuto e 40 segundos por questão
pontos de 1 a 1000, são necessários 700 pontos para passar

Pagamento e Agendamento via página da microsoft

Recomendou fazer pela Pearson Vue

Recursos
Computador
Ambiente deve ser um local privado e sem distrações
Documento de identificação com foto
Check In 30 minutos antes do horário marcado.

https://home.pearsonvue.com/Test-takers/Resources.aspx

Portal Azure

https://azure.microsoft.com/pt-br/free

Clicar em "Confira Todos os Serviços Gratuitos"

# Modelos de Cloud

IAAS - Infraestrutura como serviço
PASS - Plataforma como serviço
SAAS - Software como serviço

O IAAS alugamos a infraestrutura, ou seja, temos servidores físicos, mas não precisamos nos preocupar com a manutenção, pois a empresa que alugamos é responsável por isso.
O PAAS alugamos a plataforma, ou seja, temos servidores físicos e também o sistema operacional, mas não precisamos nos preocupar com a manutenção, pois a empresa que alugamos é responsável por isso. Aqui a aplicação é usada, Como por exemplo o Cosmo DB.
O SAAS alugamos o software, ou seja, temos servidores físicos, sistema operacional e o software, mas não precisamos nos preocupar com a manutenção, pois a empresa que alugamos é responsável por isso. Como por exemplo o Office 365.

### Leitura Complementar - Modelos de Cloud

Quais são os diferentes tipos de serviços de computação em nuvem?

Os tipos de computação em nuvem são modelos de implantação de serviço que permitem a seleção do nível de controle sobre as informações e tipos de serviço que precisam ser fornecidos. Há três tipos principais de serviços de computação em nuvem, às vezes chamados de pilha de computação em nuvem, pois são compilados um sobre o outro.

O primeiro tipo de computação em nuvem é a infraestrutura como serviço (IaaS), usada para acesso à recursos de computação e armazenamento baseados na Internet. Sendo a categoria mais básica entre os tipos de computação em nuvem, a IaaS permite que você alugue uma infraestrutura de TI (servidores e máquinas virtuais, armazenamento, redes e sistemas operacionais) de um provedor de nuvem em uma base paga conforme o uso.
https://azure.microsoft.com/pt-br/overview/what-is-iaas/

O segundo tipo de computação em nuvem é a plataforma como serviço (PaaS), que dá aos desenvolvedores as ferramentas necessárias para criar e hospedar aplicativos Web. A PaaS foi desenvolvida para proporcionar aos usuários o acesso aos componentes necessários para desenvolver e operar rapidamente aplicativos Web ou móveis na Internet, sem se preocupar com a configuração ou gerenciamento da infraestrutura subjacente dos servidores, armazenamento, redes e bancos de dados.
https://azure.microsoft.com/pt-br/overview/what-is-paas/

O terceiro tipo de computação em nuvem é o software como serviço (SaaS), usado para aplicativos baseados na Web. O SaaS é um método de entrega de aplicativos de software na Internet, no qual os provedores de nuvem hospedam e gerenciam os aplicativos de software, fazendo com que seja simples ter o mesmo aplicativo em todos seus dispositivos de uma só vez por meio da nuvem.
https://azure.microsoft.com/pt-br/overview/what-is-saas/

A Azure é excelente nos 3 tipos.

# Tipos de Cloud

Private - Nuvem privada, é uma nuvem que é usada apenas por uma organização, ou seja, é uma nuvem que é usada apenas por uma empresa. Temos que fazer um contato com um data center, fazer um co-location, ou seja, alugar um espaço no data center, e colocar nossos servidores lá. Temos que nos preocupar com licenças, hardware, manutenção, etc. Usado por bancos, governos etc.

Public - Nuvem pública, é uma nuvem que é usada por várias organizações, ou seja, é uma nuvem que é usada por várias empresas. Azure, AWS e Google Cloud são exemplos de nuvens públicas. Não temos que nos preocupar com licenças, hardware, manutenção, etc. Usado por empresas de pequeno, médio e grande porte. Não quer dizer que todo mundo acessa nossos dados, quer dizer que a nuvem é publica e pode ser contratada por qualquer empresa.

Hybrid - Nuvem híbrida, é uma nuvem que é usada por várias organizações, ou seja, é uma nuvem que é usada por várias empresas, mas que também pode ser usada por uma única organização. Podemos usar uma VM e dentro desta VM ter um software privado.

O private é o mais caro dos 3 tipos, o public é o mais barato dos 3 tipos e o hybrid é o intermediário.

## Leitura Complementar - Tipos de Cloud

### O que é nuvem privada?

Uma nuvem privada consiste em recursos de computação em nuvem usados exclusivamente por uma única empresa ou organização. A nuvem privada pode estar localizada fisicamente no datacenter local da sua organização ou pode ser hospedada por um provedor de serviços terceirizado. Mas em uma nuvem privada, os serviços e a infraestrutura são sempre mantidos na rede privada e o hardware e o software são dedicados unicamente à sua organização.

Dessa forma, com a nuvem privada é mais fácil para que a organização personalize seus recursos a fim de atender a requisitos de TI específicos. As nuvens privadas geralmente são usadas por órgãos governamentais, instituições financeiras e outras organizações de grande porte com operações críticas para os negócios, que buscam melhorar o controle sobre seu ambiente.

Vantagens de uma nuvem privada:

Maior flexibilidade – sua organização pode personalizar seu ambiente de nuvem para atender a necessidades de negócios específicas.

Maior controle – os recursos não são compartilhados com outros usuários, portanto, é possível um nível maior de controle e privacidade.

Maior escalabilidade –nuvens privadas geralmente oferecem mais escalabilidade em comparação com a infraestrutura local.

### O que é uma nuvem pública?

As nuvens públicas são a maneira mais comum de implantação da computação em nuvem. Os recursos de nuvem (como servidores e armazenamento) pertencem a um provedor de serviço de nuvem terceirizado, são operados por ele e entregues pela Internet. Com uma nuvem pública, todo o hardware, software e outras infraestruturas de suporte são de propriedade do provedor de nuvem e gerenciadas por ele. O Microsoft Azure é um exemplo de nuvem pública.

Em uma nuvem pública, você compartilha os mesmos dispositivos de hardware, de armazenamento e de rede com outras organizações ou "locatários" da nuvem e acessa serviços e gerencia sua conta usando um navegador da Web. As implantações de nuvem pública geralmente são usadas para fornecer email baseado na Web, aplicativos de escritório online, armazenamento e ambientes de desenvolvimento e teste.

Vantagens das nuvens públicas:

Redução de custos – não há necessidade de comprar hardware ou software e você paga somente pelos serviços que usa.

Sem manutenção – seu provedor de serviços fornece a manutenção.

Escalabilidade quase ilimitada – recursos sob demanda estão disponíveis para atender às suas necessidades de negócios.

Alta confiabilidade – uma ampla rede de servidores assegura contra falhas.

### Computação em nuvem híbrida

Uma nuvem híbrida é um tipo de computação em nuvem que combina uma infraestrutura local ou nuvem privada com uma nuvem pública. As nuvens híbridas permitem que os dados e aplicativos se movam entre os dois ambientes.

Muitas organizações adotam a abordagem de nuvem híbrida devido a exigências comerciais, por exemplo, para atender a requisitos regulatórios e de soberania de dados, aproveitar ao máximo o investimento em tecnologia local ou lidar com problemas envolvendo latência baixa.

A nuvem híbrida está evoluindo para incluir cargas de trabalho de borda também. A computação de borda traz a potência de computação da nuvem para dispositivos IoT, mais perto de onde os dados residem. Ao mover as cargas de trabalho para a borda, os dispositivos gastam menos tempo se comunicando com a nuvem, o que reduz a latência e permite a eles até mesmo operar de maneira confiável por períodos offline estendidos.

Espero que tenha gostado :)

## Leitura Complementar - 5 benefícios de Cloud

1. Flexibilidade

Para executar com eficácia uma estratégia de transformação digital, uma empresa precisará girar seu processo de negócios várias vezes. A computação em nuvem poupa uma organização do trabalho de investir em vários recursos de TI, fornecendo recursos de computação, infraestrutura, banco de dados e plataformas em trânsito. Isso permite que uma empresa seja ágil e flexível.

2. Custo-benefício

Juntamente com a flexibilidade de ajustar os requisitos, a nuvem oferece um modelo de serviço escalável, em que uma empresa paga apenas pelos recursos usados. Assim, não apenas economiza o custo de capital na compra e no gerenciamento da infraestrutura de TI, mas também ajuda as empresas a dimensionar seus recursos com base nos requisitos.

3. Segurança

Se o seu banco de dados é armazenado internamente, você enfrenta constantemente o risco de perder informações críticas devido a violações de dados, desligamentos inesperados do sistema, desastres, ataques de cibercriminosos etc.

No caso de hospedagem em nuvem, você pode criar facilmente vários backups de seus dados. Isso é especialmente benéfico ao lidar com Big Data, pois as chances de falhas do sistema aumentam significativamente nesse caso.

4. Prototipagem rápida

Para que a transformação digital funcione e a cultura de inovação seja implantada, uma empresa precisa inovar, testar e repetir continuamente.

O cloud computing pode fornecer às empresas uma plataforma em que podem facilmente criar, testar e implantar aplicativos sem a necessidade de configurar uma infraestrutura complexa. Assim, durante a fase de transformação, uma empresa pode experimentar vários aplicativos em diferentes plataformas.

5. Melhor colaboração

A transformação digital exige que uma empresa se adapte a uma cultura de inovação e criatividade e deixe a antiga cadeia hierárquica de comandos. A computação em nuvem permite que os arquivos sejam acessados ​​de qualquer lugar e a qualquer momento.

Também é possível controlar o nível de autoridade do usuário, garantindo assim a delegação ideal. No geral, ajuda a criar uma atmosfera de colaboração e trabalho em equipe na empresa.

Todos esses benefícios sugerem claramente que, se você criar uma cultura de inovação em sua empresa, a nuvem é uma solução lógica e ideal.

</details>

<details>
  <summary>Estrutura Azure</summary>

# Regiões e Zonas de Disponibilidade

Região - É um local geográfico no planeta que contém um ou mais data centers. Por exemplo, a região Leste dos EUA contém data centers em Virgínia e Carolina do Norte.

Zona de disponibilidade - É um ou mais data centers em uma região que contém energia, rede e instalações independentes das outras zonas de disponibilidade da região. Por exemplo, a zona de disponibilidade 1 na região Leste dos EUA contém data centers em Virgínia e Carolina do Norte.

Em SP temos 3 data centers, caso aconteça um desastre em um data center, os outros 2 data centers continuam funcionando. Sempre que criamos uma VM em uma zona de disponibilidade, o Azure replica a VM para as outras zonas de disponibilidade. Caso aconteça um desastre em uma zona de disponibilidade, a VM continua funcionando nas outras zonas de disponibilidade e não percebemos nada. Isso ocorre pois a Azure tem links de fibra ótica entre os data centers com uma latência muito baixa.
A Azure tem no mínimo 3 zonas de disponibilidade em cada região.

https://azure.microsoft.com/pt-br/explore/global-infrastructure/geographies/#geographies

Neste link podemos ver as regiões e zonas de disponibilidade da Azure.

Podemos ver também os Produtos habilitados por região. Podemos haver regiões que não tem todos os produtos habilitados. E o valor dos produtos também pode variar de região para região.

Deve ser avaliado também onde estão os clientes, pois se os clientes estão em SP, não faz sentido criar uma VM em outra região, pois a latência será maior.

# Grupos de Recursos

Esta parte é mais virtual dentro da plataforma da azure.

Grupo de recursos - É um container que contém todos os recursos relacionados a uma solução. Podemos ter vários grupos de recursos dentro de uma assinatura. Podemos ter um grupo de recursos para cada solução, por exemplo, um grupo de recursos para o sistema de vendas, um grupo de recursos para o sistema de compras, etc.

Quando iniciamos um serviço na microsoft, temos que associar a um grupo de recursos. Podemos ter um grupo de recursos chamado "servers" por exemplo, ou "db". Dentro deste grupo de recursos podemos ter vários servidores, ou vários bancos de dados.

Pode ser feito por filiais da empresa também, por exemplo, um grupo de recursos para a filial de SP, um grupo de recursos para a filial de MG, etc.

Quando temos um grupo de recursos, podemos ver por cada um dos grupos de recuros os valores que estão sendo gastos, por exemplo, o grupo de recursos "servers" está gastando R$ 100,00, o grupo de recursos "db" está gastando R$ 200,00, etc.

Quem gerencia os recursos é o Azure Resource Manager ou ARM.

</details>

<details>
  <summary>Computacional</summary>
# Máquinas Virtuais

Criamos um grupo de recursos chamado "servers" por exemplo, e dentro deste grupo de recursos criamos uma VM.

Na criação da VM, temos várias etapas, Básico, Discos, Rede, Gerenciamento, Avançado, Marcas e Revisar + Criar.

Na etapa Básico, temos que escolher o nome da VM, o usuário, a senha, a assinatura, o grupo de recursos, a região, a zona de disponibilidade, a imagem, o tamanho, o disco gerenciado, a conta de armazenamento, o nome do disco, o tipo de conta de armazenamento, o local de armazenamento, o tipo de replicação, o tipo de rede, o endereço IP público, a rede virtual, o sub-rede, o endereço IP privado, a placa de rede, o nome DNS, o nome de domínio.

Criamos uma VM para demonstração e logo depois fizemos a exclusão da VM e do Disco do Sistema Operacional e as Interfaces de Rede. Caso não excluísse os recursos criados, iria continuar cobrando mesmo não usando.

A VM pode ser criada via az vm create no cli ou via jenkins.

Exemplo de script:

```
az vm create \
  --resource-group myResourceGroup \
  --name myVM \
  --image UbuntuLTS \
  --admin-username azureuser \
  --generate-ssh-keys
```

Para a criação de muitas VMs, é melhor usar o script, pois é mais rápido.

# Azure MarketPlace

O MarketPlace oferece imagens de VMs prontas para uso, por exemplo, temos imagens do Windows Server, do Ubuntu, do Red Hat, etc.

Temos uma imagem do WordPress por exemplo, que já vem com o WordPress instalado, e só precisamos configurar o banco de dados.

Podemos criar um Firewall da PaloAlto por exemplo, que já vem com o Firewall instalado. Esse pagamos a licença por exemplo.

A MarketPlace tem várias soluções implementadas.

# Scale Set

É um conjunto de máquinas virtuais idênticas, que são criadas para trabalhar em conjunto, por exemplo, um conjunto de máquinas virtuais para um sistema de vendas, um conjunto de máquinas virtuais para um sistema de compras, etc.

Podemos definir os parâmetros do scale set para que ele aumente ou diminua o número de máquinas virtuais de acordo com a demanda. O parâmetro pode ser consumo de CPU e memória por exemplo.

Quem controla o tráfego é o Load Balancer.

No scale set definimos o mínimo e máximo de VMs que queremos que fique rodando. A própria plataforma da azure irá aumentar ou diminuir o número de VMs de acordo com a demanda.

Não há custo extra por configurar o scale set.

Caso ocorra alguma falha na VM, o scale set irá criar uma nova VM para substituir a VM que falhou.

# APP Service

É um serviço que permite que você crie e hospede aplicativos Web, móveis, API e lógica rapidamente, sem gerenciar a infraestrutura. Ele oferece implantação contínua e dimensionamento automático, além de suportar vários idiomas, como .NET, .NET Core, Java, Ruby, Node.js, PHP, Python e Docker. O Azure App Service permite que você crie aplicativos e sites corporativos em escala.

O App Service é um serviço gerenciado, ou seja, não precisamos nos preocupar com a infraestrutura, pois a Azure faz isso para nós.

Pode ser executado no Kubernetes, no Windows, no Linux, etc.

O Còdigo pode acessar uma storage blob, um banco de dados, etc.

O App Service é pago por acesso, ou seja, se tivermos 1000 acessos, pagaremos por 1000 acessos.

# Containers

É uma forma de empacotar o código, as configurações e as dependências de um aplicativo em um único objeto. Os contêineres compartilham o sistema operacional do host e, portanto, são considerados mais leves que as VMs. Além disso, os contêineres são mais fáceis de criar e implantar.

Ao invés de subir o código em outra máquina, empacotamos o código em um container e subimos o container em outra máquina. Geramos uma imagem do container e subimos a imagem do container em outra máquina. Pode ser feito o deploy desta imagem.

A Azure usa o Azure Container Instance, ou ACI.

Podemos pesquisar por Azure Container no portal azure e veremos os serviços relacionados a containers.

# Azure Kubernetes Service (AKS)

É um serviço de orquestração de contêineres totalmente gerenciado que permite implantar, gerenciar e dimensionar aplicativos de contêiner sem esforço. Ele oferece um ambiente de desenvolvimento de contêineres com suporte nativo ao Kubernetes. O AKS é gratuito, você paga apenas pelos recursos de computação e armazenamento que usa.

O AKS é um serviço gerenciado, ou seja, não precisamos nos preocupar com a infraestrutura, pois a Azure faz isso para nós.

Os PODs são os containers que estão rodando no Kubernetes.

# Área de Trabalho Virtual do Azure (AVD)

Azure Virtual Desktop é um serviço de virtualização de área de trabalho e aplicativos que executa o Windows 10 em nuvem. Ele fornece aos usuários acesso remoto a aplicativos e desktops Windows hospedados em um data center do Azure de qualquer lugar do mundo.

O Pool de Hosts pode ser criado e permite que vários usuários acessem o mesmo Pool de Hosts. A vantagem é que podemos instalar os aplicativos em um único Pool de Hosts e todos os usuários terão acesso aos mesmos aplicativos.

A principal diferença entre a Área de Trabalho Virtual do Azure e a criação de VMs é que na Área de Trabalho Virtual do Azure, podemos criar um Pool de Hosts e vários usuários podem acessar o mesmo Pool de Hosts. Na criação de VMs, cada usuário teria que ter uma VM.

Não são somente as VMs que podem estar dentro da Área de Trabalho Virtual do Azure, podemos ter também desktops físicos.

# Aplicativo de Funções

Imagine que em um marketplace, receba 10.000 visitas por hora e dessas, 100 viram compras.

No marketplace, as 100 que viram compras, disparam um processo de criação de mensagem para um parceiro externo que irá entregar o produto.

Com o Aplicativo de Funções, podemos mover esta parte do código para o Aplicativo de Funções e não precisamos nos preocupar com a infraestrutura, ou seja, na nossa VM do MarketPlace não precisamos dimensionar o recurso para envio de mensagens.

A parte volátil da solução é colocada no Aplicativo de Funções. Caso não seja feita nenhuma venda, não haverá custo e o Aplicativo de Funções não estará rodando.

</details>

<details>
  <summary>Rede</summary>

# IPV4

É um endereço de 32 bits, ou seja, 4 bytes, ou seja, 4 octetos, ou seja, 4 números de 0 a 255.
Por ex. podemos ter 3 PCs, 10.1.1.1, 10.1.1.2, 10.1.1.3. Como eles tem o mesmo início, significa que estão na mesma rede.

Se colocarmos 10.1.1.1/16 por exemplo, significa que os 2 primeiros octetos são fixos e os 2 últimos octetos podem variar de 0 a 255. Ou seja, os 16 primeiros bits pertencem a rede e os outros 16 aos hosts.

ou seja, 10.1 é a rede e 1.1 é o host.

O IPV4 é usado dentro da estrutura da Microsoft Brasil.

# Criando uma VNET no portal Azure

Vamos montar uma rede própria para o nosso ambiente. Por exemplo a VNET "Dev".

Podemos criar duas VMs, Dev1 e Dev2, e colocar as duas VMs na VNET "Dev".

No portal Azure primeiro vamos criar a Rede, buscamos "rede" e escolhemos "redes virtuais".

Clicamos em "Adicionar" e preenchemos os campos.

A azure sugere 10.1.0.0/16. Para este exemplo está ok. Na criação é informado que podemos ter 65.536 endereços IP.

Na segurança vamos criar um Bastion Host, que vai nos possibilitar acessar as VMs de forma remota, passou o AzureBastionSubnet 10.1.2.0/24, para que a Azure utilize os 3 primeiros octetos para a rede e o último octeto para o host.

Caso ainda não tenha um endereço público podemos escolher "dev-public" para criar um endereço público.

# Criação das VMs na rede Dev

Criou 2 VMs Linux que sobem mais rápido que as VMs Windows. Pois só vamos testar ping.

Configurou a segurança com Senha ao invés de chave pública somente para simplificar.

Na parte de Rede, selecionou a rede "Dev".

Após a criação podemos ver que o IP assignado a VM.

# Conexão com as VMs

Vamos enviar um ping para 8.8.8.8 que é o DNS do Google para validarque temos conexão com a internet.

Abrimos a primeira máquina virtual e clicamos em "Conectar" e escolhemos "Bastion". Preenchemos login e senha e clicamos em "Conectar". Já abre o linux.

comandos no terminal:

```
sudo su
apt instal net-tools
ifconfig
```

O IP assignado foi o 10.1.0.4

Na interface do portal Azure, podemos ver os detalhes da VM, inclusive o IP assignado. Da segunda máquina ficou 10.1.0.5.

Agora entramos na VM1 e enviamos um ping para o DNS do Google e funcionou.

Enviamos um ping da Dev2 para 10.1.0.4 que é a Dev1 e funcionou.

Nas remoções, primeiro removeu as VMs.

Depois entrou em Redes Virtuais / Dev e aparecem as duas VMs e o Bastion. Removeu o Bastion e depois removeu os endereços das VMs de dentro da rede.

Depois removeu a Rede Virtual Dev. A exclusão do Bastion demora um pouco. Validou que a rede virtual Dev foi excluída, validou que as VMs foram excluídas tbm.

# Balanceador de Carga - Load Balancer

O Load Balancer é um serviço que distribui o tráfego entre várias máquinas virtuais ou servidores para melhorar o desempenho e a confiabilidade dos aplicativos. O Load Balancer fornece alta disponibilidade ao distribuir as solicitações de entrada entre duas ou mais máquinas virtuais do conjunto de máquinas virtuais. Cada máquina virtual no conjunto de máquinas virtuais recebe uma parte do tráfego de entrada.

O Load Balancer fica entre o FrontEnd e o BackEnd e pode ter regras, por exemplo se temos 2 VMs com recursos diferentes, podemos enviar 70% das requests para a VM1 e 30% para a VM2.

# VPN Gateway

O Gateway VPN é um serviço que permite conectar uma rede local a uma rede virtual do Azure. O Gateway VPN pode ser usado para enviar tráfego de rede entre redes virtuais do Azure e locais, entre redes virtuais do Azure e entre redes virtuais. O Gateway VPN usa o protocolo IPsec (Protocolo de Segurança da Camada de Internet) para criar uma conexão segura e criptografada (normalmente com uma chave de 256 bits), entre os recursos do Azure e os recursos locais.

Por exemplo temos servidores físicos na rede da empresa e temos servidores virtuais na Azure. Podemos criar uma VPN entre a rede da empresa e a Azure. Essa VPN vai circular as informações dentro de um túnel encriptado. Será encriptado na saída e decriptado na entrada.

# Application Gateway

O Application Gateway é um serviço de balanceamento de carga de aplicativos da Web que permite criar um gateway de aplicativo altamente disponível e dimensionável para aplicativos Web, APIs e funções. O Application Gateway fornece recursos de balanceamento de carga de camada 7 (HTTP/HTTPS), roteamento de tráfego, regras de back-end, regras de redirecionamento, SSL offloading/terminação e muito mais.

É uma melhora do Load Balancer que é de camada 4, ou seja, não tem regras de negócio. O Application Gateway é de camada 7, ou seja, tem regras de negócio. Por exemplo podemos ter uma VM que entrega as imagens e outra VM que entrega os vídeos para o front-end. Podemos ter uma regra que se o usuário acessar uma imagem, o Application Gateway envia a request para a VM que entrega as imagens, e se o usuário acessar um vídeo, o Application Gateway envia a request para a VM que entrega os vídeos.

Recomendou a leitura do link abaixo:
https://learn.microsoft.com/pt-br/azure/application-gateway/overview

# Express Route

O ExpressRoute é um serviço de conectividade de rede que permite criar conexões privadas entre a infraestrutura local e a rede do Azure ou o Microsoft Cloud. O ExpressRoute permite estabelecer conexões com a Microsoft, como Azure, Microsoft 365 ou Dynamics 365, em um ambiente de rede de camada 3. Os circuitos ExpressRoute não passam pela Internet pública.

Por exemplo se quisermos trafegar muitos terabytes de dados diariamente para o storage (empresa de streaming de vídeos por exemplo), não é viável trafegar pela internet, pois a internet é lenta. Podemos criar uma conexão privada entre a empresa e a Azure, e trafegar os dados por esta conexão privada.

O custo do ExpressRoute é alto, pois é uma conexão privada.

# CDN

O Azure Content Delivery Network (CDN) é um serviço de rede de entrega de conteúdo para entrega de conteúdo de alta largura de banda. Ele fornece uma maneira globalmente distribuída de fornecer conteúdo de sites de alto desempenho, como imagens, vídeos, arquivos de áudio, aplicativos, atualizações de software e outros arquivos da Web para os usuários finais, com alta disponibilidade e alto desempenho. O Azure CDN oferece suporte a conteúdo não somente do Azure, mas também de outros locais, como um data center local, e pode ser habilitado para conteúdo hospedado em qualquer lugar na Web.

CDN de maneira geral é uma rede de distribuição de conteúdo. Por exemplo, temos um site que tem muitas imagens, e estas imagens estão em um storage na Azure. Se o usuário acessar o site de SP, a imagem vai ser carregada de SP, se o usuário acessar o site de MG, a imagem vai ser carregada de MG, etc. Ou seja, a imagem vai ser carregada do local mais próximo do usuário. Isso é feito para melhorar a performance.

As CDNs ao redor do mundo se comunicam e trocam informações para saber onde está o conteúdo mais próximo do usuário.

Caso o conteúdo seja muito dinâmico e mude muito, não é recomendado usar CDN pois a cópia dos dados de uma CDN para outra demora um pouco.

</details>

<details>
  <summary>Armazenamento</summary>

# Blob Storage

O Azure Blob Storage é um serviço de armazenamento de objetos para armazenar grandes quantidades de dados não estruturados, como texto ou dados binários.
BLOB significa Binary Large Object.

Podemos armazenar por exemplo arquivos jpg, mp4, docs, xls, etc. Esses arquivos ficam armazenados em um container e o container fica dentro de uma storage account que é o Blob Storage.

Em uma VM podemos ter referências para o Blob Storage e acessar os arquivos. Nâo é necessário armazenar os arquivos na VM.

Temos 3 tipos de armazenamento na Azure:

- Hot: É o mais caro, mas é o mais rápido. É recomendado para arquivos que são acessados com frequência.
- Cool: É mais barato que o Hot, mas é mais lento. É recomendado para arquivos que são acessados com menos frequência. Os dados devem ser armazenados por no mínimo 30 dias antes de serem acessados, caso contrário será cobrado uma taxa de saída e será mais caro que o Hot.
- Archive: É o mais barato, mas é o mais lento. É recomendado para arquivos que são acessados com muita pouca frequência. Deve ser usado para backups. É normal deixar arquivos por anos sem acessar. Os dados devem ser armazenados por no mínimo 180 dias antes de serem acessados, caso contrário será cobrado uma taxa de saída e será mais caro que o Cool.

# Criando um Blob Storage

No portal Azure buscamos por Contas de Armazenamento e clicamos em "Adicionar". Pode ser que já exista uma conta de armazenamento, então clicamos em "Adicionar" e preenchemos os campos.

Criamos o Resource Group ou adicionamos a um existente, escolhemos o nome da conta de armazenamento, escolhemos a região, escolhemos o tipo de replicação, escolhemos o tipo de acesso, escolhemos o tipo de performance.

Podemos definir a redundância local, ou seja, os dados ficam em um data center, ou a redundância geográfica, ou seja, os dados ficam em vários data centers. Os custos são diferentes e vão aumentando de acordo com a redundância.

Em rede podemos definir se a conta de armazenamento vai ser acessada por qualquer rede, ou por uma rede específica, ou por uma rede virtual. Pode ser pública ou privada.

# Adicionando Arquivos ao container

Podemos fazer via web, baixar um software ou pelo Gerenciador de Armazenamento.
Ao entrar no Gerenciador de Armazenamentoi, vemos que não existe nenhum Conteiners de Blob criado. Criamos um container chamado "imagens" por exemplo e escolhemos o tipo de acesso, que pode ser privado, público ou restrito.

Após criar o blob, aparece uma interface para fazer upload de arquivos. Fizemos o upload de um arquivo jpg. Para visualizar podemos fazer o download ou clicar com o botão direito e nas propriedades do arquivo, copiar o link e colar no navegador. Ou ir direto no botão de copiar url após selecionar o arquivo.

# Gerenciamento de Discos

Quando criamos uma VM na Azure, é criado um disco para a VM. Podemos criar um disco de sistema operacional, um disco de dados, um disco de cache, etc.

Podemos depois adicionar um disco separado para armazenar os dados, pois se excluírmos a VM, não vamos perder os dados e podemos incluir em outra VM.

A Azure disponibiliza quatro tipos de discos:
HDD, Standard SSD, Premium SSD e Ultra Disk.
O HDD é usado para backups, pois é mais barato.
O Standard SSD é usado para arquivos que são acessados com menos frequência.
O Premium SSD é usado para arquivos que são acessados com mais frequência.
O Ultra Disk é usado para arquivos que são acessados com muita frequência e pode chegar a 64 TB.

Ao acessar a interface "Discos" no portal da Azure encontramos alguns discos, apesar de termos removido todas as VMs, os discos não foram removidos.

É possível alterar a configuração, o tamanho, desempenho etc.

Sempre que excluirmos uma VM, devemos nos certificar que os discos foram excluídos também.

</details>

<details>
  <summary>Banco de Dados</summary>

</details>

<details>
  <summary>Segurança</summary>

</details>

<details>
  <summary>Soluções Azure</summary>

</details>

<details>
  <summary>Valores e Suporte</summary>

</details>

<details>
  <summary>Simulado</summary>

</details>

<details>
  <summary>Finalizando</summary>

</details>
