---
title: Documentação das Ferramentas do Kit de Recursos do Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: Este tópico descreve as ferramentas do Skype para Business Server 2015 Resource Kit, incluindo o propósito de cada ferramenta e exemplos de seu uso. O Skype para Business Server 2015 Resource Kit ajuda a facilitar as tarefas de rotina para administradores de TI que implantam e gerenciam Skype para Business Server 2015. Por exemplo, a ferramenta Web Conf Data pode ser usada para controlar facilmente os dados carregados pelos usuários durante uma reunião online. A ferramenta SEFAUtil pode ser usada para configurar o encaminhamento e as respostas de chamadas de representantes para os usuários. Recomendamos que os administradores de TI para usar essas ferramentas para gerenciar com mais eficiência Skype para Business Server 2015.
ms.openlocfilehash: 3f36edc42541dfcc9b652eb16d5062277277cbc0
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294374"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Documentação das Ferramentas do Kit de Recursos do Skype for Business Server 2015

Este tópico descreve as ferramentas do Skype para Business Server 2015 Resource Kit, incluindo o propósito de cada ferramenta e exemplos de seu uso. O Skype para Business Server 2015 Resource Kit ajuda a facilitar as tarefas de rotina para administradores de TI que implantam e gerenciam Skype para Business Server 2015. Por exemplo, a ferramenta **Web Conf Data** pode ser usada para controlar facilmente os dados carregados pelos usuários durante uma reunião online. A ferramenta **SEFAUtil** pode ser usada para configurar o encaminhamento e as respostas de chamadas de representantes para os usuários. Recomendamos que os administradores de TI para usar essas ferramentas para gerenciar com mais eficiência Skype para Business Server 2015.

## <a name="installation-of-the-resource-kit-tools"></a>Instalação das Ferramentas do Kit de Recursos

Para instalar o Skype para Business Server 2015 Resource Kit, baixe [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) no Centro de Download.

Execute o **OCSResKit.msi** para fazer uma instalação simples. O .msi instala todas as ferramentas no seguinte caminho: **%Arquivos de Programas%\Skype for Business Server 2015\ResKit**. As ferramentas que são executáveis autocontidos ficam nessa pasta. As ferramentas que também têm arquivos de suporte ficam em suas próprias subpastas.

## <a name="supported-environments"></a>Ambientes com suporte

O Skype para Business Server 2015 Resource Kit deve ser instalado em um servidor que atenda às especificações exigidas para Skype para Business Server 2015, normalmente um que está sendo usada para executar o Skype para Business Server 2015.

## <a name="resource-kit-tools-overview"></a>Visão geral das Ferramentas do Kit de Recursos

O exemplo a seguir é uma lista das ferramentas são fornecidas no Skype para Business Server 2015 Resource Kit. As seções a seguir mostram uma descrição de cada ferramenta, com requisitos e exemplos de uso.

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

A ferramenta de configuração do serviço de catálogo de endereços (ABSConfig) é uma ferramenta administrativa que ajuda os administradores a personalizar a configuração do serviço Catálogo de endereços no Skype para Business Server 2015. Essa ferramenta também permite que o Skype para que os administradores corporativos Server 2015 restaurar as configurações do serviço Catálogo de endereços padrão.

### <a name="description"></a>Descrição

ABSConfig é um aplicativo de interface gráfica do usuário que permite aos administradores configurarem os atributos do Active Directory Domain Services que estão relacionados ao serviço Catálogo de endereços.

Veja aqui os principais cenários da ferramenta:

- Para permitir que os administradores mapeiem os atributos nos serviços de domínio do Active Directory para os atributos para Skype para Business Server 2015.

- Permitir que os administradores especifiquem os atributos do Active Directory Domain Services a serem incluídos ou excluídos dos arquivos do Serviço de Catálogo de Endereços.

- Permitir que os administradores restaurem as configurações padrão do Serviço de Catálogo de Endereços.

A ferramenta ABSConfig pode ser iniciada usando o arquivo absConfig.exe. A ferramenta é aberto na guia **Configurar atributos** . Esta tabela possui opções para mapear os atributos do Active Directory Domain Services para os campos de atributo do Skype para Business Server 2015 e para especificar quais usuários devem ser incluídos ou excluídos nos arquivos do serviço de catálogo de endereços com base em filtros específicos de atributo. Ela também tem opções para personalizar quais números telefônicos serão incluídos no arquivo do Catálogo de Endereços. A opção **Restaurar Padrões** permite aos administradores restaurar os valores padrão das configurações do Serviço de Catálogo de Endereços.

> [!NOTE]
> Novamente o mapeamento dos atributos do AD para diferentes nomes de campo do OC será somente trabalho para Download de arquivo do catálogo de endereços e não é suportado pelo Address Book Web Query.

### <a name="output"></a>Resultado

A ABSConfig armazena a configuração do Serviço de Catálogo de Endereços no banco de dados.

