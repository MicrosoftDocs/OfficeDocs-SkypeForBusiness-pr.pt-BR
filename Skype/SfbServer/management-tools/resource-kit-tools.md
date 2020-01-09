---
title: Documentação das Ferramentas do Kit de Recursos do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: Este tópico descreve as ferramentas no kit de recursos do Skype for Business Server 2015, incluindo a finalidade de cada ferramenta e exemplos de seu uso. O kit de recursos do Skype for Business Server 2015 ajuda a facilitar tarefas de rotina para administradores de ti que implantam e gerenciam o Skype for Business Server 2015. Por exemplo, a ferramenta Web Conf Data pode ser usada para controlar facilmente os dados carregados pelos usuários durante uma reunião online. A ferramenta SEFAUtil pode ser usada para configurar o encaminhamento e as respostas de chamadas de representantes para os usuários. Incentivamos os administradores de ti a usar essas ferramentas para gerenciar o Skype for Business Server 2015 com mais eficiência.
ms.openlocfilehash: 0087f4286246833f0266ad0c78636bad00167756
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992528"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Documentação das Ferramentas do Kit de Recursos do Skype for Business Server 2015

Este tópico descreve as ferramentas no kit de recursos do Skype for Business Server 2015, incluindo a finalidade de cada ferramenta e exemplos de seu uso. O kit de recursos do Skype for Business Server 2015 ajuda a facilitar tarefas de rotina para administradores de ti que implantam e gerenciam o Skype for Business Server 2015. Por exemplo, a ferramenta **Web Conf Data** pode ser usada para controlar facilmente os dados carregados pelos usuários durante uma reunião online. A ferramenta **SEFAUtil** pode ser usada para configurar o encaminhamento e as respostas de chamadas de representantes para os usuários. Incentivamos os administradores de ti a usar essas ferramentas para gerenciar o Skype for Business Server 2015 com mais eficiência.

## <a name="installation-of-the-resource-kit-tools"></a>Instalação das Ferramentas do Kit de Recursos

Para instalar o kit de recursos do Skype for Business Server 2015, baixe o [OCSReskit. msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) do centro de download.

Execute o **OCSResKit.msi** para fazer uma instalação simples. O .msi instala todas as ferramentas no seguinte caminho: **%Arquivos de Programas%\Skype for Business Server 2015\ResKit**. As ferramentas que são executáveis autocontidos ficam nessa pasta. As ferramentas que também têm arquivos de suporte ficam em suas próprias subpastas.

## <a name="supported-environments"></a>Ambientes com suporte

O kit de recursos do Skype for Business Server 2015 deve ser instalado em um servidor que atenda às especificações necessárias para o Skype for Business Server 2015, geralmente um sendo usado para executar o Skype for Business Server 2015.

## <a name="resource-kit-tools-overview"></a>Visão geral das Ferramentas do Kit de Recursos