```
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Objetivo

ABSConfig fornece uma maneira rápida e fácil personalizar Skype para o serviço de catálogo de endereços do Business Server 2015.

### <a name="requirements"></a>Requisitos

#### <a name="computer"></a>Computador

ABSConfig pode ser executado somente a partir de um computador associado ao domínio que tem Skype para negócios 2015 de servidor instalada. No caso do Skype para Business Server 2015, Enterprise Edition, essa ferramenta pode ser executada em qualquer servidor de Front-End que tenham o serviço de catálogo de endereços ativado durante a instalação.

#### <a name="network"></a>Rede

O computador deve poder se conectar ao pool de front-ends e ao banco de dados back-end.

#### <a name="software"></a>Software

Os seguintes componentes de software deverão ser instalados antes de executar a ferramenta ABSConfig:

- Skype for Business Server 2015

#### <a name="users"></a>Usuários

Administradores que possuem as permissões necessárias para atualizar o Skype para implantação Business Server 2015.

### <a name="examples"></a>Exemplos

A ABSConfig pode ser iniciada digitando **ABSConfig.exe** em um prompt de comando. Abaixo é mostrada a interface do usuário da ferramenta ABSConfig.

![A ferramenta ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Resumo

A ferramenta ABSConfig fornece uma rápida e fácil de usar a ferramenta para personalizar o Skype para o serviço de catálogo de endereços do Business Server 2015 de administradores.

## <a name="bandwidth-policy-service-monitor"></a>Monitor de Serviços da Política de Largura de Banda
<a name="bpsm"> </a>

A ferramenta Monitor de Serviços da Política de Largura de Banda permite que os administradores visualizem uma lista contendo:

1. Todos o Skype configurado para os serviços de diretiva de largura de banda do Business Server 2015 (autenticação e núcleo) na topologia

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
>  Se a ferramenta Monitor de serviço de política de largura de banda apresenta falha ao se conectar a qualquer um dos serviços de política de largura de banda configurados, as informações em guias **Informações de topologia** e as **Informações de máquina** não ser preenchidas. No entanto, é possível que a ferramenta se conecte inicialmente, mas depois perca a conexão com o serviço. Nesses casos, os administradores poderão ver informações desatualizadas. Há um carimbo de data/hora **Última Atualização** em cada uma das guias que permite aos administradores ver quando os dados foram atualizados pela última vez para um determinado Serviço da Política de Largura de Banda.

### <a name="output"></a>Resultado

Não há nenhum resultado na linha de comando; o resultado do programa está contido dentro da GUI (interface gráfica do usuário) principal.

### <a name="purpose"></a>Objetivo

O objetivo da ferramenta Monitor de Serviços da Política de Largura de Banda é proporcionar aos administradores visibilidade do estado de cada um dos serviços da Política de Largura de Banda definidos na topologia. Além disso, os administradores podem ver o uso da largura de banda em tempo real de todos os links definidos no documento de configuração da rede.

### <a name="requirements"></a>Requisitos

A ferramenta Monitor de serviço de política de largura de banda deve ser executado em um computador que faz parte do Skype para a topologia de servidor de negócios.

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

No qualquer implantação de vídeo e voz, é essencial para monitorar e entender a tendência de utilização de largura de banda de tráfego de mídia na rede corporativa. A ferramenta Analisador de Utilização da Largura de Banda permite ao administrador realizar justamente isso. Essa ferramenta faz o seguinte:

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

- **WanLinkLogCollector.exe** essa ferramenta permite que o usuário a digitar as informações necessárias.

- **BandwidthUtilizationAnalyzer.xlsm** relatório de software do Microsoft Excel de uma planilha é iniciado automaticamente pelo WanLinkLogCollector.exe. Este aplicativo permite ao usuário aplicar filtros ao relatório, como será mostrado posteriormente neste artigo.

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

1. **A linha do tempo de log** Forneça a linha do tempo que precisa ser gerado para o relatório

2. **Especificar os diretórios de arquivo** Fornecer informações de local de arquivo

3. **Coletar os logs e iniciar o Visualizador de relatório** Execute o comando para gerar o relatório

#### <a name="step-1---log-the-timeline"></a>Etapa 1 – Registrar a linha do tempo

O registro da linha do tempo permite que o usuário da ferramenta especifique o seguinte, conforme mostra a figura abaixo: 

1. **Data de início** Trata-se da data de início da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 1º de agosto de 2010.

2. **Data de término** Trata-se da data de término da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 30 de setembro de 2010.

     ![Datas de início e término na Utilização da Largura de Banda A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Etapa 2 – Especificar os diretórios do arquivo

Os seguintes diretórios de arquivo devem ser especificados pelo usuário, como a seguir:

- **Local de arquivos de log do servidor** O local da pasta onde os logs do servidor de política de largura de banda são armazenados. Esse é normalmente em \<servidor de arquivos\>\\<choice de FE\>\AppServerFiles\PDP.

- **Local de armazenamento de arquivo temporário** O local de arquivo temporário onde os arquivos intermediários são armazenados enquanto o relatório está sendo gerado.

![Arquivos de diretórios na Análise da Utilização da Largura de Banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> Forneça ao usuário da ferramenta acesso suficiente aos arquivos de logs do servidor e à pasta de repositório de arquivos temporários.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Etapa 3 – Coletar os logs e iniciar o visualizador de relatórios

Para coletar os logs e iniciar o visualizador de relatórios, clique em **Executar**, como mostrado abaixo. Esta etapa coleta os dados necessários.

![Coletando dados da Análise de Utilização de Largura de Banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Se a validação da entrada for bem-sucedida, a mensagem abaixo será exibida.

![Notificação de coleta de logs no Bandwidth Utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Clique em **OK**. BandwidthUtilizationAnalyzer.xlsm será iniciado automaticamente. Siga as instrução na caixa de mensagens. Para obter mais detalhes, consulte **Uso do BandwidthUtilizationAnalyzer.xlsm ** na próxima seção.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Uso do BandwidthUtilizationAnalyzer.xlsm

1. Se o BandwidthUtilizationAnalyzer.xlsm tiver sido iniciado automaticamente, clique em **Atualizar**, como a seguir.

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Quando uma pasta de arquivos for aberta, selecione consolidated.csv na localização especificada na caixa de mensagens, como a seguir. A localização também é mostrada como **C:\Temp**.

     ![Como abrir uma pasta no BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Clique em **Importar**.

4. A plotagem gráfica é gerada automaticamente. Ela será disponibilizada assim que o ponteiro de trabalho em segundo plano desaparecer.

     ![Aplicando filtros no modo de exibição Relatórios.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Aplicando filtros ao visualizador de relatórios

Os filtros que podem ser aplicados ao visualizador de relatórios, conforme mostrado abaixo, são descritos da seguinte forma:

![Aplicando filtros no modo de exibição Relatórios.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

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

![Filtrando por nome em BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filtrar por **Limite excedido**. Selecione **True** para impor o filtro.

![Filtrando por Limite Excedido.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtrar por **Níveis críticos**. Selecione **True** para impor o filtro.

![Filtrando por Níveis Críticos.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtrar por **Subutilizado**. Selecione **True** para impor o filtro.

![Filtrando por Sub-utilizados.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtrar por **Tipo de Link**. Selecione um ou mais tipos que precisam ser exibidos.

![Filtrando por tipo de Link.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtrar por **Região**. Selecione uma lista de regiões cujos links precisam ser exibidos.

![Filtrando por Região.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Requisitos

- .NET Framework 3.5

- Microsoft Excel 2010 ou Excel 2007

### <a name="summary"></a>Resumo

O Analisador de Utilização da Largura de Banda é usado para plotar a utilização da largura de banda de áudio do tráfego de UC na rede. Esta ferramenta pode ser usada também para relatar a utilização da largura de banda de vídeo na rede.

## <a name="call-parkometer"></a>Parquímetro de Chamada
<a name="callpark"> </a>

O Parquímetro de Chamada é um aplicativo de linha de comando que proporciona fácil acesso ao banco de dados da Órbita do Call Park.

### <a name="description"></a>Descrição

O Parquímetro de Chamada é uma ferramenta que rastreia as chamadas estacionadas atualmente. Ele também coleta estatísticas sobre as órbitas e o uso do CPS (Servidor de Estacionamento de Chamada). Essa ferramenta de linha de comando fornece acesso de leitura e gravação para a banco de dados do SQL Server de órbita de CPS de um computador local ou remotamente conectado.

Todas as opções são mutuamente exclusivas. A sintaxe da linha de comando é a seguinte:

- **-o** parâmetro — todos configurados para este pool de intervalos de órbita de listas.

- parâmetro **-n** — Órbitas listas tudo atualmente usadas neste pool. As informações são exibidas da seguinte forma:

  - URI (Uniform Resource Identifier) do SIP da chamada estacionada e do estacionador.

  - Nome do host do CPS onde a chamada está estacionada.

  - Carimbo de data/hora de quando a chamada foi estacionada.

- parâmetro **-f** — lista o número de Órbitas atualmente gratuitos no pool.

- **-r \<n\> ** parâmetro — lista as \<n\> última estacionadas chamadas. As informações são exibidas da seguinte forma:

  - URI do SIP da chamada estacionada.

  - URI do SIP do estacionador da chamada.

  - Nome do host do CPS onde a chamada foi estacionada.

  - Carimbo de data/hora de quando a chamada foi recuperada ou ignorada.

- **-t\<n\> ** parâmetro - testa reservar uma órbita no banco de dados para mostrar a aleatoriedade dos números de órbita atribuído.

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

Não haverá nenhum requisito se esta ferramenta for executada no mesmo computador que estiver executando o CPS. Se essa ferramenta for executada em um computador remoto, o banco de dados do SQL Server usado pelo Skype para Business Server 2015 deve ser configurado para permitir o acesso remoto. Chamada Parkometer deve ser configurado com uma cadeia de conexão de banco de dados do SQL Server para se conectar ao servidor do SQL do pool. Esta cadeia de caracteres de conexão de banco de dados do SQL Server é definida no arquivo de configuração, **parkometer.exe.config**. Ele deve ser colocado no mesmo diretório onde parkometer.exe está localizado. O arquivo XML a seguir está um exemplo de um parkometer.exe.config. Os parâmetros que devem ser configurados são o nome de usuário (por exemplo, mydomain\Administrator), a senha (por exemplo, minhasenha) e o nome de host (por exemplo, MeuServidor).

```
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

Implantado intervalos de órbita: o parâmetro -o lista todos os intervalos de órbita que são configurados para este pool como mostrado

![Intervalos de órbitas no Estacionador de Chamadas.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Atualmente estacionadas chamadas: o parâmetro - n lista todas as Órbitas atualmente em uso desse pool, conforme mostrado

![Chamadas estacionadas no momento no Estacionador de Chamadas.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Número de Órbitas livres: o parâmetro -f lista o número de Órbitas atualmente gratuitos do pool, conforme mostrado

![Órbitas livres no Estacionador de Chamadas.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Recentemente estacionadas chamadas: - r \<n\> listas de parâmetro o \<n\> última estacionadas chamadas, conforme mostrado

![Chamadas estacionadas recentemente no Estacionador de Chamadas.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Reserva de órbita de teste: -t \<n\> parâmetro testa reservar uma órbita no banco de dados, conforme mostrado

![Reservas de órbitas de teste no Estacionador de Chamadas.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Resumo

O Parquímetro de Chamada é uma ferramenta de linha de comando que fornece informações detalhadas sobre o Servidor de Estacionamento de Chamada.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Descrição

DBAnalyze é uma ferramenta de linha de comando que ajuda os administradores a coletar relatórios de análise sobre o Skype para bancos de dados corporativos Server 2015. O DBAnalyze tem os seguintes modos: diagnóstico, dados do usuário, conferência, MCUs e fragmentação de disco:

- **Modo de diagnóstico** Cria um relatório que inclui informações sobre tabelas (número de registros, fragmentação, tamanho de dados e tamanho do índice), tamanhos de arquivo de dados e log, a última vez de backup, distribuição visita entre servidores que estão executando o Microsoft Office Communications Server, o número médio de permissões, contatos, recipientes, inscrições, publicações, pontos de extremidade por usuário, qualquer usuários hospedados de forma inadequada, os usuários que não podem ser roteados, o número médio de conferências organizadas por usuário, conferências agendadas, conferências ativas, e a versão do banco de dados.

    > [!NOTE]
    > A execução do modo de diagnóstico pode afetar o desempenho do servidor.

- **Modo de dados do usuário** Relatórios de contato, contêiner, assinatura, publicação, permissão e dados do grupo de contatos para um usuário específico ou para usuários que têm esse usuário em suas listas de permissão e de contato. Este modo também relata dados resumidos de conferências que um usuário organizou ou para as quais foi convidado.

- **Modo de conferência** Dados de relatórios detalhados para uma conferência específica, incluindo todos os detalhes de agenda de tempo para a conferência, a lista de convidado, a lista de tipos de mídia permitidos para a conferência, active MCUs (unidades de controle de multipontos), a lista de participantes ativos e cada um estado de sinalização do participante.

- **Decodificar ID de reunião** Decodifica uma rede telefônica pública comutada (PSTN) ID que é especificado pela opção **/pstnid** , mas não se conectam ao back-end para obter informações detalhadas de reunião.

- **Resolver a conferência** Decodifica uma ID de reunião de PSTN que é especificada pela opção **/pstnid** e exibe informações sobre a conferência indicada pela ID do.

- **Modo de MCUs** Relata a ID, tipo de mídia, URL, status da pulsação, carga de conferência e carga de participante para cada MCU no pool.

- **Modo de fragmentação de disco** Exibe o status de fragmentação de todos os discos.

Esta ferramenta pode ser usada para diagnosticar diversos problemas ou para ajudar os administradores no planejamento da capacidade. Por exemplo, se a maioria dos usuários hospedados no servidor A escolher como contatos usuários hospedados no servidor B, o administrador poderá mover os usuários do servidor A para o servidor B para reduzir o tráfego entre servidores.

### <a name="output"></a>Resultado

Essa ferramenta emite predefinidos relatórios sobre o Skype para banco de dados de negócios Server 2015. **Caminho**: %Arquivos de Programas%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>Objetivo

Para instalar o Dbanalyze.exe, copiá-lo para uma pasta local e, em seguida, executar a ferramenta. Para usar a ferramenta, execute o seguinte comando na linha de comando. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`As descrições das opções de linha de comando são mostradas abaixo.

![Opções de linha de comando para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Requisitos

 **Computador** DBAnalyze pode ser executado somente a partir de um computador associado ao domínio que tem Skype para negócios 2015 de servidor instalada.

 **Rede** O computador deve poder se conectar ao banco de dados back-end.

 **Software** Skype para componentes de software do Business Server 2015 deve ser instalado antes de executar DBAnalyze.

 **Usuários** A tabela abaixo mostra os administradores que têm as permissões necessárias para acessar o Skype para bancos de dados corporativos Server 2015.

![Tabela de permissões para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

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

DBAnalyzer fornece aos administradores uma rápida e fácil de analisar Skype para bancos de dados corporativos Server 2015.

## <a name="import-storage-service-data"></a>Importar Dados do Serviço de Armazenamento
<a name="Issd"> </a>

A ferramenta ImportStorageServiceData do kit de recursos permite reimportar os dados da fila e do ponto de extremidade que foram exportados do Serviço de Armazenamento (LYSS) para o Serviço de Armazenamento.

### <a name="description"></a>Descrição

A exportação dos dados do Serviço de Armazenamento pode ter sido automática (periodicamente) com base no status do item da fila ou no tamanho do banco de dados. Ela pode ter ocorrido devido à invocação manual do cmdlet de failover do pool ou do cmdlet StorageServiceFullFlush (invocado pelo cmdlet de failover do pool). Observe que dados idealmente não devem ser novamente importados se qualquer um do tamanho do banco de dados de serviço de armazenamento (LYSS) no front-ends estiver acima do nível normal, pois isso provavelmente apenas causará mais dados a serem exportados retirada. Além disso, quaisquer problemas que poderiam ter contribuíram para erros que causaram a fila do serviço de armazenamento crescer devem primeiro ser resolvidos (para erros de ponto de extremidade do Exchange de exemplo, problemas de rede ou outros problemas).

 **Cenário 1:** durante o failover do pool, os arquivos poderão ser liberados do serviço de armazenamento de cada front-end. Após a conclusão do failover, a ferramenta deverá ser executada para reimportar os dados.

 **Cenário 2:** os dados estão sendo exportados de maneira automática diariamente ou em resposta ao banco de dados de Serviço de Armazenamento ter excedido determinados limites de tamanho (por exemplo, 60%, 80%, 90%, capacidade total). Esses dados exportados automaticamente devem ser reimportados regularmente pelo administrador. Na situação acima, se o pacote do SCOM monitoramento não estiver implantado, existem eventos para Skype para serviço de armazenamento do servidor do Business relacionadas a dados sendo liberados do serviço de armazenamento. As IDs de evento são: 32075 (operação de exportação completa iniciada), 32076 (exportação completa concluída), 32082 (exportação de nível de manutenção iniciada), 32083 (exportação de nível de manutenção concluída), 32089 (exportação ocorrida devido ao preenchimento do banco de dados). Observe que essas IDs de evento correspondem à versão do RTM. Quando um administrador vê esses eventos, significa que não existem arquivos que foram liberados check-out. Esses dados devem ser importados rotineiramente volta usando essa ferramenta, por exemplo uma vez por semana.

Para a versão de serviço on-line, se o pacote do SCOM do Skype para Business Server de monitoramento de integridade tiver sido implantada, há novos alertas que podem ser geradas que pedir ao administrador Reimporte os dados liberados volta para o serviço de armazenamento. Haverá um evento correspondente no log de eventos no servidor front-end que disparou o alerta. O evento dará uma descrição do caminho pai sob o qual se encontram os arquivos de dados exportados, bem como a quantidade de arquivos existentes que cumpre os critérios do alerta. O critério de alerta é de que há X ou mais arquivos sob o caminho pai específico que tem pelo menos Y dias (em que X e Y são predefinidos dentro do StorageService, mas podem ser substituídos, alterando o arquivo APPCONFIG). Dois exemplos de eventos que podem disparar o alerta de integridade são mostrados abaixo, com a diferença sendo seu respectivo caminho pai. Uma possibilidade está no compartilhamento de arquivos do serviço Web, enquanto a outra possibilidade está no diretório Dados de Aplicativos local de cada front-end (por exemplo c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService). O administrador executará essa ferramenta do reskit.

Essa ferramenta aumentará a carga de CPU e de E/S no front-end em que estiver sendo executada e também em outros front-ends se os dados não pertencerem ao front-end no qual a ferramenta estiver sendo executada. Recomendamos executar essa ferramenta quando os front-ends não estiverem sob uma carga de E/S e CPU pesada, por exemplo, fora dos horários de pico. Em segundo lugar, essa ferramenta leva de 2 a 3 minutos para importar um arquivo de dados. Lembre-se disso ao estimar por quanto tempo a ferramenta será executada. O arquivo de log detalhado gerado pela ferramenta será exibido por padrão no Repositório de Arquivos. Exclua-o se não houver nenhum erro relatado, pois o arquivo de log pode ter muitos megabytes.

![Amostra de eventos de registro de eventos do Servidor de Armazenamento.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Requisitos

Instale o Skype para as ferramentas do Resource Kit do Business Server 2015. A ferramenta é executada em computadores de domínio onde Skype para Business Server e do Skype do Shell de gerenciamento do servidor de negócios estão instalados. A ferramenta usa um cmdlet do shell de gerenciamento para identificar todos os servidores de Front-End no pool. Em segundo lugar, a ferramenta deve ser executada em uma máquina do pool que tem o banco de dados **RtcLocal** instalado. Esse banco de dados é usado pela ferramenta para recuperar o local do compartilhamento de arquivo WEBSERVICE para o pool. Além disso, antes de usar a ferramenta, cada servidor Front-End deve primeiro habilitar usando **Enable-PSRemoting** em cada servidor Front-End, bem como a máquina que está executando a ferramenta de comunicação remota do Windows PowerShell. Caso contrário, os comandos do Windows PowerShell remotos dessa ferramenta irá falhar. Windows PowerShell remoto podem ser desativado em todos os servidores de Front-End no pool depois que ele for concluído. Finalmente, a conta ou a ferramenta de invocação de credencial deve ter permissão de leitura/gravação para o compartilhamento de arquivo para o pool que eles estão executando essa ferramenta webservice. Caso contrário, a ferramenta irá falhar com erros de permissão de e/s.

> [!NOTE]
> No Windows Server 2012, o Windows PowerShell remoto é habilitado por padrão, mas não no sistema operacional Windows Server 2008.

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

A ferramenta de LCSSync ajuda implantar Skype para o software de comunicação de negócios 2015 de servidor em um ambiente de várias floresta. Essa ferramenta é usada para sincronizar os usuários e grupos de florestas de usuário diferente, como um Active Directory Domain Services entre em contato com o objeto para uma floresta central onde Skype para Business Server 2015 está instalado.

### <a name="description"></a>Descrição

 LCSSync usa os serviços de domínio Active Directory sincronizados entre em contato com os objetos na floresta central para habilitar usuários para Skype para Business Server. Para fornecer o single sign-on, a conta de usuário principal deve ser mapeada para o objeto de contato do Active Directory Domain Services na floresta central para Skype para Business Server 2015. Essa ferramenta ajuda a realizar esse mapeamento. Ela também fornece modelos para a criação de Agentes de Gerenciamento no Microsoft Identity Integration Server.

### <a name="summary"></a>Resumo

A ferramenta de LCSSync ajuda implantar Skype para Business Server 2015 em um ambiente de várias floresta.

## <a name="lookup-user-console"></a>Pesquisar no Console de Usuários
<a name="LUC"> </a>

A ferramenta de LookupUserConsole exibe interno Skype para obter informações de roteamento do Business Server sobre usuários específicos. Essas informações poderão ser úteis para o suporte pessoal da Microsoft no diagnóstico de problemas de implantação e roteamento.

### <a name="description"></a>Descrição

 Executar LookupUserConsole.exe abrirá um prompt de comando que aceita endereços SIP e tenta exibir Skype interno para informações de roteamento Business Server relacionando-os. Digite **exit** para sair da ferramenta LookupUserConsole.

### <a name="requirements"></a>Requisitos

Instale o Skype para Business Server 2015 Resource Kit. A ferramenta é executada em computadores de domínio onde o Skype para Business Server está instalado.

### <a name="examples"></a>Exemplos

C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe

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

A ferramenta MSTurnPing permite que um administrador do Skype Business Server 2015 software de comunicações para verificar o status dos servidores executando os serviços de borda de áudio/vídeo e áudio/vídeo de autenticação, bem como os servidores que estão executando a política de largura de banda Serviços na topologia.

### <a name="description"></a>Descrição

A ferramenta MSTurnPing permite que um administrador do Skype Business Server 2015 software de comunicações para verificar o status dos servidores executando os serviços de borda de áudio/vídeo e áudio/vídeo de autenticação, bem como os servidores que estão executando a política de largura de banda Serviços na topologia.

A ferramenta permite ao administrador realizar os seguintes testes:

1. Teste do Servidor de Borda A/V: a ferramenta realiza testes em todos os Servidores de Borda A/V na topologia fazendo o seguinte:

   - Verificando se o Skype para serviço de autenticação de áudio/vídeo do Business Server é iniciado e pode emitir credenciais apropriadas.

   - Verificando se o Skype para serviço de borda de áudio/vídeo do Business Server é iniciado e pode alocar os recursos na borda externa com êxito.

2. Teste do Serviço da Política de Largura de Banda: a ferramenta realiza testes em todos os servidores que estejam executando os Serviços da Política de Largura de Banda na topologia fazendo o seguinte:

   - Verificando se o Skype para o serviço de política de largura de banda do Business Server (autenticação) foi iniciado e pode emitir credenciais apropriadas.

   - Verificando se o Skype para o serviço de política de largura de banda do Business Server (núcleo) é iniciado e pode executar a verificação de largura de banda com êxito.

Essa ferramenta deve ser executada em um computador que faça parte da topologia e tenha o repositório local instalado. 

### <a name="output"></a>Resultado

Essa ferramenta gera os resultados de cada uma das operações.

- Quando o teste **AudioVideoEdgeServer ** é realizado, a ferramenta gera o seguinte:

  - Os resultados do teste dos computadores que fornecem o Skype para serviço de autenticação de servidor 2015 áudio/vídeo de negócios da topologia

  - Os resultados do teste dos computadores que fornecem o Skype para serviço de borda do servidor 2015 áudio/vídeo de negócios da topologia

- Quando o teste **BandwidthPolicyServer** é realizado, a ferramenta gera o seguinte:

  - Os resultados do teste dos computadores que fornecem o Skype para serviço de política de largura de banda 2015 do Business Server (autenticação) na topologia

  - Os resultados do teste dos computadores que fornecem o Skype para serviço de política de largura de banda 2015 do Business Server (núcleo) na topologia

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

Essa ferramenta pode ser um recurso valioso para Skype para administradores de negócios Server 2015 que deseja verificar o status dos servidores que estão executando o áudio/vídeo e dos serviços de política de largura de banda.

## <a name="network-configuration-viewer"></a>Visualizador da Configuração de Rede
<a name="NCV"> </a>

Visualizador de configuração de rede pode ser usado pelo Skype para administradores de software de comunicações do Business Server 2015 para exibir a topologia de rede CAC (controle) de admissão de chamada para uma empresa que é provisionada para permitir que as sessões de comunicação em tempo real, como chamadas de voz ou vídeos com base em especificado a capacidade de largura de banda. Skype para administradores corporativos Server 2015 definir políticas CAC, que são impostas pelos serviços de política de largura de banda que são instalados com Skype para Business Server 2015.

### <a name="description"></a>Descrição

O Visualizador da Configuração de Rede (NetworkConfigurationViewer.exe) permite aos administradores executar as seguintes tarefas:

- Carregar e exibir a topologia de rede do CAC de um Skype para Business Server 2015 implantação em um formato gráfico.

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

 **Topologia de rede CAC carga e o modo de exibição de um Skype para Business Server 2015 implantação em um formato gráfico**: Skype para administradores corporativos Server 2015 pode carregar e exibir a configuração de topologia de rede do CAC em qualquer Skype para computador Business Server 2015 por usando a opção **Baixar a configuração de rede** , conforme mostrado na figura a seguir. A ferramenta irá falhar baixar ou exibir a configuração quando implantado em um computador que não tem conectividade com o Skype para Business Server 2015 repositório de configuração.

![Baixando configurações de rede.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Topologia de rede de carga e o CAC do modo de exibição de um arquivo de log do servidor de política de largura de banda em um formato gráfico:** Skype para servidores de diretiva de largura de banda do Business Server 2015 salve a topologia de rede CAC como parte do mecanismo de registro em log sob o Skype para o local de compartilhamento de arquivo Business Server 2015. Skype para administradores corporativos Server 2015 pode exibir tal arquivo em um formato gráfico, utilizando a opção de **Configuração de rede aberta** , conforme mostrado abaixo.

![Abrindo um arquivo de registro do Servidor de Políticas de Largura de Banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Salvar e armazenar a topologia de rede do CAC em um formato XML no disco: Skype para administradores corporativos Server 2015 pode salvar o arquivo de configuração de topologia de rede do CAC em um formato XML usando a opção **Salvar uma cópia da configuração de rede** , conforme mostrado abaixo. O arquivo de configuração salvo pode ser usado offline para fins de exibição gráfica.

![Salvando a configuração de rede como arquivo XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Salvar e diagrama de topologia de rede CAC repositório no formato JPG ou BMP: Skype para administradores corporativos Server 2015 pode salvar a configuração de topologia de rede do CAC em um formato gráfico (formatos de arquivo JPG e BMP) usando o diagrama **Salvar a configuração de rede como imagem** opção conforme mostrado abaixo.

![Salvando a configuração de rede como imagem.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Dados de configuração de topologia de rede CAC do modo de exibição:</strong> Skype para administradores corporativos Server 2015 pode exibir os dados de configuração de rede relacionados como regiões de rede, sites de rede, perfis de largura de banda e endereços IP de sub-rede de site em um formato textual usando a opção de dados de configuração de rede do modo de exibição conforme mostrado abaixo.

![Exibindo dados de configuração de rede.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Topologia de rede CAC do modo de exibição em um estilo de modo de exibição de árvore:** Skype para administradores corporativos Server 2015 pode exibir os dados de configuração de rede relacionados em um estilo de modo de exibição de árvore gráfica usando o painel de controle no lado esquerdo da janela de ferramenta, conforme mostrado abaixo.

![Exibindo dados de configuração de rede na visualização de árvore.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Conectores personalizados de definir CAC links de topologia (por exemplo, links de região do site, a região e to-site) de rede:** Skype para administradores corporativos Server 2015 pode definir conectores personalizados de gráficos para os links de WAN de configuração de rede CAC usando a opção de configurações, conforme mostrado abaixo. Isso ajuda a diferenciar entre os vários tipos de links de rede provisionados na configuração da rede.

![Ferramentas](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Informações de site de topologia de rede CAC do modo de exibição, as informações de região e políticas de largura de banda provisionados:** Skype para administradores corporativos Server 2015 pode exibir informações de região de rede CAC relacionadas, informações de site e largura de banda do CAC provisionamento informações usando as opções mostradas abaixo. Por exemplo, clique em **Informações** em uma região da rede ou objeto do site da rede.

![Definindo conectores personalizados para sua rede.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para Skype para administradores de negócios Server 2015 que gostaria de exibir a topologia de rede CAC para sua implantação em um formato gráfico.

## <a name="response-group-agent-live"></a>Agente do Grupo de Resposta em Tempo Real
<a name="RGAL"> </a>

O aplicativo Grupo de Resposta proporciona aos agentes a capacidade de acessar informações úteis em tempo real usando o serviço Web interno. Infelizmente, nenhuma exibição gráfica desses dados está disponível fora do aplicativo. A ferramenta de resposta grupo agente Live Resource Kit resolve esse problema, fornecendo uma maneira simples e gráfica para acessar essa informação, aprimorada com Skype em tempo real para informações de software de comunicações comerciais, como a presença de outros operadores.

### <a name="description"></a>Descrição

O Agente do Grupo de Resposta em Tempo Real é um aplicativo do Windows que fornece a funcionalidade de entrar e sair e algumas informações em tempo real (como membros do grupo e número atual de chamadas) a agentes do Grupo de Resposta. Ele deve ser uma versão aprimorada da página grupos de operadores (acessível a partir do Skype para negócios.

### <a name="purpose"></a>Objetivo

O aplicativo Grupo de Resposta enfileira as chamadas recebidas e, em seguida, as encaminha para os grupos de agentes. Para tomar decisões conscientes sobre quais chamadas devem ser atendidas, os agentes podem acessar informações em tempo real sobre os grupos de agentes, como quais outros agentes estão disponíveis e quantas chamadas estão em espera em cada fila. Essas informações, inicialmente acessíveis somente por meio do serviço de Grupo de Resposta, são disponibilizadas de forma intuitiva pelo Agente do Grupo de Resposta em Tempo Real.

#### <a name="features"></a>Recursos

A ferramenta Live de agente do grupo de resposta foi criada com o serviço de grupo de resposta e o Skype para Business Server 2015 SDK. Ela fornece aos agentes do Grupo de Resposta as informações e os recursos disponíveis no serviço de Grupo de Resposta (como membros do grupo, presença de outros agentes e número de chamadas em espera).

A figura abaixo ilustra a interface principal do Agente do Grupo de Resposta em Tempo Real.

![A ferramenta Agente de Grupo de Respostas Dinâmico.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Os seguintes três recursos principais estão disponíveis para os agentes do Agente do Grupo de Resposta em Tempo Real:

- **Entrada/saída:** Ao contrário da página grupos de agentes (acessível a partir do Skype para Business Server 2015), Live de agente do grupo de resposta permite que os agentes somente entrar ou sair de todos os agentes grupos ao mesmo tempo. Esse aplicativo oferece três maneiras rápidas para a entrada ou de saída de agentes:

  - Clicar nos botões Entrar/sair (verde e vermelho) no aplicativo.

  - Clicar com o botão direito do mouse no ícone de bandeja do sistema e selecionar entrar ou sair.

  - Usar os atalhos do teclado configuráveis.

- **a associação de grupo:** Quando um grupo de operadores é selecionado, agente do grupo de resposta Live exibe a lista de operadores do grupo, no painel direito. Se Skype para Business Server 2015 estiver em execução no mesmo computador que esse aplicativo, informações de presença e o cartão de visita são exibidos em que o agente de grupo de resposta Live. Os operadores podem enviar uma mensagem Instantânea ou chamada outros operadores diretamente a partir daí.

- **Estatísticas em tempo real:** o Agente do Grupo de Resposta em Tempo Real fornece estatísticas em tempo real de todos os grupos de agentes. A frequência de atualização é de um minuto. Quando uma chamada é atendida por um Grupo de Resposta, um indicador visual é adicionado ao lado do nome do grupo com o número atual de chamadas em fila. Pausar o ponteiro sobre um grupo também exibe o tempo de espera mais longo.

### <a name="requirements"></a>Requisitos

O Agente do Grupo de Resposta em Tempo Real requer o .NET Framework 4.0. Além disso, para se beneficiar dos recursos de cartão de contato e presença, Skype para negócios deve ser instalado localmente (e estar sendo executado).

#### <a name="configuration"></a>Configuração

O Agente do Grupo de Resposta em Tempo Real pode ser personalizado de acordo com as preferências individuais usando a caixa de diálogo Opções no aplicativo. Além disso, o administrador pode definir o endereço de host padrão editando diretamente a propriedade defaultHostAddress do arquivo RGAgentLive.exe.config.

A figura abaixo ilustra a caixa de diálogo Opções que os agentes podem usar para configurar as teclas de atalho e o endereço de host. Essa caixa de diálogo é acessada clicando no botão Opções no canto superior direito da interface principal.

![A caixa de diálogo de opções do Agente de Grupo de Respostas Dinâmico.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

As três configurações diferentes a seguir podem ser personalizadas na configuração do Agente do Grupo de Resposta em Tempo Real:

- Endereço de host: esse é normalmente web pertencentes ao pool primário do agente FQDN do pool. O endereço de serviço exato do Grupo de Resposta é automaticamente derivado em segundo plano dessa informação (anexado no caminho à direita depois do host).

- Atalhos: os atalhos exatos para entrar/sair podem ser personalizados. A única limitação é que ambos os atalhos devem conter a chave "Logotipo do Windows" (além de pelo menos outra chave).

- Iniciar com o Windows: o aplicativo pode ser configurado para ser iniciado automaticamente com o Windows.

### <a name="examples"></a>Exemplos

A figura abaixo ilustra como chamar ou enviar uma mensagem instantânea para outro agente clicando com o botão direito do mouse no contato no painel à direita.

![Realizar uma chamada ou enviar chat.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

A figura abaixo ilustra como o Agente do Grupo de Resposta em Tempo Real exibe o número atual de chamadas na fila e o tempo de espera mais longo entre todas as chamadas de entrada.

![Visualizando informações da fila.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Resumo

Ações rápidas de entrada e saída, associação a um grupo e estatísticas básicas em tempo real são recursos interessantes do Agente do Grupo de Resposta que estão disponíveis apenas fora do aplicativo do serviço de Grupo de Resposta. Com a ferramenta de resposta grupo agente Live Resource Kit, Skype para administradores corporativos Server 2015 pode fornecer seus agentes com um aplicativo do Windows que permite que eles realizem tarefas de forma mais rápida e gráfica.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (ativação do recurso de extensão secundário) é uma ferramenta de linha de comando que permite Skype para administradores de software de comunicações do Business Server 2015 e operadores de assistência técnica configurar o delegado toques, encaminhamento de chamadas, simultâneo tocando, configurações de chamada de equipe e retirada de chamada de grupo em nome de um Skype para usuário Business Server 2015. A ferramenta também permite aos administradores consultar as configurações de roteamento de chamadas que são publicadas para um usuário específico. A ferramenta SEFAUtil permite ao administrador para habilitar/desabilitar/modificar chamada encaminhamento ou toque simultaneamente em nome do usuário. O administrador pode especificar o destino (na forma de um URI do SIP) ou use um destino que já tenha sido publicado pelo usuário. Essa ferramenta também permite aos administradores adicionar ou remover representantes ou membros do grupo de chamada de equipe em nome do usuário. Essa ferramenta é compilada no Microsoft Unified Communications Managed API (UCMA) 3.0 e requer que os administradores criar um aplicativo confiável no repositório de gerenciamento Central para SEFAUtil.

SEFAUtil (ativação do recurso de extensão secundário) permite Skype para administradores de negócios Server 2015 e operadores de assistência técnica Configurar toques de representante, encaminhamento de chamadas, simultâneo toque, configurações de chamada de equipe e retirada de chamada de grupo em nome de um Skype para o usuário Business Server 2015. Essa ferramenta também permite aos administradores consultar as configurações de roteamento de chamadas publicadas para determinado usuário.

### <a name="description"></a>Descrição

A versão atual de SEFAUtil é apenas uma ferramenta de linha de comando; não há nenhum suporte para interface gráfica do usuário. Essa ferramenta baseia-se no Microsoft Unified Communications Managed API (UCMA) 3.0. Os recursos dessa ferramenta permitem a administradores e agentes de assistência técnica realizar as seguintes ações:

- Exibir todas as configurações de roteamento de chamadas de um usuário (inclui encaminhamento de chamadas, delegação, toque simultâneo, chamada de equipe e recebimento de chamada em grupo).

- Habilitar/desabilitar/modificar a configuração de encaminhamento de chamadas (inclui temporizador sem resposta e de destino).

- Habilitar/desabilitar/modificar configurações imediatas de encaminhamento de chamadas.

- Habilitar/desabilitar/modificar configurações de delegação.

- Habilitar/desabilitar/modificar configurações do grupo de chamada de equipe.

    > [!NOTE]
    > Novo no Skype para ferramenta de Business Server 2015 SEFAUtil

- Habilitar/desabilitar/modificar configurações de toque simultâneo (inclui destino).

    > [!NOTE]
    > Novo no Skype para ferramenta de Business Server 2015 SEFAUtil

- Habilitar/desabilitar/modificar configurações de recebimento de chamada em grupo.

    > [!CAUTION]
    > Novo no Skype para ferramenta de Business Server 2015 SEFAUtil

Esta ferramenta apresenta as seguintes limitações:

- Suporte apenas para usuários hospedados em um Skype para pool de servidores de negócios

- Não há suporte para edição em massa de configurações de roteamento de chamadas para diversos usuários.

### <a name="output"></a>Resultado

A versão atual desta ferramenta fornece resultados apenas na janela Prompt de Comando. Para ver detalhes, consulte a seção Exemplos mais adiante neste documento.

### <a name="purpose"></a>Objetivo

Veja a seguir alguns dos principais cenários onde esta ferramenta pode ser usada:

- Bob é uma executiva e foi movido para Skype para telefonia Business Server. Ele já tem delegação em seu sistema PBX existente. Como parte da movimentação para Skype para Business Server 2015, o administrador é capaz de configurar o roteamento de Bob para refletir a sua configuração de delegação pré-existente.

- Brenda está viajando e aguarda uma chamada importante de um de seus clientes. No entanto, ela está em hotel e não tem acesso a computador. Ela liga para a assistência técnica e solicita que encaminhem para seu número de celular todas as chamadas feitas para seu número comercial. O pessoal da assistência técnica pode fazer a configuração em seu nome.

- As chamadas para seu número comercial do Aníbal serão seu correio de voz móvel sempre que ele estiver no trabalho; No entanto, as coisas parecem estar funcionando corretamente na maioria dos outros locais. O técnico de assistência técnica é capaz de exibir a configuração de roteamento do Aníbal e descobre que Joe tenha configurado para seu telefone celular toque simultâneo. O técnico pergunta Joe sobre a cobertura móvel em seu escritório e é capaz de determinar o que a regra de toque simultânea é o que está causando as chamadas ir para a caixa postal de móvel do Aníbal quando sua cobertura de rede estiver baixa.

- Mike é um novo funcionário na Contoso e ele está ingressando em uma nova equipe em que todos os membros são configurados para chamada de equipe, quando está sendo habilitado para Skype para Business Server 2015, o administrador é capaz de definir as configurações de grupo para incluir todos os seus novos membros da equipe de sua chamada de equipe , além disso, o administrador adiciona Mike como um membro do grupo de chamada de equipe para cada um dos membros na sua equipe.

- Uma prática de atendimento ao cliente no departamento de recursos humanos da Contoso é fornecer um atendimento pessoal a todos os chamadores desde a primeira chamada. Como todos os membros do departamento sentam-se muito próximos uns dos outros, ter todos os telefones tocando ao mesmo tempo com a chamada de equipe é desconfortável para a equipe. Para fornecer o melhor serviço sem interromper os membros da equipe, o Skype para administrador Business Server 2015 aproveita a capacidade de atendimento de chamada do grupo. O administrador adiciona todos os membros do departamento a um grupo de recebimento e informa o número do grupo de recebimento ao departamento. Quando Clara está fora de sua mesa, Vinícius percebe que o telefone dela está tocando e atende à chamada em sua própria mesa.

### <a name="requirements"></a>Requisitos

A ferramenta SEFAUtil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis. O UCMA 3.0 deve ser instalado nesse computador. Para executar a ferramenta, um novo aplicativo confiável com a ID do aplicativo SEFAUtil deve ser criado nesse pool.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Criando um novo aplicativo confiável para a ferramenta SEFAUtil

1. A ferramenta SEFAUTil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis. Se necessário, a adição de um pool como um novo pool de aplicativos confiáveis pode ser feita por meio do Skype do Shell de gerenciamento do servidor de negócios com o seguinte cmdlet:

   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > O UCMA 3.0 deve ser instalado em qualquer computador que será usado para executar a ferramenta SEFAUtil.

2. Um aplicativo confiável precisa ser definido na topologia para a ferramenta SEFAUtil. Para definir SEFAUtil como um novo aplicativo confiável, usar o Skype para Business Server Management Shell e execute o seguinte cmdlet:

   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Uma porta diferente pode ser usada, se necessário.

3. As alterações de topologia precisam ser habilitadas. Habilitar as alterações de topologia pode ser feita por meio do Skype do Shell de gerenciamento do servidor de negócios, executando o seguinte cmdlet:

   ```
   Enable-CsToplogy
   ```

4. Se necessário, instale o Skype para Business Server 2015 ferramentas do Resource Kit no servidor que será usado para executar a ferramenta de SEFAUtil (o servidor deve ser parte de um pool de aplicativos confiáveis).

5. Verifique se o SEFAUtil está sendo executado corretamente. Para fazer isso, execute a ferramenta em um prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamadas de um usuário na implantação. Por padrão, a ferramenta será localizada em: "...\Program Files\Skype para 2015\Reskit Business Server". Para exibir as configurações de encaminhamento de chamadas de um usuário, use o seguinte comando:

   ```
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    As configurações de encaminhamento de chamadas do usuário devem ser exibidas.

#### <a name="group-call-pickup"></a>Recebimento de Chamadas em Grupo

Atendimento de chamada de grupo requer configuração adicional no Skype para negócios 2015 de servidor para o recurso deverá ser totalmente habilitado. Antes de atribuir grupos de atendimento aos usuários, consulte a documentação do produto de Recebimento de Chamadas em Grupo para ver as etapas de planejamento e implantação desse recurso.

### <a name="examples"></a>Exemplos

#### <a name="display-current-call-handling-settings"></a>Exibir configurações atuais de administração de chamadas

O comando a seguir exibe a administração de chamadas do usuário.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> Este exemplo usa a opção **/server** para especificar o Skype para Business Server para se conectar ao.

 **Saída**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Definir destino de encaminhamento de chamadas/destino sem resposta

Este exemplo define o encaminhamento de chamadas/destino sem resposta e o atraso de toque. Aqui, a opção /server não for fornecida; SEFAUtil tenta descoberta automática do Skype para Business Server 2015.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 **Saída**

```
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

```
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

 **Resultado**

```
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

 **Resultado**

```
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

```
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

```
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

```
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

```
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

```
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

```
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

```
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

```
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
> Se o grupo de chamada de equipe do usuário tiver sem membros, chamada de equipe não será ativada.

 **Saída**

#### <a name="disable-team-call"></a>Desabilitar chamada de equipe

Este exemplo desabilita a chamada de equipe de um determinado usuário.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **Saída**

```
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

```
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

SYSPrep.ps1 é um script do Windows PowerShell que instalarão o seguinte Skype para Business Server 2015 pré-requisitos em sua máquina do sistema operacional Windows Server 2008.

- Microsoft .Net Framework 4.5

- Microsoft SQL Server Express

- Windows PowerShell versão 3.0

- Pacotes Redistribuíveis do Visual C++ 2010

- Atualizações do Servidor de Informações da Internet

- Windows Identity Foundation

- Skype para arquivos de núcleo do Business Server 2015

  Embora o nome do script seja semelhante à Ferramenta de Preparação do Sistema para os sistemas operacionais Microsoft Windows, eles são diferentes. Esse script instalará apenas os pré-requisitos necessários para Skype para Business Server 2015. Depois que esses requisitos estiverem instalados, a ferramenta SYSPrep do Windows poderá então ser usada para criar uma imagem do servidor.

### <a name="requirements"></a>Requisitos

Antes de executar o script SYSPrep.ps1, você deve copiar os arquivos de pré-requisito para uma pasta local no computador do sistema operacional Windows Server 2008 (por exemplo **d:\Setup.)**. Essa pasta também deverá incluir uma cópia do Skype para arquivos de negócios Server 2015, especificamente **Setup.exe.** Os arquivos de pré-requisitos podem ser baixados dos seguintes locais:


| **Pré-requisito**                                | **Local**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .Net Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell versão 3.0  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| Pacotes Redistribuíveis do Visual C++ 2010  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| Atualizações do Servidor de Informações da Internet  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| Skype para Business Server 2015 Setup.exe  <br/> | Copiar do Skype para mídia Business Server 2015  <br/>                   |

### <a name="parameter"></a>Parâmetro

O parâmetro **- SetupFolder** tem como um argumento, o local do diretório dos arquivos de pré-requisito

### <a name="examples"></a>Exemplos

Para executar o script SYSPrep.ps1 e instalar o Skype para Business Server 2015 pré-requisitos, execute o seguinte comando em um prompt de comando elevado:

```
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Migração de Comunicados de Número Não Atribuído
<a name="UNAM"> </a>

A ferramenta de migração de comunicados de número não atribuído habilita um Skype para Business Server 2015 administrador mover a configuração de números não atribuídos servido pelo aplicativo de anúncio de uma fonte Skype para negócios servidor ou Pool para um destino Skype para Business Server ou Pool.

### <a name="description"></a>Descrição

A ferramenta de Migração de Comunicados de Número Não Atribuído é um script do Windows PowerShell que move a configuração de números não atribuídos atendidos pelo aplicativo de comunicados de um servidor ou pool de origem para outro servidor ou pool.

Quando executado, o script da Migração de Comunicados de Número não Atribuído realizará as seguintes operações:

1. Mover todos os arquivos de áudio usados pelos comunicados de números não atribuídos do aplicativo de comunicado hospedado no servidor ou pool de origem para o repositório de arquivos do servidor ou pool de destino.

    > [!NOTE]
    > Os arquivos de áudio são removidos do pool de origem, depois que eles serão copiados para o pool de destino.

2. Mover todos os comunicados de números não atribuídos configurados do aplicativo de comunicados hospedado no servidor ou pool de origem para o servidor ou pool de destino.

3. Atribuir novamente todos os intervalos de números não atribuídos que são atendidos pelo aplicativo de comunicados hospedado no servidor ou pool de origem ao servidor ou pool de destino.

Depois de executar o script com êxito, todos os intervalos de números não atribuídos que eram atendidos pelo aplicativo de comunicados hospedado no servidor ou pool de origem agora serão atendidos com a mesma configuração pelo servidor ou pool de destino.

### <a name="output"></a>Resultado

O script **Move-CsAnnouncementConfiguration** indica no Skype para a janela de Shell de gerenciamento do Business Server a partir de onde ele tenha executado o sucesso ou falha da operação de migração.

Se a execução da operação for interrompida por qualquer erro, os intervalos de números não atribuídos que foram movidos com êxito para o destino permanecerão no destino de uma forma operacional, e o restante dos intervalos de números não atribuídos a serem migrados permanecerá na origem também em uma forma operacional. Para migrar totalmente o restante da configuração, execute novamente o script depois de resolver o erro.

### <a name="purpose"></a>Objetivo

O script de Migração de Comunicados de Número Não Atribuído pode ser usado nos três cenários a seguir:

- **Migrando as configurações para uma nova versão do Skype Business servidor:** A Contoso está em processo de migração para o Skype for Business Server 2015 e como parte do processo de migração do Skype para Business Server administrador gostaria de mover a configuração de números não atribuídos atendida pelo aplicativo comunicado do Lync Implantação de Server 2013 para o novo Skype para implantação Business Server 2015. Para mover as definições de configuração, o Skype para administrador Business Server usa a ferramenta de migração de comunicados de número não atribuído.

- **Revertendo uma implantação do Skype para Business Server 2015 ao Lync Server 2013:** Vencimento inesperadas fatores, a Contoso tem reverter a migração para o novo Skype para implantação Business Server 2015. Para minimizar as interrupções ao serviço, o Skype para administrador Business Server usa a ferramenta de migração de comunicados de número não atribuídos para reverter a configuração do Skype para Business Server 2015 implantação para a implantação do Lync Server 2013.

- **Mover dados entre implantações:** A Contoso está em processo de substituição de todos os servidores de um pool com servidores mais recentes. Sua estratégia é implantar um novo Skype para Business Server 2015 pool, mover todos os dados do ambiente antigo para o novo pool e, em seguida, preterir o pool antigo. Depois que o novo pool for implantado, a ferramenta de migração de comunicados de número não atribuído é usada para mover a configuração do pool antigo para o novo.

#### <a name="requirements"></a>Requisitos

Os principais requisitos necessários para executar a ferramenta com êxito são os seguintes:

1. O script deve ser executado em um computador que tenha Skype do Shell de gerenciamento do Business Server instalado.

2. O aplicativo de anúncio deve ser implantado com êxito na origem e destino Skype para negócios servidores ou Pools.

#### <a name="move-csannouncementconfiguration-script"></a>Script Move-CsAnnouncementConfiguration

O script Move-CsAnnouncementConfiguration exige os dois parâmetros descritos na tabela abaixo. 

![Parâmetros Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Exemplos

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Mudando a configuração de anúncios de números não atribuídos a partir de um Pool do Lync Server 2013 para um Skype para Pool de servidores 2015 de negócios

Este exemplo move os comunicados de números não atribuídos do pool de origem (Lync Server 2013) para o pool de destino (Skype para Business Server 2015).

```
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Mudando a configuração de anúncios de números não atribuídos de um Skype para Pool de servidores 2015 de negócios para um Pool do Lync Server 2013

Este exemplo move os comunicados de números não atribuídos do pool de origem (Skype para Business Server 2015) para o pool de destino (Lync Server 2013).

```
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf Data
<a name="WebConfData"> </a>

A ferramenta da Web Conf dados permite que um administrador do Skype Business Server 2015 software de comunicações para ter mais controle sobre os dados associados a conferências da Web do organizador. Cenários incluem a capacidade de excluir dados de reunião de um usuário específico, com base em um critério de carimbo de data / hora.

### <a name="description"></a>Descrição

Esta ferramenta permite ao administrador executar as seguintes operações:

1. Encontrar todos os dados de webconferência associados a um único usuário.

2. Excluir todos os dados de webconferência associados a um único usuário.

3. Excluir todos os dados de webconferência associados a um único usuário que sejam anteriores à determinada data.

4. Mover todos os dados de webconferência associados a um único usuário quando o usuário for movido de um pool para outro.

> [!NOTE]
> Ferramentas do Resource Kit do Lync Server 2010 suporte para mover todos os dados de conferência da Web associados a um único usuário quando o usuário é movido de um pool para outro. Essa funcionalidade agora foi preterida nesta ferramenta em favor do parâmetro **MoveConferenceData**. Para obter detalhes sobre esse parâmetro, consulte o cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .

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

![Parâmetros da ferramenta Web Conf Data.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

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