Veja a seguir uma lista das ferramentas fornecidas no kit de recursos do Skype for Business Server 2015. As seções a seguir mostram uma descrição de cada ferramenta, com requisitos e exemplos de uso.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Monitor de Serviço da Política de Largura de Banda](resource-kit-tools.md#bpsm)

- [Analisador de Utilização de Largura de Banda](resource-kit-tools.md#bua)

- [Estacionador de Chamadas](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Importar Dados do Serviço de Armazenamento](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Pesquisar no Console de Usuários](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Visualizador da Configuração de Rede](resource-kit-tools.md#NCV)

- [Agente do Grupo de Resposta em Tempo Real](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [Migração de Comunicados de Número não Atribuído](resource-kit-tools.md#UNAM)

- [Web Conf Data](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

A ferramenta de configuração de serviço de catálogo de endereços (ABSConfig) é uma ferramenta administrativa que ajuda administradores a personalizar a configuração de serviço de catálogo de endereços no Skype for Business Server 2015. Essa ferramenta também permite que os administradores do Skype for Business Server 2015 restaurem as configurações de serviço de catálogo de endereços padrão.

### <a name="description"></a>Descrição

O ABSConfig é um aplicativo gráfico de interface do usuário que permite aos administradores configurar os atributos dos serviços de domínio Active Directory relacionados ao serviço de catálogo de endereços.

Veja aqui os principais cenários da ferramenta:

- Para permitir que os administradores mapeiem atributos nos serviços de domínio Active Directory para os atributos do Skype for Business Server 2015.

- Permitir que os administradores especifiquem os atributos do Active Directory Domain Services a serem incluídos ou excluídos dos arquivos do Serviço de Catálogo de Endereços.

- Permitir que os administradores restaurem as configurações padrão do Serviço de Catálogo de Endereços.

A ferramenta ABSConfig pode ser iniciada usando o arquivo absConfig.exe. A ferramenta é aberta na guia **Configurar atributos** . Esta tabela tem opções para mapear atributos dos serviços de domínio Active Directory para os campos de atributo do Skype for Business Server 2015 e especificar quais usuários incluir ou excluir nos arquivos do serviço de catálogo de endereços com base em filtros de atributo específicos. Ela também tem opções para personalizar quais números telefônicos serão incluídos no arquivo do Catálogo de Endereços. A opção **Restaurar Padrões** permite aos administradores restaurar os valores padrão das configurações do Serviço de Catálogo de Endereços.

> [!NOTE]
> O remapeamento de atributos do anúncio para nomes de campos OC diferentes só funcionará com o download do arquivo de catálogo de endereços e não é compatível com a consulta à Web do catálogo de endereços.

### <a name="output"></a>Resultado

A ABSConfig armazena a configuração do Serviço de Catálogo de Endereços no banco de dados.

```PowerShell
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Objetivo

O ABSConfig oferece uma maneira rápida e fácil de personalizar o serviço de catálogo de endereços do Skype for Business Server 2015.

### <a name="requirements"></a>Requisitos

#### <a name="computer"></a>Computador

O ABSConfig pode ser executado apenas em um computador associado a um domínio que tenha o Skype for Business Server 2015 instalado. No caso do Skype for Business Server 2015, Enterprise Edition, essa ferramenta pode ser executada em qualquer servidor front-end que tenha o serviço de catálogo de endereços habilitado durante a instalação.

#### <a name="network"></a>Rede

O computador deve poder se conectar ao pool de front-ends e ao banco de dados back-end.

#### <a name="software"></a>Software

Os seguintes componentes de software deverão ser instalados antes de executar a ferramenta ABSConfig:

- Skype for Business Server 2015

#### <a name="users"></a>Usuários

Administradores que têm as permissões necessárias para atualizar a implantação do Skype for Business Server 2015.

### <a name="examples"></a>Exemplos

A ABSConfig pode ser iniciada digitando **ABSConfig.exe** em um prompt de comando. Abaixo é mostrada a interface do usuário da ferramenta ABSConfig.

![A ferramenta ABSConfig. exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Resumo

A ferramenta ABSConfig fornece aos administradores uma ferramenta rápida e fácil de usar para personalizar o serviço de catálogo de endereços do Skype for Business Server 2015.

## <a name="bandwidth-policy-service-monitor"></a>Monitor de Serviços da Política de Largura de Banda
<a name="bpsm"> </a>

A ferramenta Monitor de Serviços da Política de Largura de Banda permite que os administradores visualizem uma lista contendo:

1. Todos os serviços de política de largura de banda do Skype for Business Server 2015 configurados (autenticação e núcleo) na topologia

2. As conexões de cada um dos serviços com outros serviços da Política de Largura de Banda e servidores de borda.

3. Todos os links configurados contidos no documento de configuração de rede e uso de largura de banda em tempo real, conforme relatado por cada um dos serviços da Política de Largura de Banda.

### <a name="description"></a>Descrição

A ferramenta Monitor de Serviços da Política de Largura de Banda é implementada como um aplicativo baseado na GUI. Os administradores iniciam a ferramenta executando PDPMonUI.exe.

Quando a ferramenta é iniciada, ela tenta descobrir a lista dos serviços da Política de Largura de Banda na topologia. Após a conclusão da atualização inicial, o painel à esquerda da janela é populada com uma lista de serviços agrupados pelos clusters aos quais pertencem.

Quando os administradores selecionam determinado Serviço da Política de Largura de Banda, o painel à direita exibe as informações sobre o serviço. O painel também tem duas guias principais que exibem informações.

#### <a name="machine-info-tab"></a>Guia Informações do Computador

A guia **Informações do Computador** mostra os detalhes do Serviço da Política de Largura de Banda selecionado, bem como a lista e o estado de todas as conexões realizadas pelo Serviço da Política de Largura de Banda selecionado com outros serviços.

#### <a name="topology-info-tab"></a>Guia Informações da Topologia

A guia **Informações da Topologia** mostra uma lista de todos os links definidos nas configurações de rede. É exibida a capacidade de largura de banda de vídeo e áudio de cada link. Além disso, a largura de banda utilizada atualmente também é exibida, em Kbps e em um percentual da capacidade. A ferramenta usa codificação por cores para realçar os links cuja utilização esteja próxima do limite de capacidade, permitindo que os administradores isolem rapidamente esses links.

> [!NOTE]
>  Se a ferramenta monitoração do serviço de política de largura de banda apresentar falha quando ela se conecta a qualquer um dos serviços de política de largura de banda configurados, as informações nas guias **informações do computador** e **informações de topologia** não serão preenchidas. No entanto, é possível que a ferramenta se conecte inicialmente, mas depois perca a conexão com o serviço. Nesses casos, os administradores poderão ver informações desatualizadas. Há um carimbo de data/hora **Última Atualização** em cada uma das guias que permite aos administradores ver quando os dados foram atualizados pela última vez para um determinado Serviço da Política de Largura de Banda.

### <a name="output"></a>Resultado

Não há nenhum resultado na linha de comando; o resultado do programa está contido dentro da GUI (interface gráfica do usuário) principal.

### <a name="purpose"></a>Objetivo

O objetivo da ferramenta Monitor de Serviços da Política de Largura de Banda é proporcionar aos administradores visibilidade do estado de cada um dos serviços da Política de Largura de Banda definidos na topologia. Além disso, os administradores podem ver o uso da largura de banda em tempo real de todos os links definidos no documento de configuração da rede.

### <a name="requirements"></a>Requisitos

A ferramenta de monitoração do serviço de política de largura de banda precisa ser executada em um computador que faça parte da topologia do Skype for Business Server.

### <a name="summary"></a>Resumo

A ferramenta Monitor de Serviços da Política de Largura de Banda pode ser um recurso valioso para os administradores, pois com ela é possível inspecionar na topologia o estado de todos os serviços da Política de Largura de Banda e, o mais importante, obter a utilização da largura de banda em tempo real dos links definidos nas configurações da rede.

## <a name="bandwidth-utilization-analyzer"></a>Analisador de Utilização da Largura de Banda
<a name="bua"> </a>

O Analisador de Utilização da Largura de Banda é uma ferramenta que cria relatórios sobre diversas exibições do consumo de largura de banda pelos pontos de extremidade de UC nos links WAN da rede corporativa. Esses relatórios podem ser usados para entender o padrão de consumo de largura de banda atual e auxiliar no planejamento de capacidade de largura de banda.

### <a name="description"></a>Descrição

O Analisador de Utilização da Largura de Banda é implementado como um aplicativo baseado na GUI. Essa ferramenta gera relatórios específicos para utilização de áudio na rede e ajuda no planejamento da capacidade. Também itera na capacidade de largura de banda atribuída a diversos links.

### <a name="output"></a>Resultado

O Analisador de Utilização da Largura de Banda fornece plotagens gráficas da utilização e da capacidade de largura da banda de áudio de todos os links WAN configurados no sistema.

### <a name="purpose"></a>Objetivo

Em qualquer implantação de voz e vídeo, é essencial monitorar e entender a tendência de utilização de largura de banda do tráfego de mídia na rede da empresa. A ferramenta Analisador de Utilização da Largura de Banda permite ao administrador realizar justamente isso. Essa ferramenta faz o seguinte:

- Gera relatórios específicos de utilização de áudio na rede.

- Ajuda com um planejamento de capacidade mais eficaz e com a iteração na capacidade de largura de banda atribuída a vários links.

O Analisador de Utilização da Largura de Banda gera plotagens gráficas dos relatórios de utilização e capacidade de largura de banda; são os seguintes:

- Todos os links WAN na rede corporativa.

- Filtradas pelos links WAN selecionados que foram escolhidos.

- Filtradas pelos links WAN que excederam o limite de capacidade.

- Filtradas pelos links WAN que têm subutilizado a largura de banda provisionada.

- Filtradas pelos links WAN que alcançaram níveis críticos (uma utilização de largura de banda superior a 90% da capacidade de largura de banda do link WAN).

- Filtradas pelo tipo de link WAN : links rede-site, links inter-regionais e links dentro de um site.

- Filtradas por região de rede.

#### <a name="applications"></a>Aplicativos

O Analisador de Utilização da Largura de Banda tem os dois aplicativos (ferramentas) abaixo:

- **WanLinkLogCollector. exe** esta ferramenta permite que o usuário insira as informações necessárias.

- **BandwidthUtilizationAnalyzer. xlsm** um relatório de software de planilha do Microsoft Excel é iniciado automaticamente por WanLinkLogCollector. exe. Este aplicativo permite ao usuário aplicar filtros ao relatório, como será mostrado posteriormente neste artigo.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fases de uso do Analisador de Utilização da Largura de Banda

Há duas fases ao usar o Analisador de Utilização da Largura de Banda:

- Coletar logs, o que é realizado ao usar o WanLinkLogCollector.exe.

- Personalizar relatórios, o que é realizado ao usar o BandwidthUtilizationAnalyzer.xlsm.

> [!IMPORTANT]
> Recomendamos que o BandwidthUtilizationAnalyzer.xlsm não seja iniciado manualmente pelos usuários finais.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Iniciando o Analisador de Utilização da Largura de Banda

Inicie o WanLinkLogCollector.exe no prompt de comando ou no Windows Explorer.

 **Usando o WanLinkLogCollector.exe**

Há três etapas para usar o WanLinkLogCollector.exe:

1. **Registrar a linha do tempo** Fornecer a linha do tempo para a qual o relatório precisa ser gerado

2. **Especificar os diretórios de arquivos** Fornecer informações de localização do arquivo

3. **Coletar os logs e iniciar o Visualizador de relatórios** Executar o comando para gerar o relatório

#### <a name="step-1---log-the-timeline"></a>Etapa 1 – Registrar a linha do tempo

O registro da linha do tempo permite que o usuário da ferramenta especifique o seguinte, conforme mostra a figura abaixo: 

1. **Data de início** Trata-se da data de início da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 1º de agosto de 2010.

2. **Data de término** Trata-se da data de término da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 30 de setembro de 2010.

     ![Datas de início e término na utilização da largura de banda A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Etapa 2 – Especificar os diretórios do arquivo

Os seguintes diretórios de arquivo devem ser especificados pelo usuário, como a seguir:

- **Local dos arquivos de log do servidor** O local da pasta onde os logs do servidor de política de largura de banda são armazenados. Geralmente, isso ocorre \<\> \\<em \AppServerFiles\PDP. de opções\>de FE do FE

- **Local de armazenamento de arquivo temporário** O local do arquivo temporário onde os arquivos intermediários são armazenados enquanto o relatório está sendo gerado.

![Diretórios de arquivos no anal de utilização da largura de banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> Forneça ao usuário da ferramenta acesso suficiente aos arquivos de logs do servidor e à pasta de repositório de arquivos temporários.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Etapa 3 – Coletar os logs e iniciar o visualizador de relatórios

Para coletar os logs e iniciar o visualizador de relatórios, clique em **Executar**, como mostrado abaixo. Esta etapa coleta os dados necessários.

![Coletando dados na Analy de utilização da largura de banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Se a validação da entrada for bem-sucedida, a mensagem abaixo será exibida.

![Registra a notificação coletada no utilitário de largura de banda](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Clique em **OK**. BandwidthUtilizationAnalyzer.xlsm será iniciado automaticamente. Siga as instrução na caixa de mensagens. Para obter mais detalhes, consulte **Uso do BandwidthUtilizationAnalyzer.xlsm ** na próxima seção.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Uso do BandwidthUtilizationAnalyzer.xlsm

1. Se o BandwidthUtilizationAnalyzer.xlsm tiver sido iniciado automaticamente, clique em **Atualizar**, como a seguir.

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Quando uma pasta de arquivos for aberta, selecione consolidated.csv na localização especificada na caixa de mensagens, como a seguir. A localização também é mostrada como **C:\Temp**.

     ![Abrir uma pasta no BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Clique em **Importar**.

4. A plotagem gráfica é gerada automaticamente. Ela será disponibilizada assim que o ponteiro de trabalho em segundo plano desaparecer.

     ![Aplicação de filtros no modo de exibição relatório.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Aplicando filtros ao visualizador de relatórios

Os filtros que podem ser aplicados ao visualizador de relatórios, conforme mostrado abaixo, são descritos da seguinte forma:

![Aplicação de filtros no modo de exibição relatório.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Nome** Filtrar por links WAN (o filtro se situa no lado direito do gráfico). O prefixo denota os tipos de links a seguir; consulte a caixa (azul) vertical:

   - **S Site ** O link WAN de um site da rede a uma região da rede

   - **IS Entre sites** O link WAN entre dois sites da rede

   - **R Inter-regional** O link WAN entre duas regiões da rede

2. **Limite excedido** Filtrar por links WAN cuja utilização de largura de banda seja superior à capacidade da largura de banda

3. **Níveis críticos** Filtrar por links WAN cuja utilização da largura de banda tenha alcançado 90% ou mais da capacidade da largura de banda

4. **Subutilizado** Filtrar por links WAN cuja utilização da largura de banda seja inferior a 25% da capacidade da largura de banda

5. **Tipo de link** Filtrar pelos seguintes tipos de links WAN:

   - 
            Tipo **Site da rede**

   - 
            Tipo **Entre sites**

   - 
            Tipo **Link inter-regional**

6. **Região** Filtrar pela região da rede

As imagens abaixo mostram os filtros descritos anteriormente.

Filtrar por **Nome**. Selecione a lista de links que precisam ser exibidos no gráfico.

![Filtragem por nome no BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filtrar por **Limite excedido**. Selecione **True** para impor o filtro.

![A filtragem excedeu o limite.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtrar por **Níveis críticos**. Selecione **True** para impor o filtro.

![Filtragem por níveis críticos.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtrar por **Subutilizado**. Selecione **True** para impor o filtro.

![Filtragem por subutilizado.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtrar por **Tipo de Link**. Selecione um ou mais tipos que precisam ser exibidos.

![Filtragem por tipo de link.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtrar por **Região**. Selecione uma lista de regiões cujos links precisam ser exibidos.

![Filtragem por região.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Requisitos

- .NET Framework 3.5

- Microsoft Excel 2010 ou Excel 2007

### <a name="summary"></a>Resumo

O Analisador de Utilização da Largura de Banda é usado para plotar a utilização da largura de banda de áudio do tráfego de UC na rede. Esta ferramenta pode ser usada também para relatar a utilização da largura de banda de vídeo na rede.

## <a name="call-parkometer"></a>Parquímetro de Chamada
<a name="callpark"> </a>

O Parquímetro de Chamada é um aplicativo de linha de comando que proporciona fácil acesso ao banco de dados da Órbita do Call Park.

### <a name="description"></a>Descrição

O Parquímetro de Chamada é uma ferramenta que rastreia as chamadas estacionadas atualmente. Ele também coleta estatísticas sobre as órbitas e o uso do CPS (Servidor de Estacionamento de Chamada). Essa ferramenta de linha de comando fornece acesso de leitura e gravação ao banco de dados do SQL Server do CPS órbita a partir de um computador local ou remotamente conectado.

Todas as opções são mutuamente exclusivas. A sintaxe da linha de comando é a seguinte:

- **-o** parâmetro — lista todos os intervalos de órbita configurados para este pool.

- **-n** parâmetro — lista todas as órbitas atualmente usadas neste pool. As informações são exibidas da seguinte forma:

  - URI (Uniform Resource Identifier) do SIP da chamada estacionada e do estacionador.

  - Nome do host do CPS onde a chamada está estacionada.

  - Carimbo de data/hora de quando a chamada foi estacionada.

- **-f** parâmetro — lista o número de órbitas livres no momento no pool.

- **-r \<n\> ** parâmetro — lista as \<chamadas\> n últimas chamadas estacionadas. As informações são exibidas da seguinte forma:

  - URI do SIP da chamada estacionada.

  - URI do SIP do estacionador da chamada.

  - Nome do host do CPS onde a chamada foi estacionada.

  - Carimbo de data/hora de quando a chamada foi recuperada ou ignorada.

- **-t\<n\> ** parâmetros-testes reservando uma órbita no banco de dados para mostrar a aleatoriedade dos números de órbita atribuídos.

### <a name="output"></a>Resultado

Dependendo dos parâmetros de entrada especificados em um prompt de comando, o Parquímetro de Chamada exibirá o seguinte resultado:

- Todos os intervalos de órbita configurados para este pool

- Chamadas estacionadas atualmente

- Número de órbitas livres (disponíveis)

- Chamadas estacionadas recentemente

- Órbitas reservadas para testes uniformes e valores de órbita aleatórios

### <a name="purpose"></a>Objetivo

O objetivo da ferramenta CPS é fornecer acesso de linha de comando ao banco de dados do CPS. O administrador pode visualizar o CPS usado e determinar o números de órbitas atribuídas a um pool.

### <a name="requirements"></a>Requisitos

Não haverá nenhum requisito se esta ferramenta for executada no mesmo computador que estiver executando o CPS. Se essa ferramenta for executada em um computador remoto, o banco de dados do SQL Server usado pelo Skype for Business Server 2015 deve ser configurado para permitir o acesso remoto. Chame Parkometer deve ser configurado com uma cadeia de conexão de banco de dados SQL Server para se conectar ao SQL Server do pool. Esta cadeia de conexão de banco de dados do SQL Server é definida no arquivo de configuração **parkometer. exe. config**. Ele deve ser colocado no mesmo diretório em que o parkometer. exe está localizado. O arquivo XML a seguir é um exemplo de um parkometer. exe. config. Os parâmetros que devem ser configurados são o nome de usuário (por exemplo, mydomain\Administrator), senha (por exemplo, mypassword) e nome do host (por exemplo, meuservidor).

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
   <add key="SQL" value="server=myserver\RTC;
database=cpsdyn;
User Id=mydomain\Administrator;
Password=mypassword.;
Integrated Security=false;"/>
  </appSettings>
</configuration>
```

### <a name="examples"></a>Exemplos

Intervalos de órbita implantados: o parâmetro-o lista todos os intervalos de órbitas que são configurados para esse pool conforme mostrado

![As faixas órbitas no Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Chamadas atualmente estacionadas: o parâmetro-n lista todas as órbitas atualmente usadas neste pool, conforme mostrado

![Chamadas estacionadas no momento no Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Número de órbitas livres: o parâmetro-f lista o número de órbitas livres atualmente no pool conforme mostrado

![Órbitas grátis no Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Chamadas estacionadas recentemente: o parâmetro \<-\> r n lista \<as\> n últimas chamadas estacionadas conforme mostrado

![Chamadas estacionadas recentemente no Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Testar reserva de órbita: os testes \<de\> parâmetro-t n reservando uma órbita no banco de dados conforme mostrado

![Teste as reservas em órbita na Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Resumo

O Parquímetro de Chamada é uma ferramenta de linha de comando que fornece informações detalhadas sobre o Servidor de Estacionamento de Chamada.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Descrição

DBAnalyze é uma ferramenta de linha de comando que ajuda os administradores a reunir relatórios de análise sobre os bancos de dados do Skype for Business Server 2015. O DBAnalyze tem os seguintes modos: diagnóstico, dados do usuário, conferência, MCUs e fragmentação de disco:

- **Modo de diagnóstico** Cria um relatório que inclui informações sobre tabelas (número de registros, fragmentação, tamanho de dados e tamanho de índice), arquivos de dados e log, o último tempo de backup, a distribuição de contatos entre servidores que executam o Microsoft Office Communications Server, o número médio de permissões, contatos, contêineres, assinaturas, publicações, pontos de extremidade por usuário, todos os usuários hospedados incorretamente, usuários que não podem ser roteados, o número médio de conferências organizadas por usuário, conferências programadas e a versão do banco de dados.

    > [!NOTE]
    > A execução do modo de diagnóstico pode afetar o desempenho do servidor.

- **Modo de dados do usuário** Relata os dados de contato, contêiner, assinatura, publicação, permissão e grupo de contatos para um usuário especificado ou para usuários que tenham esse usuário em suas listas de contatos e permissões. Este modo também relata dados resumidos de conferências que um usuário organizou ou para as quais foi convidado.

- **Modo de conferência** Relata dados detalhados para uma conferência específica, incluindo todos os detalhes de tempo de agendamento da conferência, a lista de convidados, a lista de tipos de mídia permitidos para a conferência, as MCUs ativas (unidades de controle multiponto), a lista de participantes ativa e o estado de sinalização de cada participante.

- **Decodificar ID da reunião** Decodifica uma ID de reunião PSTN (rede telefônica pública comutada) especificada pela opção **/pstnid** , mas não se conecta ao back-end para obter informações detalhadas.

- **Resolver conferência** Decodifica uma ID de reunião PSTN especificada pela opção **/pstnid** e exibe informações sobre a conferência indicada pela ID.

- **Modo MCUs** Informa a identificação, o tipo de mídia, a URL, o status de Heartbeat, a carga de conferência e a carga de participantes para cada MCU do pool.

- **Modo de fragmentação de disco** Exibe o status de fragmentação de todos os discos.

Esta ferramenta pode ser usada para diagnosticar diversos problemas ou para ajudar os administradores no planejamento da capacidade. Por exemplo, se a maioria dos usuários hospedados no servidor A escolher como contatos usuários hospedados no servidor B, o administrador poderá mover os usuários do servidor A para o servidor B para reduzir o tráfego entre servidores.

### <a name="output"></a>Resultado

Esta ferramenta emite relatórios predefinidos sobre o banco de dados do Skype for Business Server 2015. **Caminho**: %Arquivos de Programas%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>Objetivo

Para instalar o Dbanalyze. exe, copie-o para uma pasta local e execute a ferramenta. Para usar a ferramenta, execute o seguinte comando a partir da linha de comando. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`As descrições das opções de linha de comando são mostradas abaixo.

![Opções da linha de comando para Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Requisitos

 **Computador** O DBAnalyze pode ser executado apenas em um computador associado a um domínio que tenha o Skype for Business Server 2015 instalado.

 **Rede** O computador deve poder se conectar ao banco de dados back-end.

 **Software** Os componentes do software do Skype for Business Server 2015 devem ser instalados antes de executar o DBAnalyze.

 **Usuários** do A tabela a seguir mostra os administradores que têm as permissões necessárias para acessar bancos de dados do Skype for Business Server 2015.

![Tabela de permissões para Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Uma conta de administrador local é necessária para o modo **/report:disk**.

### <a name="examples"></a>Exemplos

Veja abaixo exemplos de comandos válidos do Dbanalyze.exe:

```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Resumo

O DBAnalyzer fornece aos administradores um rápido e fácil de analisar bancos de dados do Skype for Business Server 2015.

## <a name="import-storage-service-data"></a>Importar Dados do Serviço de Armazenamento
<a name="Issd"> </a>

A ferramenta ImportStorageServiceData do kit de recursos permite reimportar os dados da fila e do ponto de extremidade que foram exportados do Serviço de Armazenamento (LYSS) para o Serviço de Armazenamento.

### <a name="description"></a>Descrição

A exportação dos dados do Serviço de Armazenamento pode ter sido automática (periodicamente) com base no status do item da fila ou no tamanho do banco de dados. Ela pode ter ocorrido devido à invocação manual do cmdlet de failover do pool ou do cmdlet StorageServiceFullFlush (invocado pelo cmdlet de failover do pool). Lembre-se de que os dados não devem ser importados novamente se qualquer um dos tamanhos de banco de dados do serviço de armazenamento (LYSS) no front-ends estiver acima do nível normal, porque isso provavelmente apenas fará com que mais dados sejam exportados. Além disso, quaisquer problemas que possam ter contribuído com erros que fizeram com que a fila do serviço de armazenamento cresça devem primeiro ser resolvidos (por exemplo, erros de ponto de extremidade do Exchange, problemas de rede ou outros problemas).

 **Cenário 1:** durante o failover do pool, os arquivos poderão ser liberados do serviço de armazenamento de cada front-end. Após a conclusão do failover, a ferramenta deverá ser executada para reimportar os dados.

 **Cenário 2:** os dados estão sendo exportados de maneira automática diariamente ou em resposta ao banco de dados de Serviço de Armazenamento ter excedido determinados limites de tamanho (por exemplo, 60%, 80%, 90%, capacidade total). Esses dados exportados automaticamente devem ser reimportados regularmente pelo administrador. Na situação acima, se o pacote do SCOM que está sendo monitorado não for implantado, há eventos para o serviço de armazenamento do Skype for Business Server relacionados a dados que estão sendo liberados do serviço de armazenamento. As IDs de evento são: 32075 (operação de exportação completa iniciada), 32076 (exportação completa concluída), 32082 (exportação de nível de manutenção iniciada), 32083 (exportação de nível de manutenção concluída), 32089 (exportação ocorrida devido ao preenchimento do banco de dados). Observe que essas IDs de evento correspondem à versão do RTM. Quando um administrador vê esses eventos, isso significa que há arquivos que foram liberados. Esses dados devem ser importados rotineiramente usando essa ferramenta, por exemplo, uma vez por semana.

Para o lançamento do serviço online, se o pacote do SCOM Pack para o Skype for Business Server for implantado, há novos alertas que podem ser gerados para solicitar que o administrador reimporte os dados liberados de volta para o serviço de armazenamento. Haverá um evento correspondente no log de eventos no servidor front-end que disparou o alerta. O evento dará uma descrição do caminho pai sob o qual se encontram os arquivos de dados exportados, bem como a quantidade de arquivos existentes que cumpre os critérios do alerta. O critério de alerta é de que há X ou mais arquivos sob o caminho pai específico que tem pelo menos Y dias (em que X e Y são predefinidos dentro do StorageService, mas podem ser substituídos, alterando o arquivo APPCONFIG). Dois exemplos de eventos que podem disparar o alerta de integridade são mostrados abaixo, com a diferença sendo seu respectivo caminho pai. Uma possibilidade está no compartilhamento de arquivos do serviço Web, enquanto a outra possibilidade está no diretório Dados de Aplicativos local de cada front-end (por exemplo c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService). O administrador executará essa ferramenta do reskit.

Essa ferramenta aumentará a carga de CPU e de E/S no front-end em que estiver sendo executada e também em outros front-ends se os dados não pertencerem ao front-end no qual a ferramenta estiver sendo executada. Recomendamos executar essa ferramenta quando os front-ends não estiverem sob uma carga de E/S e CPU pesada, por exemplo, fora dos horários de pico. Em segundo lugar, essa ferramenta leva de 2 a 3 minutos para importar um arquivo de dados. Lembre-se disso ao estimar por quanto tempo a ferramenta será executada. O arquivo de log detalhado gerado pela ferramenta será exibido por padrão no Repositório de Arquivos. Exclua-o se não houver nenhum erro relatado, pois o arquivo de log pode ter muitos megabytes.

![Exemplos de eventos do log de eventos do servidor de armazenamento.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Requisitos

Instale as ferramentas do kit de recursos do Skype for Business Server 2015. A ferramenta é executada em máquinas Unidas a domínios em que o Shell de gerenciamento do Skype for Business Server e do Skype for Business Server está instalado. A ferramenta usa um cmdlet do Shell de gerenciamento para identificar todos os servidores de front-end do pool. Em segundo lugar, a ferramenta deve ser executada em um computador no pool em que o banco de dados do **RtcLocal** está instalado. Esse banco de dados é usado pela ferramenta para recuperar a localização do compartilhamento de arquivo WEBSERVICE para o pool. Além disso, antes de usar a ferramenta, cada servidor front-end deve primeiro habilitar a comunicação remota do Windows PowerShell usando **Enable-PSRemoting** em cada servidor front-end, bem como a máquina na qual a ferramenta é executada. Caso contrário, os comandos remotos do Windows PowerShell dessa ferramenta falharão. A comunicação remota do Windows PowerShell pode ser desativada em todos os servidores de front-end do pool após o término. Por fim, a conta ou a credencial que invocar a ferramenta deve ter permissão de leitura/gravação para o compartilhamento de arquivo WebService para o pool em que ele está executando essa ferramenta. Caso contrário, a ferramenta irá falhar com erros de permissão de e/s.

> [!NOTE]
> No Windows Server 2012, a comunicação remota do Windows PowerShell está habilitada por padrão, mas não no sistema operacional Windows Server 2008.

### <a name="examples"></a>Exemplos

```
>  C:\StorageService>ImportStorageServiceData.exe
Description:
This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
Additional Options:
-Verbose                    : Turn verbose output on.

-StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )

-FileSharePath              : Import only all data from just under the UNC path specified.

ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
Using NetNamedPipeBinding...
OnTopologyChanged Event received
Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService

Front Ends:
server.vdomain.com
server2.vdomain.com
server1.vdomain.com
server3.vdomain.com
Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
# Files found: 8
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
Items deserialized: 20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
3832e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
86684d3832e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
ain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
287dd6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
b46a42287dd6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
d251e6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
e08a15d251e6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
17c220__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
949ff817c220__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
6d5317__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
749be66d5317__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
86b565__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
657eda86b565__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
vices-1\StorageService
Importing files for: server.vdomain.com
No files founds.
Importing files for: server2.vdomain.com
No files founds.
Importing files for: server1.vdomain.com
No files founds.
Importing files for: server3.vdomain.com
No files founds.
Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
Log20120910_1609SS
Tool has finished execution.
>  C:\StorageService>
```

## <a name="lcssync"></a>LCSSync
<a name="LCSSync"> </a>

A ferramenta LCSSync ajuda a implantar o software de comunicação do Skype for Business Server 2015 em um ambiente de várias florestas. Essa ferramenta é usada para sincronizar usuários e grupos de florestas de usuários diferentes como um objeto de contato dos serviços de domínio Active Directory para uma floresta central na qual o Skype for Business Server 2015 está instalado.

### <a name="description"></a>Descrição

 O LCSSync usa os objetos de contato sincronizados dos serviços de domínio Active Directory na floresta central para permitir aos usuários do Skype for Business Server. Para fornecer logon único, a conta de usuário principal deve ser mapeada para o objeto de contato dos serviços de domínio Active Directory na floresta central do Skype for Business Server 2015. Essa ferramenta ajuda a realizar esse mapeamento. Ela também fornece modelos para a criação de Agentes de Gerenciamento no Microsoft Identity Integration Server.

### <a name="summary"></a>Resumo

A ferramenta LCSSync ajuda a implantar o Skype for Business Server 2015 em um ambiente de várias florestas.

## <a name="lookup-user-console"></a>Pesquisar no Console de Usuários
<a name="LUC"> </a>

A ferramenta LookupUserConsole exibe informações de roteamento internas do Skype for Business Server sobre usuários específicos. Essas informações poderão ser úteis para o suporte pessoal da Microsoft no diagnóstico de problemas de implantação e roteamento.

### <a name="description"></a>Descrição

 Executar o LookupUserConsole. exe abrirá um prompt de comando que aceita endereços SIP e tentará exibir as informações de roteamento internas do Skype for Business Server relacionadas a ele. Digite **exit** para sair da ferramenta LookupUserConsole.

### <a name="requirements"></a>Requisitos

Instale o kit de recursos do Skype for Business Server 2015. A ferramenta é executada em máquinas Unidas pelo domínio onde o Skype for Business Server está instalado.

### <a name="examples"></a>Exemplos

C:\Program Files\Skype for Business Server 2015 \ reskit\>LookupUserConsole. exe

```
> sip:john.doe@vdomain.com

  Execution time (ms):                            171.094
  Exeuction result:                               Success
  SIP URI:                                        sip:john.doe@vdomain.com
  User info:
    SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
    Grouping ID:                                  00000000-0000-0000-0000-...
    Line URI:                                     <null>
    Policy assignment:                            TenantId={00000000--0000-000....
    SIP enabled:                                  True
    UC enabled:                                   False
    Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
    Active cluster:                               pool0.vdomain.com
    Backup registrar cluster:                     <null>
    Deployment location:                          <null>
    Home Front-End FQDN:                          SERVER.vdomain.com
    Primary Registrar cluster:                    pool0.vdomain.com
    Remote Director external SIP FQDN:            <null>
    Remote Director internal SIP FQDN:            <null>
    Remote Director Web FQDN:                     <null>
    Routing group ID:                             4501e04e-ae48-5605-9346...
    Service tag ID:                               1266953005
    User Front-End resolved:                      True
    User in local forest:                         True
    User in remote forest:                        False
    User in split domain:                         False
    User-Services cluster:                        pool0.vdomain.com

> sip:nouser@vdomain.com

  Execution time (ms):                            948.7574
  Exeuction result:                               UserDoesNotExist

> exit
```

## <a name="msturnping"></a>MsTurnPing
<a name="MsTurnPing"> </a>

A ferramenta MSTurnPing permite que um administrador do software de comunicação do Skype for Business Server 2015 Verifique o status dos servidores que executam a borda de áudio/vídeo e os serviços de autenticação de áudio/vídeo, bem como os servidores que estão executando os serviços de política de largura de banda na topologia.

### <a name="description"></a>Descrição

A ferramenta MSTurnPing permite que um administrador do software de comunicação do Skype for Business Server 2015 Verifique o status dos servidores que executam a borda de áudio/vídeo e os serviços de autenticação de áudio/vídeo, bem como os servidores que estão executando os serviços de política de largura de banda na topologia.

A ferramenta permite ao administrador realizar os seguintes testes:

1. Teste do Servidor de Borda A/V: a ferramenta realiza testes em todos os Servidores de Borda A/V na topologia fazendo o seguinte:

   - Verificar se o serviço de autenticação de áudio/vídeo do Skype for Business Server foi iniciado e pode emitir credenciais adequadas.

   - Verificar se o serviço de borda de áudio/vídeo do Skype for Business Server foi iniciado e pode alocar os recursos na borda externa com êxito.

2. Teste do Serviço da Política de Largura de Banda: a ferramenta realiza testes em todos os servidores que estejam executando os Serviços da Política de Largura de Banda na topologia fazendo o seguinte:

   - Verificar se o serviço de política de largura de banda (autenticação) do Skype for Business Server foi iniciado e pode emitir credenciais adequadas.

   - Verificando se o serviço de política de largura de banda do Skype for Business Server (básico) foi iniciado e pode executar a verificação de largura de banda com êxito.

Essa ferramenta deve ser executada em um computador que faça parte da topologia e tenha o repositório local instalado. 

### <a name="output"></a>Resultado

Essa ferramenta gera os resultados de cada uma das operações.

- Quando o teste **AudioVideoEdgeServer ** é realizado, a ferramenta gera o seguinte:

  - Os resultados do teste dos computadores que fornecem o serviço de autenticação de áudio/vídeo do Skype for Business Server 2015 na topologia

  - Os resultados do teste dos computadores que fornecem o serviço de borda de áudio/vídeo do Skype for Business Server 2015 na topologia

- Quando o teste **BandwidthPolicyServer** é realizado, a ferramenta gera o seguinte:

  - Os resultados do teste dos computadores que fornecem o serviço de política de largura de banda (autenticação) do Skype for Business Server 2015 na topologia

  - Os resultados do teste dos computadores que fornecem o serviço de política de largura de banda (básico) do Skype for Business Server 2015 na topologia

### <a name="requirements"></a>Requisitos

- Essa ferramenta deve ser executada em um computador que faça parte da topologia e tenha o repositório local instalado.

- A ferramenta deve ser executada por um administrador que tenha acesso ao repositório local.

### <a name="examples"></a>Exemplos

Veja a seguir um exemplo de entrada de dados da ferramenta.

```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para os administradores do Skype for Business Server 2015 que desejam verificar o status dos servidores que estão executando o áudio/vídeo e os serviços de política de largura de banda.

## <a name="network-configuration-viewer"></a>Visualizador da Configuração de Rede
<a name="NCV"> </a>

O Visualizador de configuração de rede pode ser usado pelos administradores do software de comunicações do Skype for Business Server 2015 para exibir a topologia de rede do controle de admissão de chamadas (CAC) para uma empresa que é fornecida para permitir sessões de comunicação em tempo real, como chamadas de voz ou com vídeo com base na capacidade de largura de banda especificada. Os administradores do Skype for Business Server 2015 definem políticas do CAC, que são impostas pelos serviços de política de largura de banda que são instalados com o Skype for Business Server 2015.

### <a name="description"></a>Descrição

O Visualizador da Configuração de Rede (NetworkConfigurationViewer.exe) permite aos administradores executar as seguintes tarefas:

- Carregar e exibir a topologia de rede do CAC a partir de uma implantação do Skype for Business Server 2015 em um formato gráfico.

- Carregar e exibir a topologia de rede do CAC de um arquivo de log do Servidor da Política de Largura de Banda em um formato gráfico.

- Salvar e armazenar no disco a topologia de rede do CAC no formato XML.

- Salvar e armazenar o diagrama da topologia de rede do CAC no formato JPG ou BMP.

- Exibir os dados de configuração da topologia de rede do CAC.

- Exibir a topologia de rede do CAC em modo de exibição de árvore.

- Definir conectores personalizados para os links da topologia de rede do CAC (por exemplo, links de site para região, região para região e site para site).

- Exibir as informações do site de topologia de rede do CAC, informações da região e links de rede e políticas de largura de banda provisionadas.

### <a name="purpose"></a>Objetivo

Exibir os links de topologia de rede do CAC da empresa em uma interface gráfica.

### <a name="examples"></a>Exemplos

 **Carregar e exibir a topologia de rede do CAC a partir de uma implantação do Skype for Business server 2015 em um formato gráfico**: Skype for business Server 2015 os administradores podem carregar e exibir a configuração de topologia de rede do CAC em qualquer computador com o Skype for business Server 2015, usando a opção **baixar a configuração de rede** , conforme mostrado na figura a seguir. A ferramenta não fará o download ou exibirá essa configuração quando implantada em um computador que não tenha conectividade com o repositório de configuração do Skype for Business Server 2015.

![Baixando a configuração de rede.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Carregar e exibir a topologia de rede do CAC de um arquivo de log do servidor de políticas de largura de banda em um formato gráfico:** Servidores de política de largura de banda do Skype for Business Server 2015 salve a topologia de rede do CAC como parte do mecanismo de registro em log no local de compartilhamento de arquivos do Skype for Business Server 2015. Os administradores do Skype for Business Server 2015 podem exibir esse arquivo em um formato gráfico usando a opção **abrir a configuração de rede** , como mostrado a seguir.

![Abrir um arquivo de log do servidor de políticas de largura de banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Salvar e armazenar a topologia de rede do CAC em um formato XML no disco: os administradores do Skype for Business Server 2015 podem salvar o arquivo de configuração de topologia de rede do CAC em um formato XML usando a opção **salvar uma cópia da configuração de rede** , conforme mostrado a seguir. O arquivo de configuração salvo pode ser usado offline para fins de exibição gráfica.

![Salvando a configuração de rede como um arquivo XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Salvar e armazenar o diagrama de topologia de rede do CAC no formato JPG ou BMP: os administradores do Skype for Business Server 2015 podem salvar a configuração de topologia de rede do CAC em um formato gráfico (formatos de arquivo JPG e BMP) usando a opção **salvar diagrama de configuração de rede como imagem** , conforme mostrado a seguir.

![Salvando a configuração de rede como uma imagem.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Exibir dados de configuração de topologia de rede do CAC:</strong> Os administradores do Skype for Business Server 2015 podem exibir dados de configuração de rede relacionados, como regiões de rede, sites de rede, perfis de largura de banda e endereços IP de sub-rede de sites em um formato de texto usando a opção Exibir dados de configuração de rede, conforme mostrado a seguir.

![Exibir dados de configuração de rede.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Exiba a topologia de rede do CAC em um estilo de exibição de árvore:** Os administradores do Skype for Business Server 2015 podem exibir dados de configuração de rede relacionados em um estilo de exibição de árvore gráfica usando o painel de controle no lado esquerdo da janela da ferramenta, como mostrado abaixo.

![Exibir dados de configuração de rede em um modo de exibição de árvore.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Definir conectores personalizados para links de topologia de rede do CAC (como links de site para região, região para região e links entre sites):** Os administradores do Skype for Business Server 2015 podem definir conectores gráficos personalizados para o WAN links de configuração de rede do CAC usando a opção configurações, conforme mostrado a seguir. Isso ajuda a diferenciar entre os vários tipos de links de rede provisionados na configuração da rede.

![Tools](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Exibir informações do site de topologia de rede do CAC, informações de região e políticas de largura de banda provisionadas:** Os administradores do Skype for Business Server 2015 podem exibir informações de região de rede do CAC, informações do site e informações de provisionamento de largura de banda do CAC relacionadas usando as opções mostradas abaixo. Por exemplo, clique em **Informações** em uma região da rede ou objeto do site da rede.

![Definir conectores personalizados para a sua rede.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para os administradores do Skype for Business Server 2015 que desejam exibir a topologia de rede do CAC para a implantação em um formato gráfico.

## <a name="response-group-agent-live"></a>Agente do Grupo de Resposta em Tempo Real
<a name="RGAL"> </a>

O aplicativo Grupo de Resposta proporciona aos agentes a capacidade de acessar informações úteis em tempo real usando o serviço Web interno. Infelizmente, nenhuma exibição gráfica desses dados está disponível fora do aplicativo. A ferramenta agente do grupo de resposta do Live Resource Kit resolve esse problema fornecendo uma maneira simples e gráfica de acessar essas informações, aprimoradas com informações de software de comunicação do Skype for Business em tempo real, como a presença de outros agentes.

### <a name="description"></a>Descrição

O Agente do Grupo de Resposta em Tempo Real é um aplicativo do Windows que fornece a funcionalidade de entrar e sair e algumas informações em tempo real (como membros do grupo e número atual de chamadas) a agentes do Grupo de Resposta. Ele deve ser uma versão aprimorada da página de grupos de agente (acessível pelo Skype for Business.

### <a name="purpose"></a>Objetivo

O aplicativo Grupo de Resposta enfileira as chamadas recebidas e, em seguida, as encaminha para os grupos de agentes. Para tomar decisões conscientes sobre quais chamadas devem ser atendidas, os agentes podem acessar informações em tempo real sobre os grupos de agentes, como quais outros agentes estão disponíveis e quantas chamadas estão em espera em cada fila. Essas informações, inicialmente acessíveis somente por meio do serviço de Grupo de Resposta, são disponibilizadas de forma intuitiva pelo Agente do Grupo de Resposta em Tempo Real.

#### <a name="features"></a>Recursos

A ferramenta de tempo de agente de grupo de resposta é criada no serviço de grupo de resposta e no SDK do Skype for Business Server 2015. Ela fornece aos agentes do Grupo de Resposta as informações e os recursos disponíveis no serviço de Grupo de Resposta (como membros do grupo, presença de outros agentes e número de chamadas em espera).

A figura abaixo ilustra a interface principal do Agente do Grupo de Resposta em Tempo Real.

![A ferramenta de tempo de agente do grupo de resposta.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Os seguintes três recursos principais estão disponíveis para os agentes do Agente do Grupo de Resposta em Tempo Real:

- **Entrada/saída:** Ao contrário da página de grupos de agente (acessível pelo Skype for Business Server 2015), o agente de resposta em tempo real permite que somente os agentes entrem em todos os grupos de agente ao mesmo tempo. Este aplicativo fornece três maneiras rápidas para os agentes entrarem ou sairem:

  - Clicar nos botões Entrar/sair (verde e vermelho) no aplicativo.

  - Clicar com o botão direito do mouse no ícone de bandeja do sistema e selecionar entrar ou sair.

  - Usar os atalhos do teclado configuráveis.

- **Associação a um grupo:** Quando um grupo de agente é selecionado, o agente do grupo de resposta Live exibe a lista de agentes neste grupo no painel direito. Se o Skype for Business Server 2015 estiver em execução no mesmo computador que este aplicativo, as informações de presença e o cartão de visita serão exibidos no agente do grupo de resposta ao vivo. Os agentes podem enviar uma mensagem instantânea ou ligar para outros agentes diretamente.

- **Estatísticas em tempo real:** o Agente do Grupo de Resposta em Tempo Real fornece estatísticas em tempo real de todos os grupos de agentes. A frequência de atualização é de um minuto. Quando uma chamada é atendida por um Grupo de Resposta, um indicador visual é adicionado ao lado do nome do grupo com o número atual de chamadas em fila. Pausar o ponteiro sobre um grupo também exibe o tempo de espera mais longo.

### <a name="requirements"></a>Requisitos

O Agente do Grupo de Resposta em Tempo Real requer o .NET Framework 4.0. Além disso, para tirar proveito dos recursos de presença e cartão de contato, o Skype for Business deve ser instalado localmente (e em execução).

#### <a name="configuration"></a>Configuração

O Agente do Grupo de Resposta em Tempo Real pode ser personalizado de acordo com as preferências individuais usando a caixa de diálogo Opções no aplicativo. Além disso, o administrador pode definir o endereço de host padrão editando diretamente a propriedade defaultHostAddress do arquivo RGAgentLive.exe.config.

A figura abaixo ilustra a caixa de diálogo Opções que os agentes podem usar para configurar as teclas de atalho e o endereço de host. Essa caixa de diálogo é acessada clicando no botão Opções no canto superior direito da interface principal.

![A caixa de diálogo opções de agente do grupo de resposta em tempo real.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

As três configurações diferentes a seguir podem ser personalizadas na configuração do Agente do Grupo de Resposta em Tempo Real:

- Endereço do host: geralmente é o FQDN do pool da Web pertencente ao pool primário do agente. O endereço de serviço exato do Grupo de Resposta é automaticamente derivado em segundo plano dessa informação (anexado no caminho à direita depois do host).

- Atalhos: os atalhos exatos para entrar/sair podem ser personalizados. A única limitação é que ambos os atalhos devem conter a tecla "logotipo do Windows" (além de pelo menos outra chave).

- Iniciar com o Windows: o aplicativo pode ser configurado para ser iniciado automaticamente com o Windows.

### <a name="examples"></a>Exemplos

A figura abaixo ilustra como chamar ou enviar uma mensagem instantânea para outro agente clicando com o botão direito do mouse no contato no painel à direita.

![Fazer uma chamada ou enviar uma mensagem instantânea.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

A figura abaixo ilustra como o Agente do Grupo de Resposta em Tempo Real exibe o número atual de chamadas na fila e o tempo de espera mais longo entre todas as chamadas de entrada.

![Exibir informações da fila.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Resumo

Ações rápidas de entrada e saída, associação a um grupo e estatísticas básicas em tempo real são recursos interessantes do Agente do Grupo de Resposta que estão disponíveis apenas fora do aplicativo do serviço de Grupo de Resposta. Com a ferramenta Response Group Agent Live Resource Kit, os administradores do Skype for Business Server 2015 podem oferecer seus agentes com um aplicativo do Windows que permite que eles executem tarefas de maneira mais rápida e gráfica.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (ativação de recurso de extensão secundária) é uma ferramenta de linha de comando que habilita os administradores do software de comunicações do Skype for Business Server 2015 e os agentes de assistência técnica para configurar o toque, o encaminhamento de chamadas, o toque simultâneo configurações de chamada de equipe e retirada de chamadas em grupo em nome de um usuário do Skype for Business Server 2015. A ferramenta também permite que os administradores consultem as configurações de direcionamento de chamadas publicadas para um usuário específico. A ferramenta SEFAUtil permite que o administrador habilite/desabilite/modifique o encaminhamento de chamadas ou toque simultaneamente em nome do usuário. O administrador pode especificar o destino (na forma de um URI SIP) ou usar um destino que já foi publicado pelo usuário. Essa ferramenta também permite que os administradores adicionem ou removam representantes ou membros do grupo de chamada de equipe em nome do usuário. Essa ferramenta foi criada com o Microsoft Unified Communications Managed API (UCMA) 3,0 e requer que os administradores criem um aplicativo confiável no repositório de gerenciamento central para SEFAUtil.

SEFAUtil (ativação de recurso de extensão secundária) permite que os administradores do Skype for Business Server 2015 e do helpdesk configurem o toque, o encaminhamento de chamadas, o toque simultâneo, as configurações de chamada de equipe e o recebimento de chamadas em grupo em nome de um Skype para o usuário do Business Server 2015. Essa ferramenta também permite aos administradores consultar as configurações de roteamento de chamadas publicadas para determinado usuário.

### <a name="description"></a>Descrição

A versão atual de SEFAUtil é apenas uma ferramenta de linha de comando; não há nenhum suporte para interface gráfica do usuário. Esta ferramenta se baseia na API gerenciada de comunicação unificada da Microsoft (UCMA) 3,0. Os recursos dessa ferramenta permitem a administradores e agentes de assistência técnica realizar as seguintes ações:

- Exibir todas as configurações de roteamento de chamadas de um usuário (inclui encaminhamento de chamadas, delegação, toque simultâneo, chamada de equipe e recebimento de chamada em grupo).

- Habilitar/desabilitar/modificar a configuração de encaminhamento de chamadas (inclui temporizador sem resposta e de destino).

- Habilitar/desabilitar/modificar configurações imediatas de encaminhamento de chamadas.

- Habilitar/desabilitar/modificar configurações de delegação.

- Habilitar/desabilitar/modificar configurações do grupo de chamada de equipe.

    > [!NOTE]
    > Novo na ferramenta SEFAUtil do Skype for Business Server 2015

- Habilitar/desabilitar/modificar configurações de toque simultâneo (inclui destino).

    > [!NOTE]
    > Novo na ferramenta SEFAUtil do Skype for Business Server 2015

- Habilitar/desabilitar/modificar configurações de recebimento de chamada em grupo.

    > [!CAUTION]
    > Novo na ferramenta SEFAUtil do Skype for Business Server 2015

Esta ferramenta apresenta as seguintes limitações:

- Com suporte somente para usuários hospedados em um pool do Skype for Business Server

- Não há suporte para edição em massa de configurações de roteamento de chamadas para diversos usuários.

### <a name="output"></a>Resultado

A versão atual desta ferramenta fornece resultados apenas na janela Prompt de Comando. Para ver detalhes, consulte a seção Exemplos mais adiante neste documento.

### <a name="purpose"></a>Objetivo

Veja a seguir alguns dos principais cenários onde esta ferramenta pode ser usada:

- Bob é um executivo e mudou para a telefonia do Skype for Business Server. Ele já tem delegação em seu sistema PBX existente. Como parte da mudança para o Skype for Business Server 2015, o administrador é capaz de configurar o roteamento de Bob para refletir sua configuração de delegação já existente.

- Brenda está viajando e aguarda uma chamada importante de um de seus clientes. No entanto, ela está em hotel e não tem acesso a computador. Ela liga para a assistência técnica e solicita que encaminhem para seu número de celular todas as chamadas feitas para seu número comercial. O pessoal da assistência técnica pode fazer a configuração em seu nome.

- As chamadas de Joe para o seu número de trabalho estão indo ao seu correio de voz móvel sempre que ele está no trabalho; no entanto, as coisas parecem estar funcionando corretamente na maioria dos outros locais. O técnico do helpdesk pode exibir a configuração de roteamento de Joe e descobre que Joe tem o toque simultâneo configurado para o seu celular. O técnico pede a Joe sobre a cobertura do celular em seu escritório e é capaz de determinar que a regra de toque simultâneo é o que está fazendo com que as chamadas vá para o correio de voz móvel de Joe quando sua cobertura de rede for ruim.

- Mike é um novo funcionário da Contoso e ele está participando de uma nova equipe na qual todos os membros são configurados para chamada de equipe, quando habilitados para o Skype for Business Server 2015, o administrador pode definir suas configurações de grupo de chamada de equipe para incluir todos os novos membros da equipe , além disso, o administrador adiciona Mike como um membro do grupo de chamada de equipe para cada um dos membros da equipe.

- Uma prática de atendimento ao cliente no departamento de recursos humanos da Contoso é fornecer um atendimento pessoal a todos os chamadores desde a primeira chamada. Como todos os membros do departamento sentam-se muito próximos uns dos outros, ter todos os telefones tocando ao mesmo tempo com a chamada de equipe é desconfortável para a equipe. Para fornecer o melhor serviço sem interromper os membros da equipe, o administrador do Skype for Business Server 2015 aproveita a funcionalidade de recebimento de chamadas em grupo. O administrador adiciona todos os membros do departamento a um grupo de recebimento e informa o número do grupo de recebimento ao departamento. Quando Clara está fora de sua mesa, Vinícius percebe que o telefone dela está tocando e atende à chamada em sua própria mesa.

### <a name="requirements"></a>Requisitos

A ferramenta SEFAUtil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis. O UCMA 3.0 deve ser instalado nesse computador. Para executar a ferramenta, um novo aplicativo confiável com a ID do aplicativo SEFAUtil deve ser criado nesse pool.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Criando um novo aplicativo confiável para a ferramenta SEFAUtil

1. A ferramenta SEFAUTil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis. Se necessário, adicionar um pool como um novo pool de aplicativos confiável pode ser feito por meio do Shell de gerenciamento do Skype for Business Server com o seguinte cmdlet:

   ```PowerShell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > O UCMA 3.0 deve ser instalado em qualquer computador que será usado para executar a ferramenta SEFAUtil.

2. Um aplicativo confiável precisa ser definido na topologia para a ferramenta SEFAUtil. Para definir SEFAUtil como um novo aplicativo confiável, use o Shell de gerenciamento do Skype for Business Server e execute o seguinte cmdlet:

   ```PowerShell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > Uma porta diferente pode ser usada, se necessário.
    
    > [!NOTE]
    > FQDN do pool: o FQDN do servidor ou pool que hospedará o aplicativo SEFAUtil (geralmente, um servidor front-end do Skype for Business > ou o pool).
    > FQDN do registrador de pool: o FQDN do servidor de front-end do Skype for Business ou pool associado a este pool de aplicativos.
    > Site de pool: a ID do site na qual esse pool é hospedado.

3. As alterações de topologia precisam ser habilitadas. Habilitar as alterações de topologia pode ser feito por meio do Shell de gerenciamento do Skype for Business Server executando o seguinte cmdlet:

   ```PowerShell
   Enable-CsToplogy
   ```

4. Se necessário, instale as ferramentas do kit de recursos do Skype for Business Server 2015 no servidor que serão usadas para executar a ferramenta SEFAUtil (o servidor deve fazer parte de um pool de aplicativos confiável).

5. Verifique se o SEFAUtil está sendo executado corretamente. Para fazer isso, execute a ferramenta em um prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamadas de um usuário na implantação. Por padrão, a ferramenta estará localizada em: ". ..\Program Files\Skype for Business Server 2015 \ reskit". Para exibir as configurações de encaminhamento de chamadas de um usuário, use o seguinte comando:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    As configurações de encaminhamento de chamadas do usuário devem ser exibidas.

#### <a name="group-call-pickup"></a>Recebimento de Chamadas em Grupo

A retirada de chamadas em grupo requer configuração adicional no Skype for Business Server 2015 para que o recurso seja totalmente habilitado. Antes de atribuir grupos de atendimento aos usuários, consulte a documentação do produto de Recebimento de Chamadas em Grupo para ver as etapas de planejamento e implantação desse recurso.

### <a name="examples"></a>Exemplos

#### <a name="display-current-call-handling-settings"></a>Exibir configurações atuais de administração de chamadas

O comando a seguir exibe a administração de chamadas do usuário.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> Este exemplo usa a opção **/Server** para especificar o Skype for Business Server ao qual se conectar.

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Definir destino de encaminhamento de chamadas/destino sem resposta

Este exemplo define o encaminhamento de chamadas/destino sem resposta e o atraso de toque. Aqui, a opção/Server não é fornecida; O SEFAUtil tenta descobrir a descoberta automática do Skype for Business Server 2015.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>Habilitar o encaminhamento de chamadas imediatamente

Este exemplo habilita imediatamente o encaminhamento de chamadas para outro usuário.

```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>Desabilitar o encaminhamento de chamadas imediatamente

Este exemplo desabilita imediatamente o encaminhamento de chamadas.

```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Adicionar um usuário como um representante e configurar o toque simultâneo dos representantes

Este exemplo adiciona um usuário como um representante e configura o toque simultâneo dos representantes:

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Alterar regra de toque simultâneo dos representantes

Este exemplo altera a regra de toque simultâneo que foi definida no exemplo anterior à regra de toque atrasado.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **Resultado**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>Remover o representante

Este exemplo remove o representante.

> [!NOTE]
> Quando o ultimo representante é removido, o toque delegado é desabilitado automaticamente.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Adicionar um representante e configurar a regra de encaminhamento de chamadas para representantes

Este exemplo adiciona um representante e configura a regra de encaminhamento de chamadas para representantes.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Habilitar toque simultâneo e definir um número de destino

Este exemplo habilita o toque simultâneo e define o número de destino do toque simultâneo.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Para alterar o número de destino do toque simultâneo de um usuário cujo toque simultâneo já está habilitado, mantenha o comando com a opção /enablesimulring; caso contrário, o número de destino não será alterado.

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Desabilitar toque simultâneo

Este exemplo desabilita o toque simultâneo.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Adicionar um membro da equipe para chamada de equipe e configurar toque simultâneo para o grupo de membros da chamada de equipe

Este exemplo adiciona um membro ao grupo de chamada de equipe de um usuário e habilita o toque simultâneo para o grupo de chamada de equipe.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Adicionar um membro ao grupo de chamada de equipe de um usuário mudará automaticamente as configurações de toque simultâneo dos usuários para o toque simultâneo do grupo de chamada de equipe desse membro.

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Remover um membro do grupo de chamada de equipe

Este exemplo remove um membro da equipe do grupo de chamada de equipe de um usuário.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Se o membro a ser removido for o único membro do grupo de chamada de equipe, o toque simultâneo para o grupo de chamada de equipe será automaticamente desabilitado.

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Definir toque atrasado para o grupo de chamada de equipe

Este exemplo altera o toque atrasado para a configuração de hora do grupo de chamada de equipe.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>Habilitar chamada de equipe

Isso habilita a chamada de equipe de determinado usuário.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Se o grupo de chamada de equipe do usuário não tiver membros, a chamada de equipe não será habilitada.

 **Saída**

#### <a name="disable-team-call"></a>Desabilitar chamada de equipe

Este exemplo desabilita a chamada de equipe de um determinado usuário.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Habilitar recebimento de chamadas em grupo e atribuir um grupo de recebimento a um usuário

Este exemplo atribui um grupo de recebimento a um usuário e habilita o Recebimento de Chamadas em Grupo.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **Saída**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>Desabilitar recebimento de chamadas em grupo

Este exemplo desabilita o Recebimento de Chamadas em Grupo de determinado usuário.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Ao desabilitar o Recebimento de Chamadas em Grupo de determinado usuário, o número do grupo que foi atribuído ao usuário não é retido. Se desejar habilitar novamente o Recebimento de Chamadas em Grupo para esse usuário, será necessário atribuir o numero do grupo novamente com a opção /enablegrouppickup.

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Descrição

SYSPrep. ps1 é um script do Windows PowerShell que instalará os seguintes pré-requisitos do Skype for Business Server 2015 na máquina do sistema operacional Windows Server 2008.

- Microsoft .Net Framework 4.5

- Microsoft SQL Server Express

- Windows PowerShell versão 3.0

- Pacotes Redistribuíveis do Visual C++ 2010

- Atualizações do Servidor de Informações da Internet

- Windows Identity Foundation

- Arquivos principais do Skype for Business Server 2015

  Embora o nome do script seja semelhante à Ferramenta de Preparação do Sistema para os sistemas operacionais Microsoft Windows, eles são diferentes. Este script instalará somente os pré-requisitos obrigatórios do Skype for Business Server 2015. Depois que esses requisitos estiverem instalados, a ferramenta SYSPrep do Windows poderá então ser usada para criar uma imagem do servidor.

### <a name="requirements"></a>Requisitos

Antes de executar o script SYSPrep. ps1, você deve copiar os arquivos de pré-requisito para uma pasta local na máquina do sistema operacional Windows Server 2008 (por exemplo, **D:\setup)**. Essa pasta também deve incluir uma cópia dos arquivos do Skype for Business Server 2015, especificamente **Setup. exe.** Os arquivos de pré-requisitos podem ser baixados dos seguintes locais:


| **Pré-requisito**                                | **Local**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .Net Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell versão 3.0  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| Pacotes Redistribuíveis do Visual C++ 2010  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| Atualizações do Servidor de Informações da Internet  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| Setup. exe do Skype for Business Server 2015  <br/> | Copiar da mídia do Skype for Business Server 2015  <br/>                   |

### <a name="parameter"></a>Parâmetro

O parâmetro **-SetupFolder** assume como um argumento o local do diretório dos arquivos de pré-requisito

### <a name="examples"></a>Exemplos

Para executar o script SYSPrep. ps1 e instalar os pré-requisitos do Skype for Business Server 2015, execute o seguinte comando em um prompt de comando elevado:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Migração de Comunicados de Número Não Atribuído
<a name="UNAM"> </a>

A ferramenta de migração de anúncios de número não atribuído permite que um administrador do Skype for Business Server 2015 mova a configuração de números não atribuídos que é atendida pelo aplicativo de anúncio de um servidor ou pool de origem do Skype for Business para um Servidor ou pool de destino do Skype for Business.

### <a name="description"></a>Descrição

A ferramenta de Migração de Comunicados de Número Não Atribuído é um script do Windows PowerShell que move a configuração de números não atribuídos atendidos pelo aplicativo de comunicados de um servidor ou pool de origem para outro servidor ou pool.

Quando executado, o script da Migração de Comunicados de Número não Atribuído realizará as seguintes operações:

1. Mover todos os arquivos de áudio usados pelos comunicados de números não atribuídos do aplicativo de comunicado hospedado no servidor ou pool de origem para o repositório de arquivos do servidor ou pool de destino.

    > [!NOTE]
    > Os arquivos de áudio são removidos do pool de origem quando são copiados para o pool de destino.

2. Mover todos os comunicados de números não atribuídos configurados do aplicativo de comunicados hospedado no servidor ou pool de origem para o servidor ou pool de destino.

3. Atribuir novamente todos os intervalos de números não atribuídos que são atendidos pelo aplicativo de comunicados hospedado no servidor ou pool de origem ao servidor ou pool de destino.

Depois de executar o script com êxito, todos os intervalos de números não atribuídos que eram atendidos pelo aplicativo de comunicados hospedado no servidor ou pool de origem agora serão atendidos com a mesma configuração pelo servidor ou pool de destino.

### <a name="output"></a>Resultado

O script **move-CsAnnouncementConfiguration** indica na janela do Shell de gerenciamento do Skype for Business Server na qual ele é executado o êxito ou falha da operação de migração.

Se a execução da operação for interrompida por qualquer erro, os intervalos de números não atribuídos que foram movidos com êxito para o destino permanecerão no destino de uma forma operacional, e o restante dos intervalos de números não atribuídos a serem migrados permanecerá na origem também em uma forma operacional. Para migrar totalmente o restante da configuração, execute novamente o script depois de resolver o erro.

### <a name="purpose"></a>Objetivo

O script de Migração de Comunicados de Número Não Atribuído pode ser usado nos três cenários a seguir:

- **Migrando definições de configuração para uma nova versão do Skype for Business Server:** A Contoso está em processo de migração para o Skype for Business Server 2015 e, como parte do processo de migração, o administrador do Skype for Business Server gostaria de mover a configuração de números não atribuídas atendida pelo aplicativo de anúncio da implantação do Lync Server 2013 para a nova implantação do 2015 do Skype for Business Server. Para mover as definições de configuração, o administrador do Skype for Business Server usa a ferramenta de migração de anúncios de número não atribuído.

- Reverter **uma implantação do Skype for Business server 2015 para o Lync Server 2013:** Devido a fatores inesperados, a contoso tem que reverter a migração para a nova implantação do Skype for Business Server 2015. Para minimizar as interrupções do serviço, o administrador do Skype for Business Server usa a ferramenta de migração de anúncios de número não atribuído para reverter a configuração da implantação do Skype for Business Server 2015 para a implantação do Lync Server 2013.

- **Mover dados entre implantações:** A Contoso está em processo de substituição de todos os servidores de um pool por servidores mais recentes. Sua estratégia é implantar um novo pool do Skype for Business Server 2015, mover todos os dados do antigo para o novo pool e, em seguida, substituir o antigo pool. Depois que o novo pool é implantado, a ferramenta de migração anúncios de número não atribuído é usada para mover a configuração do pool antigo para o novo.

#### <a name="requirements"></a>Requisitos

Os principais requisitos necessários para executar a ferramenta com êxito são os seguintes:

1. O script deve ser executado em um computador com o Shell de gerenciamento do Skype for Business Server instalado.

2. O aplicativo de anúncio precisa ser implantado com sucesso nos servidores ou pools de origem e destino do Skype for Business.

#### <a name="move-csannouncementconfiguration-script"></a>Script Move-CsAnnouncementConfiguration

O script Move-CsAnnouncementConfiguration exige os dois parâmetros descritos na tabela abaixo. 

![Parâmetros move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Exemplos

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Mover a configuração de anúncios de número não atribuído de um pool do Lync Server 2013 para um pool do Skype for Business Server 2015

Este exemplo move os anúncios de número não atribuído do pool de origem (Lync Server 2013) para o pool de destino (Skype for Business Server 2015).

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Mover a configuração de anúncios de número não atribuído de um pool do Skype for Business Server 2015 para um pool do Lync Server 2013

Este exemplo move os anúncios de número não atribuído do pool de origem (Skype for Business Server 2015) para o pool de destino (Lync Server 2013).

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf Data
<a name="WebConfData"> </a>

A ferramenta Web conf data permite que um administrador do software de comunicação do Skype for Business Server 2015 tenha mais controle sobre os dados associados às conferências da Web do organizador. Cenários incluem a capacidade de excluir os dados de uma reunião de um usuário específico com base em um critério de carimbo de data/hora.

### <a name="description"></a>Descrição

Esta ferramenta permite ao administrador executar as seguintes operações:

1. Encontrar todos os dados de webconferência associados a um único usuário.

2. Excluir todos os dados de webconferência associados a um único usuário.

3. Excluir todos os dados de webconferência associados a um único usuário que sejam anteriores à determinada data.

4. Mover todos os dados de webconferência associados a um único usuário quando o usuário for movido de um pool para outro.

> [!NOTE]
> As ferramentas do kit de recursos para Lync Server 2010 têm suporte para mover todos os dados de Webconferência associados a um único usuário quando esse usuário é movido de um pool para outro. Essa funcionalidade agora foi preterida nesta ferramenta em favor do parâmetro **MoveConferenceData**. Para obter detalhes sobre esse parâmetro, consulte o cmdlet [move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .

A ferramenta exclui dados apenas de reuniões que estejam inativas. As reuniões ativas (ou reuniões em sessões) não podem ser excluídas.

Essa ferramenta deve ser executada em um computador que esteja no mesmo pool do usuário de destino. O usuário cujos dados de conteúdo de reuniões estiverem sendo gerenciados por essa ferramenta deverá ser hospedado no mesmo pool de usuários.

### <a name="output"></a>Resultado

Essa ferramenta gera os resultados de cada uma das operações:

- Se uma consulta é executada, a ferramenta gera a lista de todas as pastas de dados de reuniões inativas que tenham esse usuário como organizador.

- Se uma exclusão é realizada, a ferramenta gera a lista de todas as pastas de dados de reuniões cujos dados serão excluídos.

### <a name="requirements"></a>Requisitos

A ferramenta deve ser executada no mesmo pool onde o organizador está hospedado.

A ferramenta deve ser executada com privilégios de administrador com acesso ao repositório de arquivos de conteúdo.

### <a name="examples"></a>Exemplos

A tabela a seguir descreve os parâmetros, alguns dos quais são usados nos exemplos.

![Parâmetros da ferramenta de dados Web conf.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

O exemplo anterior mostra como um comando de consulta funcionaria. O resultado desse comando seria uma lista de todas as pastas de conteúdo de reuniões que seriam afetadas por essa ferramenta.

```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

O exemplo anterior mostra um comando de exclusão (delete), que removerá todas as pastas de reuniões inativas deste usuário.

### <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para os administradores que precisam de um controle mais preciso sobre os dados de reuniões realizadas em chamadas em conferência.


