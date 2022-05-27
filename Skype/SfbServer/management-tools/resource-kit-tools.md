---
title: Skype for Business Server documentação das Ferramentas do Kit de Recursos de 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: Este artigo descreve as ferramentas no Kit de Recursos do Skype for Business Server 2015, incluindo a finalidade de cada ferramenta e exemplos de seu uso. O Skype for Business Server 2015 Resource Kit ajuda a facilitar as tarefas rotineiras para os administradores de TI que implantam e gerenciam o Skype for Business Server 2015. Por exemplo, a ferramenta Web Conf Data pode ser usada para controlar facilmente os dados carregados pelos usuários durante uma reunião online. A ferramenta SEFAUtil pode ser usada para configurar o encaminhamento de chamadas de representante e a resposta para os usuários. Incentivamos os administradores de TI a usar essas ferramentas para gerenciar com mais eficiência o Skype for Business Server 2015.
ms.openlocfilehash: 83777dbe16e70030b13c07fced716ffbc4d51f35
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675493"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Skype for Business Server documentação das Ferramentas do Kit de Recursos de 2015

Este artigo descreve as ferramentas no Kit de Recursos do Skype for Business Server 2015, incluindo a finalidade de cada ferramenta e exemplos de seu uso. O Skype for Business Server 2015 Resource Kit ajuda a facilitar as tarefas rotineiras para os administradores de TI que implantam e gerenciam o Skype for Business Server 2015. Por exemplo, a **ferramenta Web Conf Data** pode ser usada para controlar facilmente os dados carregados pelos usuários durante uma reunião online. A **ferramenta SEFAUtil** pode ser usada para configurar o encaminhamento de chamadas de representante e a resposta para os usuários. Incentivamos os administradores de TI a usar essas ferramentas para gerenciar com mais eficiência o Skype for Business Server 2015.

## <a name="installation-of-the-resource-kit-tools"></a>Instalação das Ferramentas do Kit de Recursos

Para instalar o Skype for Business Server 2015 Resource Kit, baixe [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) do Centro de Download.

Execute **OCSResKit.msi** para fazer uma instalação simples. O .msi instala todas as ferramentas no seguinte caminho: %Arquivos de Programas **%\Skype for Business Server 2015\ResKit**. As ferramentas que são executáveis autossuficiente estão nesta pasta. As ferramentas que também têm arquivos de suporte estão em suas próprias subpastas.

## <a name="supported-environments"></a>Ambientes com suporte

O kit de recursos do Skype for Business Server 2015 deve ser instalado em um servidor que atenda às especificações necessárias para o Skype for Business Server 2015, geralmente um sendo usado para executar o Skype for Business Server 2015.

## <a name="resource-kit-tools-overview"></a>Visão geral das Ferramentas do Kit de Recursos

A seguir está uma lista das ferramentas fornecidas no Kit de Recursos Skype for Business Server 2015. Uma descrição de cada ferramenta, incluindo os requisitos e o uso de exemplo, é abordada nas seções a seguir.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Monitor do Serviço de Política de Largura de Banda](resource-kit-tools.md#bpsm)

- [Analisador de Utilização de Largura de Banda](resource-kit-tools.md#bua)

- [Chamar Parkometer](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Importar Armazenamento de serviço](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Console do Usuário de Pesquisa](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Visualizador de Configuração de Rede](resource-kit-tools.md#NCV)

- [Agente do Grupo de Resposta Ativo](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [Migração de comunicados de número não atribuído](resource-kit-tools.md#UNAM)

- [Dados de Web Conf](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

A ferramenta de Configuração do Serviço de Catálogo de Endereços (ABSConfig) é uma ferramenta administrativa que ajuda os administradores a personalizar a configuração do Serviço de Catálogo de Endereços no Skype for Business Server 2015. Essa ferramenta também permite que Skype for Business Server 2015 restaure as configurações padrão do Serviço de Catálogo de Endereços.

### <a name="description"></a>Descrição

ABSConfig é um aplicativo de interface gráfica do usuário que permite que os administradores configurem Active Directory Domain Services atributos relacionados ao Serviço de Catálogo de Endereços.

Os principais cenários da ferramenta são os seguintes:

- Para permitir que os administradores mapeiem atributos Active Directory Domain Services para os atributos do Skype for Business Server 2015.

- Para permitir que os administradores especifiquem Active Directory Domain Services atributo a ser incluído ou excluído nos arquivos do Serviço de Catálogo de Endereços.

- Para permitir que os administradores restaurem, as configurações padrão do Serviço de Catálogo de Endereços.

A ferramenta ABSConfig pode ser iniciada usando o ABSConfig.exe arquivo. A ferramenta é aberta na **guia Configurar Atributos**. Esta tabela tem opções para mapear Active Directory Domain Services atributos para os campos de atributo do Skype for Business Server 2015 e especificar quais usuários incluir ou excluir em arquivos do Serviço de Catálogo de Endereços com base em filtros de atributo específicos. Ele também tem opções para personalizar qual valor do número de telefone a ser incluído no arquivo do Catálogo de Endereços. A **opção Restaurar Padrões permite** que os administradores restaurem as configurações do Serviço de Catálogo de Endereços para valores padrão.

> [!NOTE]
> O novo mapeamento de atributos do AD para nomes de campo OC diferentes funcionará apenas para Download de Arquivo do Catálogo de Endereços e não tem suporte da Consulta Web do Catálogo de Endereços.

### <a name="output"></a>Saída

ABSConfig armazena a configuração do Serviço de Catálogo de Endereços no banco de dados.

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Objetivo

ABSConfig fornece uma maneira rápida e fácil de personalizar Skype for Business Server Catálogo de Endereços 2015.

### <a name="requirements"></a>Requisitos

#### <a name="computer"></a>Computador

ABSConfig pode ser executado somente de um computador ingressado no domínio que tenha Skype for Business Server 2015 instalado. No caso do Skype for Business Server 2015, Edição Enterprise, essa ferramenta pode ser executada em qualquer servidor Front-End que tenha o Serviço de Catálogo de Endereços habilitado durante a instalação.

#### <a name="network"></a>Rede

O computador deve ser capaz de se conectar ao pool Front-End e ao banco de dados de back-end.

#### <a name="software"></a>Software

Os seguintes componentes de software devem ser instalados antes de executar a ferramenta ABSConfig:

- Skype for Business Server 2015

#### <a name="users"></a>Usuários

Administradores que têm as permissões necessárias para atualizar a implantação Skype for Business Server 2015.

### <a name="examples"></a>Exemplos

ABSConfig pode ser iniciado digitando **ABSConfig.exe** em um prompt de comando. Veja abaixo a interface do usuário da ferramenta ABSConfig.

![A ABSConfig.exe ferramenta.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Resumo

A ferramenta ABSConfig fornece aos administradores uma ferramenta rápida e fácil de usar para personalizar Skype for Business Server Serviço de Catálogo de Endereços 2015.

## <a name="bandwidth-policy-service-monitor"></a>Monitor do Serviço de Política de Largura de Banda
<a name="bpsm"> </a>

A ferramenta Monitor do Serviço de Política de Largura de Banda destina-se a permitir que os administradores exibam uma lista do seguinte:

1. Todos os serviços de Política Skype for Business Server 2015 (Autenticação e Núcleo) configurados na topologia

2. As conexões que cada serviço faz com outros serviços de Política de Largura de Banda e com os servidores de Borda

3. Todos os links configurados no documento de configuração de rede e no uso de largura de banda em tempo real, conforme relatado por cada um dos serviços de Política de Largura de Banda

### <a name="description"></a>Descrição

A ferramenta Monitor do Serviço de Política de Largura de Banda é implementada como um aplicativo baseado em GUI. Os administradores iniciam a ferramenta executando PDPMonUI.exe.

Quando a ferramenta é iniciada, ela tenta descobrir a lista de serviços de Política de Largura de Banda na topologia. Após a conclusão da atualização inicial, o painel à esquerda da janela é preenchido com uma lista de serviços agrupados pelos clusters aos quais pertencem.

Quando os administradores selecionam um Serviço de Política de Largura de Banda específico, o painel à direita exibe as informações sobre esse serviço específico. Esse painel também tem duas guias principais que exibem informações.

#### <a name="machine-info-tab"></a>Guia Informações do Computador

A **guia Informações do** Computador mostra os detalhes do Serviço de Política de Largura de Banda selecionado e a lista e o estado de todas as conexões feitas pelo Serviço de Política de Largura de Banda selecionado para outros serviços.

#### <a name="topology-info-tab"></a>Guia Informações de Topologia

A **guia Informações de Topologia** mostra uma lista de todos os links que estão definidos nas definições de configuração de rede. Para cada link, a capacidade de largura de banda de áudio e vídeo é exibida. Além disso, a largura de banda utilizada no momento é exibida, tanto em Kbps quanto como um percentual da capacidade. A ferramenta usa a codificação de cores para realçar links que têm utilização próxima à capacidade. Isso permite que os administradores isolem rapidamente esses links.

> [!NOTE]
>  Se a ferramenta Monitor do Serviço de Política de Largura de Banda apresentar falha ao se conectar a qualquer um dos serviços de Política de Largura de  Banda configurados, as informações nas guias Informações do Computador e Informações de **Topologia** não serão preenchidas. No entanto, é possível que a ferramenta possa se conectar inicialmente, mas, posteriormente, perder sua conexão com o serviço. Nesses casos, os administradores podem ver informações desatualizadas. Há um carimbo **de data** /hora da Última Atualização em cada uma das guias que podem permitir que os administradores vejam quando os dados foram atualizados pela última vez para um Serviço de Política de Largura de Banda específico.

### <a name="output"></a>Saída

Não há saída de linha de comando; a saída do programa está contida na GUI (interface gráfica do usuário) principal.

### <a name="purpose"></a>Objetivo

A finalidade da ferramenta Monitor do Serviço de Política de Largura de Banda é permitir que os administradores visibilidade do estado de cada um dos serviços de Política de Largura de Banda definidos na topologia. Além disso, os administradores podem ver o uso de largura de banda em tempo real para todos os links definidos no documento de configuração de rede.

### <a name="requirements"></a>Requisitos

A ferramenta Monitor do Serviço de Política de Largura de Banda precisa ser executada em um computador que faz parte Skype for Business Server topologia.

### <a name="summary"></a>Resumo

A ferramenta Monitor do Serviço de Política de Largura de Banda pode ser um recurso valioso para os administradores para que eles possam inspecionar o estado de todos os serviços de Política de Largura de Banda na topologia, e o mais importante, eles podem obter a utilização de largura de banda em tempo real para os links definidos nas definições de configuração de rede.

## <a name="bandwidth-utilization-analyzer"></a>Analisador de Utilização de Largura de Banda
<a name="bua"> </a>

O Analisador de Utilização de Largura de Banda é uma ferramenta que cria relatórios sobre várias exibições de consumo de largura de banda pelos pontos de extremidade de UC em links WAN na rede corporativa. Esses relatórios podem ser usados para entender o padrão de consumo de largura de banda atual e para auxiliar no planejamento da capacidade de largura de banda.

### <a name="description"></a>Descrição

O Analisador de Utilização de Largura de Banda é implementado como um aplicativo baseado em GUI. Essa ferramenta gera relatórios especificamente para utilização de áudio em toda a rede e ajuda no planejamento de capacidade. Ele também itera na capacidade de largura de banda atribuída a vários links.

### <a name="output"></a>Saída

O Analisador de Utilização de Largura de Banda fornece gráficos de capacidade de largura de banda e utilização de áudio para todos os links WAN configurados no sistema.

### <a name="purpose"></a>Objetivo

Em qualquer implantação de voz e vídeo, é essencial monitorar e entender a tendência de utilização de largura de banda do tráfego de mídia em toda a rede corporativa. A ferramenta Analisador de Utilização de Largura de Banda permite que um administrador obtenha exatamente isso. Essa ferramenta faz o seguinte:

- Gera relatórios específicos para utilização de áudio em toda a rede

- Ajuda com o planejamento e a iteração de capacidade mais eficazes na capacidade de largura de banda atribuída a vários links

O Analisador de Utilização de Largura de Banda pode gerar gráficos de relatórios de capacidade e utilização de largura de banda; eles são os seguintes:

- Todos os links WAN na rede corporativa

- Filtrados por links WAN selecionados que foram escolhidos

- Filtrados por links WAN que excederam a capacidade do link

- Filtrados por links WAN que estão sub utilizando a largura de banda provisionada

- Filtrar por links WAN que atingiram níveis críticos (uma utilização de largura de banda maior que 90% da capacidade de largura de banda do link WAN)

- Filtrado por tipo de link WAN – links de site de rede, links inter-regiões e links dentro de um site

- Filtrado por região de rede

#### <a name="applications"></a>Aplicativos

O Analisador de Utilização de Largura de Banda tem os dois aplicativos a seguir (ferramentas):

- **WanLinkLogCollector.exe** Essa ferramenta permite que seu usuário insira as informações necessárias.

- **BandwidthUtilizationAnalyzer.xlsm** Um relatório de software de Microsoft Excel planilha é iniciado automaticamente pelo WanLinkLogCollector.exe. Esse aplicativo permite que o usuário aplique filtros ao relatório, conforme mostrado posteriormente neste artigo.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fases do uso do Analisador de Utilização de Largura de Banda

Há duas fases ao usar o Analisador de Utilização de Largura de Banda:

- Coletar logs, que são executados usando WanLinkLogCollector.exe

- Personalizar relatórios, que são executados usando BandwidthUtilizationAnalyzer.xlsm

  > [!IMPORTANT]
  > É altamente recomendável que BandwidthUtilizationAnalyzer.xlsm não seja iniciado manualmente pelos usuários finais.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Iniciando o Analisador de Utilização de Largura de Banda

Inicie WanLinkLogCollector.exe no prompt de comando ou usando Windows Explorer.

 **Usando WanLinkLogCollector.exe**

Há três etapas para usar WanLinkLogCollector.exe:

1. **Registrar a linha do tempo** Forneça a linha do tempo para a qual o relatório precisa ser gerado

2. **Especificar os diretórios de arquivos** Fornecer informações de localização do arquivo

3. **Coletar os logs e iniciar o visualizador de relatórios** Execute o comando para gerar o relatório

#### <a name="step-1---log-the-timeline"></a>Etapa 1 – Registrar em log a linha do tempo

Registrar em log a linha do tempo permite que o usuário da ferramenta especifique o seguinte, conforme mostrado na figura abaixo.

1. **Data de início** Esta é a data de início da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 1º de agosto de 2010.

2. **Data de término** Esta é a data de término da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 30 de setembro de 2010.

     ![Datas de início e término na utilização da largura de banda A.](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Etapa 2 – Especificar os diretórios de arquivo

Os diretórios de arquivos a seguir podem ser especificados pelo usuário, conforme mostrado.

- **Local dos arquivos de log do servidor** O local da pasta em que os logs do servidor de política de largura de banda são armazenados. Normalmente, isso é<\<fileserver\>\\ de FE\>\AppServerFiles\PDP.

- **Local de armazenamento de arquivos temporário** O local do arquivo temporário em que os arquivos intermediários são armazenados enquanto o relatório está sendo gerado.

  ![Diretórios de arquivo no Anal de Utilização de Largura de Banda.](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

  > [!NOTE]
  > Verifique se o acesso de arquivo suficiente aos logs do servidor e à pasta de repositório de arquivos temporários é fornecido ao usuário da ferramenta.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Etapa 3 – Coletar os logs e iniciar o visualizador de relatórios

Para coletar os logs e iniciar o visualizador de relatórios, clique em **Executar** , conforme mostrado abaixo. Esta etapa coleta os dados necessários.

![Coletando dados na Análise de Utilização de Largura de Banda.](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Quando a validação de entrada for bem-sucedida, a mensagem mostrada abaixo será exibida.

![Registra a notificação coletada no Utili de Largura de Banda.](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Clique em **OK**. BandwidthUtilizationAnalyzer.xlsm é iniciado automaticamente. Siga as instruções na caixa de mensagem. Para obter detalhes, **consulte Using BandwidthUtilizationAnalyzer.xlsm** na próxima seção.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Usando BandwidthUtilizationAnalyzer.xlsm

1. Quando BandwidthUtilizationAnalyzer.xlsm for iniciado automaticamente, clique em **Atualizar** , conforme mostrado abaixo.

     ![BandwidthUtilizationAnalyzer.xlsm.](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Quando uma pasta de arquivos for aberta, selecione consolidated.csv local especificado na caixa de mensagem, conforme mostrado abaixo. Ele também mostra o local como **C:\Temp**.

     ![Abrir uma pasta em BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Clique em **Importar**.

4. O gráfico é gerado automaticamente. Ele está disponível quando o ponteiro de trabalho em segundo plano desaparece.

     ![Aplicando filtros no Modo de Exibição de Relatório.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Aplicando filtros à exibição de relatório

Os filtros que podem ser aplicados à exibição de relatório, conforme mostrado abaixo, são descritos da seguinte maneira:

![Aplicando filtros no Modo de Exibição de Relatório.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Nome** Filtrar por links WAN (o filtro está no lado direito do grafo). O prefixo indica os seguintes tipos de link; consulte a caixa vertical (azul):

   - **Site S** O link wan de um site de rede para uma região de rede

   - **IS Entre Sites** O link wan entre dois sites de rede

   - **R Entre Regiões** O link wan entre duas regiões de rede

2. **Limite excedido** Filtrar por links WAN cuja utilização de largura de banda é maior que a capacidade de largura de banda

3. **Níveis críticos** Filtrar por links WAN cuja utilização de largura de banda atingiu 90% ou mais do que a capacidade de largura de banda

4. **Subutildo** Filtrar por links WAN cuja utilização de largura de banda tenha sido inferior a 25% da capacidade de largura de banda

5. **Tipo de link** Filtre pelos seguintes tipos de links WAN:

   - **Tipo de site de** rede

   - **Tipo entre sites**

   - **Tipo de link entre regiões**

6. **Região** Filtrar por região de rede

As figuras a seguir mostram os filtros descritos anteriormente.

Filtrar por **Nome**. Selecione a lista de links que precisam ser exibidos no grafo.

![Filtragem por nome em BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filtrar **por limite excedido**. Selecione **True** para impor o filtro.

![Filtragem por limite excedido.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtrar por **níveis críticos**. Selecione **True** para impor o filtro.

![Filtragem por níveis críticos.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtrar **por Subutildo**. Selecione **True** para impor o filtro.

![Filtragem por Subutilizando.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtrar por **Tipo de Link**. Selecione o tipo ou os tipos que precisam ser exibidos.

![Filtragem por tipo de link.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtrar por **região**. Selecione uma lista de regiões cujos links precisam ser exibidos.

![Filtragem por região.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Requisitos

- O .NET Framework 3.5

- Microsoft Excel 2010 ou Excel 2007

### <a name="summary"></a>Resumo

O Analisador de Utilização de Largura de Banda é usado para plotar a utilização de largura de banda de áudio para o tráfego de UC em toda a rede. Essa ferramenta também pode ser usada para relatar a utilização da largura de banda de vídeo na rede.

## <a name="call-parkometer"></a>Chamar Parkometer
<a name="callpark"> </a>

Chamar o Parkometer é um aplicativo de linha de comando que fornece acesso fácil ao banco de dados de órbita do Estacionamento de Chamada.

### <a name="description"></a>Descrição

Chamar o Parkometer é uma ferramenta para acompanhar chamadas estacionadas no momento. Ele também coleta estatísticas sobre órbitas e uso do CPS (Servidor de Estacionamento de Chamada). Essa ferramenta de linha de comando fornece acesso de leitura e gravação à órbita do CPS SQL Server banco de dados de um computador conectado local ou remotamente.

Todas as opções são mutuamente exclusivas. A sintaxe da linha de comando é a seguinte:

- **-o** parâmetro — lista todos os intervalos de órbita configurados para esse pool.

- **-n** parâmetro — lista todas as órbitas usadas atualmente neste pool. As informações exibidas são as seguintes:

  - URI (Uniform Resource Identifier) sip do parkee e parker.

  - Nome do host do CPS onde a chamada está estacionada.

  - Carimbo de data/hora de quando a chamada foi estacionada.

- **-f** parameter — lista o número de órbitas livres no pool no momento.

- **-r \<n\>** parâmetro – lista as últimas \<n\> chamadas estacionadas. As informações exibidas são as seguintes:

  - URI SIP parkee.

  - Parker SIP URI.

  - Nome do host do CPS onde a chamada foi estacionada.

  - Carimbo de data/hora de quando a chamada foi recuperada ou descartada.

- **-t\<n\>** parâmetro – testa a reserva de uma órbita no banco de dados para mostrar a aleatoriedade dos números de órbita atribuídos.

### <a name="output"></a>Saída

Dependendo dos parâmetros de entrada especificados em um prompt de comando, o Estacionamento de Chamada exibe a seguinte saída:

- Todos os intervalos de órbita configurados para esse pool

- Chamadas estacionadas no momento

- Número de órbitas livres (disponíveis)

- Chamadas estacionadas recentemente

- Órbitas reservadas para testar valores de órbita uniformes e aleatórias

### <a name="purpose"></a>Objetivo

A finalidade da ferramenta CPS é fornecer acesso de linha de comando ao banco de dados CPS. O administrador pode exibir o uso do CPS e determinar o número de órbitas atribuídas a um pool.

### <a name="requirements"></a>Requisitos

Não há requisitos se essa ferramenta for executada no mesmo computador que está executando o CPS. Se essa ferramenta for executada em um computador remoto, o banco de dados SQL Server usado pelo Skype for Business Server 2015 deverá ser configurado para permitir o acesso remoto. O Parkometer de chamada deve ser configurado com uma cadeia SQL Server de conexão do banco de dados para se conectar ao banco de dados do pool SQL Server. Essa SQL Server de conexão de banco de dados é definida no arquivo de configuração, **parkometer.exe.config**. Ele deve ser colocado no mesmo diretório em que parkometer.exe está localizado. O arquivo XML a seguir é um exemplo de um parkometer.exe.config. Os parâmetros que devem ser configurados são nome de usuário (por exemplo, mydomain\Administrator), senha (por exemplo, mypassword) e nome do host (por exemplo, myserver).

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

Intervalos de órbita implantados: o parâmetro -o lista todos os intervalos de órbita configurados para esse pool, conforme mostrado

![Intervalos de órbita em Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Chamadas estacionadas no momento: o parâmetro -n lista todas as órbitas usadas no momento neste pool, conforme mostrado

![Chamadas estacionadas no estacionamento de chamadas.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Número de órbitas livres: o parâmetro -f lista o número de órbitas livres no pool no momento, conforme mostrado

![Órbitas livres em Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Chamadas estacionadas recentemente: o parâmetro -r \<n\> lista as últimas \<n\> chamadas estacionadas, conforme mostrado

![Chamadas estacionadas recentemente no Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Testar a reserva de órbita: os testes de parâmetro -t \<n\> reservando uma órbita no banco de dados, conforme mostrado

![Testar reservas de órbita no Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Resumo

Call Parkometer é uma ferramenta de linha de comando que fornece informações detalhadas sobre o Servidor de Estacionamento de Chamada.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Descrição

DBAnalyze é uma ferramenta de linha de comando que ajuda os administradores a coletar relatórios de análise sobre os bancos de dados Skype for Business Server 2015. O DBAnalyze tem os seguintes modos: diagnóstico, dados do usuário, conferência, MCUs e fragmentação de disco:

- **Modo de diagnóstico** Cria um relatório que inclui informações sobre tabelas (número de registros, fragmentação, tamanho dos dados e tamanho do índice), tamanhos de arquivos de dados e de log, o último tempo de backup, distribuição de contatos entre servidores que estão executando o Microsoft Office Communications Server, o número médio de permissões, contatos, contêineres, assinaturas, publicações, pontos de extremidade por usuário, quaisquer usuários hospedados incorretamente, usuários que não podem ser roteados,  o número médio de conferências organizadas por usuário, conferências agendadas, conferências ativas e a versão do banco de dados.

    > [!NOTE]
    > A execução do modo de diagnóstico pode afetar o desempenho do servidor.

- **Modo de dados do usuário** Relata dados de contato, contêiner, assinatura, publicação, permissão e grupo de contatos para um usuário especificado ou para usuários que têm esse usuário em suas listas de contatos e permissões. Esse modo também relata dados de resumo para conferências que um usuário organiza ou é convidado.

- **Modo de conferência** Relata dados detalhados de uma conferência específica, incluindo todos os detalhes de tempo de agendamento para a conferência, a lista de convidados, a lista de tipos de mídia permitidos para a conferência, MCUs ativos (unidades de controle multipoint), a lista de participantes ativos e o estado de sinalização de cada participante.

- **Decodificar A ID da Reunião** Decodifica uma ID de reunião PSTN (rede telefônica pública comuada) especificada pelo comutador **/pstnid** , mas não se conecta ao back-end para obter informações detalhadas.

- **Resolver conferência** Decodifica uma ID de reunião PSTN especificada pela opção **/pstnid** e exibe informações sobre a conferência indicada pela ID.

- **Modo MCUs** Relata a ID, o tipo de mídia, a URL, o status da pulsação, a carga de conferência e a carga do participante para cada MCU no pool.

- **Modo de fragmentação de disco** Exibe o status de fragmentação de todos os discos.

Essa ferramenta pode ser usada para diagnosticar vários problemas ou para ajudar os administradores com o planejamento de capacidade. Por exemplo, se a maioria dos usuários hospedados no servidor A escolher usuários hospedados no servidor B como seus contatos, o administrador poderá mover os usuários no servidor A para o servidor B para reduzir o tráfego entre servidores.

### <a name="output"></a>Saída

Essa ferramenta gera relatórios predefinidos sobre o banco de dados Skype for Business Server 2015. **Caminho**: %ProgramFiles%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>Objetivo

Para instalar Dbanalyze.exe, copie-o para uma pasta local e execute a ferramenta. Para usar a ferramenta, execute o comando a seguir na linha de comando. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` As descrições das opções de linha de comando são mostradas abaixo.

![Opções de linha de comando para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Requisitos

 **Computador** O DBAnalyze só pode ser executado em um computador ingressado no domínio que tenha Skype for Business Server 2015 instalado.

 **Rede** O computador deve ser capaz de se conectar ao banco de dados de back-end.

 **Os** componentes Skype for Business Server software 2015 devem ser instalados antes de executar o DBAnalyze.

 **Usuários** A tabela a seguir mostra os administradores que têm as permissões necessárias para acessar Skype for Business Server 2015.

![Tabela de permissões para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Uma conta de administrador local é necessária para **o modo /report:disk** .

### <a name="examples"></a>Exemplos

A seguir estão exemplos de comandos Dbanalyze.exe válidos:

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Resumo

O DBAnalyzer fornece aos administradores uma análise rápida e fácil de Skype for Business Server 2015.

## <a name="import-storage-service-data"></a>Importar Armazenamento de serviço
<a name="Issd"> </a>

A ferramenta de kit de recursos ImportStorageServiceData permite reimportar dados de fila e ponto de extremidade que foram liberados do serviço Armazenamento (LYSS) de volta para o serviço Armazenamento.

### <a name="description"></a>Descrição

Os dados liberados do serviço Armazenamento podem ter sido automáticos (periódicos) com base no status do Item de Fila ou no tamanho do banco de dados. Isso pode ter acontecido devido à invocação manual do cmdlet de failover do pool ou ao cmdlet StorageServiceFullFlush (invocado pelo cmdlet de failover do pool). Observe que o ideal é que os dados não sejam reimportados se qualquer um dos tamanhos de banco de dados do serviço Armazenamento (LYSS) nos front-ends estiver acima do nível normal, pois isso provavelmente fará com que mais dados sejam exportados novamente. Além disso, todos os problemas que poderiam ter contribuído para erros que causaram o aumento da Fila de Serviço do Armazenamento devem primeiro ser resolvidos Exchange (por exemplo, erros de ponto de extremidade, problemas de rede ou outros problemas).

 **Cenário 1: durante** o failover do pool, os arquivos podem ser liberados do serviço de armazenamento para cada front-end. Depois que o failover for concluído, a ferramenta deverá ser executada para reimportar os dados.

 Cenário **2:** os dados estão sendo liberados automaticamente todos os dias ou em resposta ao banco de dados de serviço do Armazenamento excedendo determinados limites de tamanho (por exemplo, 60%, 80%, 90% cheio). Esses dados liberados automaticamente devem ser reimportados rotineiramente pelo administrador. Na situação acima, se o pacote SCOM de monitoramento não for implantado, haverá eventos para o serviço Skype for Business Server Armazenamento relacionados aos dados que estão sendo liberados do serviço de Armazenamento. IDs de evento 32075 (operação de liberação completa iniciada), 32076 (liberação completa concluída), 32082 (liberação de nível de manutenção iniciada), 32083 (liberação de nível de manutenção concluída), 32089 (liberação ocorreu devido ao preenchimento do banco de dados). Observe que essas IDs de evento correspondem à versão RTM. Quando um administrador vê esses eventos, isso significa que há arquivos que foram liberados. Esses dados devem ser importados rotineiramente usando essa ferramenta, por exemplo, uma vez por semana.

Para a versão do Serviço Online, se o pacote SCOM de monitoramento de integridade para Skype for Business Server for implantado, haverá novos alertas que podem ser gerados que solicitam ao administrador que reporte os dados liberados de volta para o serviço Armazenamento. Haverá um evento correspondente no log de eventos no servidor Front-End que disparou o alerta. O evento fornecerá uma descrição do caminho pai no qual os arquivos de dados liberados estão localizados e quantos arquivos existem que atendem aos critérios de alerta. Os critérios de alerta são que há X ou mais arquivos no caminho pai específico que têm pelo menos Y dias (em que X e Y são predefinidos no StorageService, mas podem ser substituídos alterando o arquivo APPCONFIG.) Dois exemplos de eventos que podem disparar o alerta de integridade são mostrados abaixo, com a diferença sendo o caminho pai. Uma possibilidade está no compartilhamento de arquivos do serviço Web, enquanto a outra possibilidade é o diretório local de Dados do Aplicativo de cada front-end. (por exemplo, c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService). Em seguida, o administrador executará essa ferramenta de reskit.

Essa ferramenta aumentará a carga de CPU e E/S no front-end em que está sendo executada e em outros front-ends, na situação em que os dados não pertencem ao front-end em que a ferramenta é executada. É recomendável executar essa ferramenta quando os front-ends não estão sob carga pesada de CPU e E/S, por exemplo, fora do horário de pico. Em segundo lugar, essa ferramenta pode de 2 a 3 minutos para importar um arquivo de dados. Tenha isso em mente ao estimar por quanto tempo a ferramenta estará em execução. O arquivo de log detalhado gerado pela ferramenta será exibido por padrão no Repositório de Arquivos. Exclua-o se não houver erros relatados, pois o arquivo de log pode ter dezenas de MB ou mais.

![Exemplo de Armazenamento de log de eventos do servidor.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Requisitos

Instale as Skype for Business Server ferramentas do Kit de Recursos 2015. A ferramenta é executada em computadores ingressados no domínio em que Skype for Business Server e Skype for Business Server Shell de Gerenciamento estão instalados. A ferramenta usa um cmdlet do shell de gerenciamento para identificar todos os Front-End servidores no pool. Em segundo lugar, a ferramenta deve ser executada de um computador no pool que tem o **banco de dados RtcLocal** instalado. Esse banco de dados é usado pela ferramenta para recuperar o local do compartilhamento de arquivo WEBSERVICE para o pool. Além disso, antes de usar a ferramenta, cada servidor Front-End deve primeiro habilitar a comunicação remota usando **Enable-PSRemoting** em cada servidor Front-End e Windows PowerShell o computador do qual a ferramenta é executada. Caso contrário, Windows PowerShell comandos remotos dessa ferramenta falharão. Windows PowerShell a comunicação remota pode ser desativada em todos os Front-End no pool após sua conclusão. Por fim, a conta ou credencial que invoca a ferramenta deve ter permissão de leitura/gravação para o compartilhamento de arquivos de serviço Web para o pool em que está executando essa ferramenta. Caso contrário, a ferramenta falhará com erros de Permissão de E/S.

> [!NOTE]
> No Windows Server 2012, Windows PowerShell comunicação remota está habilitada por padrão, mas não no sistema operacional Windows Server 2008.

### <a name="examples"></a>Exemplos

```console
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

A ferramenta LCSSync ajuda a implantar Skype for Business Server software de comunicação 2015 em um ambiente de várias florestas. Essa ferramenta é usada para sincronizar usuários e grupos de diferentes florestas de usuários como um objeto Active Directory Domain Services contato com uma floresta central em que o Skype for Business Server 2015 está instalado.

### <a name="description"></a>Descrição

 O LCSSync usa os objetos de Active Directory Domain Services sincronizados na floresta central para habilitar os usuários para Skype for Business Server. Para fornecer logon único, a conta de usuário principal deve ser mapeada para o objeto Active Directory Domain Services contato na floresta central para Skype for Business Server 2015. Essa ferramenta ajuda a executar esse mapeamento. Essa ferramenta fornece modelos para criar Agentes de Gerenciamento no Microsoft Identity Integration Server.

### <a name="summary"></a>Resumo

A ferramenta LCSSync ajuda a implantar o Skype for Business Server 2015 em um ambiente de várias florestas.

## <a name="lookup-user-console"></a>Console do Usuário de Pesquisa
<a name="LUC"> </a>

A ferramenta LookupUserConsole exibe informações Skype for Business Server roteamento internos sobre usuários específicos. Essas informações podem ser úteis para o suporte pessoal da Microsoft no diagnóstico de problemas de implantação e roteamento.

### <a name="description"></a>Descrição

 A execução LookupUserConsole.exe abrirá um prompt de comando que aceita endereços SIP e tenta exibir informações de roteamento Skype for Business Server internas relacionadas a eles. Digite **a saída** para sair da ferramenta LookupUserConsole.

### <a name="requirements"></a>Requisitos

Instale o Skype for Business Server 2015 Resource Kit. A ferramenta é executada em computadores ingressados no domínio Skype for Business Server está instalado.

### <a name="examples"></a>Exemplos

C:\Arquivos de Programas\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe

```console
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

A ferramenta MSTurnPing permite que um administrador do software de comunicações do Skype for Business Server 2015 verifique o status dos servidores que executam os serviços de Borda de Áudio/Vídeo, Autenticação de Áudio/Vídeo e os servidores que executam os Serviços de Política de Largura de Banda na topologia.

### <a name="description"></a>Descrição

A ferramenta MSTurnPing permite que um administrador do software de comunicações do Skype for Business Server 2015 verifique o status dos servidores que executam os serviços de Borda de Áudio/Vídeo, Autenticação de Áudio/Vídeo e os servidores que executam os Serviços de Política de Largura de Banda na topologia.

A ferramenta permite que o administrador execute os seguintes testes:

1. Teste do Servidor de Borda A/V: a ferramenta executa testes em todos os Servidores de Borda A/V na topologia fazendo o seguinte:

   - Verificar se o serviço Skype for Business Server autenticação de áudio/vídeo foi iniciado e pode emitir as credenciais apropriadas.

   - Verificar se o serviço Skype for Business Server de Borda de Áudio/Vídeo foi iniciado e pode alocar os recursos na borda externa com êxito.

2. Teste do Serviço de Política de Largura de Banda: a ferramenta executa testes em todos os servidores que estão executando os Serviços de Política de Largura de Banda na topologia fazendo o seguinte:

   - Verificar se o serviço Skype for Business Server Política de Largura de Banda (Autenticação) foi iniciado e pode emitir as credenciais apropriadas.

   - Verificar se o serviço Skype for Business Server de Política de Largura de Banda (Core) foi iniciado e se pode executar a verificação de largura de banda com êxito.

Essa ferramenta deve ser executada em um computador que faz parte da topologia e tem o repositório local instalado.

### <a name="output"></a>Saída

A ferramenta gera os resultados de cada uma das operações.

- Se o **teste AudioVideoEdgeServer** for executado, as saídas da ferramenta serão as seguintes:

  - Os resultados de teste dos computadores que fornecem o serviço Skype for Business Server Autenticação de Áudio/Vídeo do Skype for Business Server 2015 na topologia

  - Os resultados do teste dos computadores que fornecem o Skype for Business Server de Borda de Áudio/Vídeo 2015 na topologia

- Se o **teste BandwidthPolicyServer** for executado, as saídas da ferramenta serão as seguintes:

  - Os resultados do teste dos computadores que fornecem o Skype for Business Server de Política de Largura de Banda (Autenticação) do Skype for Business Server 2015 na topologia

  - Os resultados do teste dos computadores que fornecem o Skype for Business Server De política de largura de banda (Core) do Skype for Business Server 2015 na topologia

### <a name="requirements"></a>Requisitos

- Essa ferramenta deve ser executada em um computador que esteja na topologia e que tenha o repositório local.

- A ferramenta deve ser executada como um administrador que tenha acesso ao repositório local.

### <a name="examples"></a>Exemplos

A seguir está um exemplo da entrada da ferramenta.

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso Skype for Business Server administradores de 2015 que desejam verificar o status dos servidores que executam serviços de política de áudio/vídeo e largura de banda.

## <a name="network-configuration-viewer"></a>Visualizador de Configuração de Rede
<a name="NCV"> </a>

O Visualizador de Configuração de Rede pode ser usado pelos administradores de software de comunicação do Skype for Business Server 2015 para exibir a topologia de rede do CAC (controle de admissão de chamadas) para uma empresa provisionada para permitir sessões de comunicação em tempo real, como chamadas de voz ou vídeo com base na capacidade de largura de banda especificada. Skype for Business Server 2015 define as políticas do CAC, que são impostas pelos serviços de Política de Largura de Banda instalados com o Skype for Business Server 2015.

### <a name="description"></a>Descrição

O Visualizador de Configuração de Rede (NetworkConfigurationViewer.exe) permite que os administradores executem as seguintes tarefas:

- Carregue e exiba a topologia de rede do CAC de uma implantação Skype for Business Server 2015 em um formato gráfico.

- Carregue e exiba a topologia de rede do CAC de um arquivo de log do Servidor de Política de Largura de Banda em um formato gráfico.

- Salve e armazene a topologia de rede do CAC em um formato XML no disco.

- Salve e armazene o diagrama de topologia de rede do CAC no formato JPG ou BMP.

- Exibir dados de configuração de topologia de rede do CAC.

- Exiba a topologia de rede do CAC em um estilo de exibição de árvore.

- Defina conectores personalizados para links de topologia de rede do CAC (por exemplo, links site a região, região a região e site a site).

- Exiba informações do site de topologia de rede do CAC, informações de região e políticas de largura de banda provisionadas e links de rede.

### <a name="purpose"></a>Objetivo

Exiba links de topologia de rede do CAC corporativo em uma interface gráfica.

### <a name="examples"></a>Exemplos

 Carregue e exiba a topologia de rede cac de uma implantação do **Skype for Business Server 2015** em um formato gráfico: os administradores do Skype for Business Server 2015 podem carregar e exibir a configuração de topologia de rede do CAC em qualquer computador do Skype for Business Server 2015 **usando o Baixe a opção configuração** de rede, conforme mostrado na figura abaixo. A ferramenta não baixará ou exibirá essa configuração quando implantada em um computador que não tenha conectividade com o repositório de configuração Skype for Business Server 2015.

![Baixando a configuração de rede.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 Carregue e exiba **a topologia de rede do CAC** de um arquivo de log do servidor da Política de Largura de Banda em um formato gráfico: os servidores da Política de Largura de Banda do Skype for Business Server 2015 salvam a topologia de rede do CAC como parte do mecanismo de registro em log no local de compartilhamento de arquivos do Skype for Business Server 2015. Skype for Business Server administradores do 2015 podem exibir esse arquivo em um formato gráfico usando a opção Abrir Configuração  de Rede, conforme mostrado abaixo.

![Abrir um arquivo de log do Servidor de Política de Largura de Banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Salve e armazene a topologia de rede CAC em um formato XML no disco: os administradores do Skype for Business Server 2015 podem salvar o arquivo de configuração de topologia de rede do CAC em um formato XML usando **a** opção Salvar uma cópia da Configuração de Rede, conforme mostrado abaixo. O arquivo de configuração salvo pode ser usado offline para fins de exibição gráfica.

![Salvando a configuração de rede como um arquivo XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Salvar e armazenar o diagrama de topologia de rede do CAC no formato JPG ou BMP: os administradores do Skype for Business Server 2015 podem salvar a configuração de topologia de rede do CAC em um formato gráfico (formatos de arquivo JPG  e BMP) usando o diagrama Salvar Configuração de Rede como opção de imagem, conforme mostrado abaixo.

![Salvando a configuração de rede como uma imagem.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 Exibir dados de configuração de topologia de rede do <strong>CAC:</strong> os administradores do Skype for Business Server 2015 podem exibir dados de configuração de rede relacionados, como regiões de rede, sites de rede, perfis de largura de banda e endereços IP da sub-rede do site em um formato textual usando a opção Exibir dados de Configuração de Rede, conforme mostrado abaixo.

![Exibindo dados de configuração de rede.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 Exiba **a topologia de rede do CAC** em um estilo de exibição de árvore: os administradores do Skype for Business Server 2015 podem exibir dados de configuração de rede relacionados em um estilo de exibição de árvore gráfica usando o painel de controle no lado esquerdo da janela de ferramentas, conforme mostrado abaixo.

![Exibindo dados de configuração de rede em um modo de exibição de árvore.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 Defina conectores **personalizados para links de topologia de rede do CAC (como links site a região,** região a região e site a site): os administradores do Skype for Business Server 2015 podem definir conectores gráficos personalizados para links WAN de configuração de rede do CAC usando a opção Configurações, conforme mostrado abaixo. Isso ajuda a diferenciar entre vários tipos de links de rede provisionados na configuração de rede.

![Ferramentas.](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 Exiba informações do **site de topologia** de rede do CAC, informações de região e políticas de largura de banda provisionadas: os administradores do Skype for Business Server 2015 podem exibir informações relacionadas da região de rede do CAC, informações do site e informações de provisionamento de largura de banda do CAC usando as opções mostradas abaixo. (Por exemplo, clique **em Informações em** uma região de rede ou objeto de site de rede.)

![Definindo conectores personalizados para sua rede.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso Skype for Business Server administradores de 2015 que desejam exibir a topologia de rede do CAC para sua implantação em um formato gráfico.

## <a name="response-group-agent-live"></a>Agente do Grupo de Resposta Ativo
<a name="RGAL"> </a>

O aplicativo Grupo de Resposta oferece aos agentes a capacidade de acessar informações úteis em tempo real usando seu serviço Web interno. Infelizmente, nenhuma exibição gráfica desses dados está disponível fora do aplicativo. A ferramenta Live Resource Kit do Agente do Grupo de Resposta resolve esse problema fornecendo uma maneira simples e gráfica de acessar essas informações, aprimorada com informações de software de comunicação em tempo real do Skype for Business, como a presença de outros agentes.

### <a name="description"></a>Descrição

O Response Group Agent Live é um aplicativo de Windows que fornece funcionalidade de entrada e saída e algumas informações em tempo real (como associação de grupo e número atual de chamadas) para agentes do Grupo de Resposta. Ele deve ser uma versão aprimorada da página Grupos de Agentes (acessível de Skype for Business.

### <a name="purpose"></a>Objetivo

O aplicativo Grupo de Resposta enfileira chamadas de entrada e as roteia para grupos de agentes. Para tomar decisões informadas sobre quais chamadas para o serviço, os agentes podem acessar informações em tempo real sobre seus grupos de agentes, como quais outros agentes estão disponíveis e quantas chamadas estão aguardando em cada fila. Essas informações, inicialmente acessíveis somente por meio do serviço Grupo de Resposta, são disponibilizadas de maneira intuitiva pelo Agente do Grupo de Resposta Ao Vivo.

#### <a name="features"></a>Recursos

A ferramenta Dinâmica do Agente do Grupo de Resposta é criada no serviço grupo de resposta e no SDK do Skype for Business Server 2015. Ele fornece aos agentes do Grupo de Resposta as informações e os recursos disponíveis no serviço grupo de resposta (como associação de grupo, presença de outros agentes e número de chamadas em espera).

A figura a seguir ilustra a interface principal do Agente de Grupo de Resposta Ao Vivo.

![A ferramenta Dinâmica do Agente de Grupo de Resposta.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Os três principais recursos a seguir estão disponíveis para agentes no Response Group Agent Live:

- **Entrada/saída:** Ao contrário da página Grupos de Agentes (acessível do Skype for Business Server 2015), o Response Group Agent Live permite que somente agentes se conectem ou saiam de todos os grupos de agentes de uma só vez. Este aplicativo fornece três maneiras rápidas para os agentes entrarem ou sairem:

  - Clique nos botões Entrar/Sair (verde e vermelho) dentro do aplicativo.

  - Clique com o botão direito do mouse no ícone de bandeja do sistema e selecione entrar ou sair.

  - Usando atalhos de teclado configuráveis.

- **Associação de grupo:** Quando um grupo de agentes é selecionado, o Agente dinâmico do Grupo de Resposta exibe a lista de agentes nesse grupo no painel direito. Se Skype for Business Server 2015 estiver em execução no mesmo computador que este aplicativo, as informações de presença e o cartão de visita serão exibidos no Agente do Grupo de Resposta Ao Vivo. Os agentes podem enviar uma mensagem instantânea ou chamar outros agentes diretamente de lá.

- **Estatísticas em tempo real:** O Response Group Agent Live fornece estatísticas em tempo real para todos os grupos de agentes. A frequência de atualização é de um minuto. Quando uma chamada é atendida por um Grupo de Resposta, um indicador visual é adicionado ao lado do nome do grupo com o número atual de chamadas enfileiradas. Pausar o ponteiro sobre um grupo também exibe o tempo de espera mais longo.

### <a name="requirements"></a>Requisitos

O Agente de Grupo de Resposta Ao Vivo .NET Framework o .NET Framework 4.0. Além disso, para aproveitar os recursos de presença e cartão de visita, Skype for Business deve ser instalado localmente (e estar em execução).

#### <a name="configuration"></a>Configuração

O Agente de Grupo de Resposta ao vivo pode ser personalizado para preferências individuais usando a caixa de diálogo Opções no aplicativo. Além disso, o administrador pode definir o endereço de host padrão editando diretamente a propriedade defaultHostAddress do RGAgentLive.exe.config arquivo.

A figura a seguir ilustra a caixa de diálogo Opções que os agentes podem usar para configurar o endereço do host e as teclas de atalho. Essa caixa de diálogo é acessada clicando no botão Opções no canto superior direito da interface principal.

![A caixa de diálogo Opções Dinâmicas do Agente de Grupo de Resposta.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

As três configurações diferentes a seguir podem ser personalizadas na configuração dinâmica do Agente do Grupo de Resposta:

- Endereço do host: normalmente é o FQDN do pool da Web que pertence ao pool inicial do agente. O endereço de serviço exato do Grupo de Resposta é derivado automaticamente em segundo plano dessa informação (acrescentando o caminho certo após o host).

- Atalhos: os atalhos exatos para entrar/sair podem ser personalizados. A única limitação é que ambos os atalhos devem conter a tecla "logotipo Windows" (além de pelo menos outra tecla).

- Comece com Windows: o aplicativo pode ser configurado para iniciar automaticamente com Windows.

### <a name="examples"></a>Exemplos

A figura a seguir ilustra como chamar ou enviar uma mensagem instantânea para outro agente clicando com o botão direito do mouse no contato no painel direito.

![Fazer uma chamada ou enviar uma mensagem instantânea.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

A figura a seguir ilustra como o Agente de Grupo de Resposta ao vivo exibe o número atual de chamadas na fila e o tempo de espera mais longo entre todas essas chamadas de entrada.

![Exibindo informações da fila.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Resumo

Logon e saída rápidos, associação de grupo e estatísticas básicas em tempo real são recursos interessantes do agente do Grupo de Resposta que só estão disponíveis fora do aplicativo do serviço grupo de resposta. Com a ferramenta Kit de Recursos dinâmicos do Agente de Grupo de Resposta, os administradores do Skype for Business Server 2015 podem fornecer a seus agentes um aplicativo Windows que permite que eles executem tarefas de maneira mais rápida e gráfica.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (ativação de recursos de extensão secundária) é uma ferramenta de linha de comando que permite que os administradores de software de comunicação do Skype for Business Server 2015 e agentes de assistência técnica configurem toque delegado, encaminhamento de chamadas, toque simultâneo, configurações de chamada de equipe e recebimento de chamadas em grupo em nome de um usuário do Skype for Business Server 2015. A ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico. A ferramenta SEFAUtil permite que o administrador habilite/desabilite/modifique o encaminhamento de chamadas ou toque simultâneo em nome do usuário. O administrador pode especificar o destino (na forma de um URI SIP) ou usar um destino que já foi publicado pelo usuário. Essa ferramenta também permite que os administradores adicionem ou removam delegados ou membros do grupo de chamada de equipe em nome do usuário. Essa ferramenta se baseia na UCMA (Api Gerenciada de Comunicações Unificadas) 3.0 da Microsoft e requer que os administradores criem um aplicativo confiável no repositório de Gerenciamento Central para SEFAUtil.

O SEFAUtil (ativação de recurso de extensão secundária) permite que os administradores e agentes de assistência técnica do Skype for Business Server 2015 configurem toque delegado, encaminhamento de chamadas, toque simultâneo, configurações de chamada de equipe e recebimento de chamadas em grupo em nome de um usuário do Skype for Business Server 2015. Essa ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico.

### <a name="description"></a>Descrição

A versão atual do SEFAUtil é apenas uma ferramenta de linha de comando; não há suporte para interface gráfica do usuário. Essa ferramenta é baseada na UCMA (Unified Communications Managed API) 3.0 da Microsoft. Os recursos nesta ferramenta permitem que os administradores e agentes de assistência técnica executem o seguinte:

- Exibir todas as configurações de roteamento de chamadas para um usuário (inclui encaminhamento de chamadas, delegação, toque simultâneo, chamada de equipe e recebimento de chamadas em grupo)

- Habilitar/desabilitar/modificar a configuração de encaminhamento de chamadas (inclui o temporizador de destino e sem resposta)

- Habilitar/desabilitar/modificar configurações imediatas de encaminhamento de chamadas

- Habilitar/desabilitar/modificar configurações de delegação

- Habilitar/desabilitar/modificar configurações de grupo de chamada de equipe

    > [!NOTE]
    > Novidades na Skype for Business Server 2015 SEFAUtil

- Habilitar/desabilitar/modificar configurações de toque simultâneo (inclui o destino)

    > [!NOTE]
    > Novidades na Skype for Business Server 2015 SEFAUtil

- Habilitar/desabilitar/modificar configurações de recebimento de chamadas de grupo

    > [!CAUTION]
    > Novidades na Skype for Business Server 2015 SEFAUtil

Essa ferramenta tem as seguintes limitações:

- Com suporte apenas para usuários hospedados em um pool de Skype for Business Server

- Não há suporte para a edição em massa das configurações de roteamento de chamadas para vários usuários

### <a name="output"></a>Saída

A versão atual dessa ferramenta fornece saída somente na janela prompt de comando. Para obter detalhes, consulte a seção Exemplos mais adiante neste documento.

### <a name="purpose"></a>Objetivo

A seguir estão alguns dos principais cenários em que essa ferramenta pode ser usada:

- Bob é um executivo e foi movido para Skype for Business Server telefonia. Ele tem delegação em seu sistema PBX existente. Como parte da mudança para o Skype for Business Server 2015, o administrador é capaz de configurar o roteamento de Bob para refletir sua configuração de delegação pré-existente.

- Alice está viajando e percebe que está esperando uma chamada importante de um de seus clientes. No entanto, ela está em um hotel e não tem acesso a um computador. Ela chama a assistência técnica e solicita que encaminhem para seu número de celular todas as chamadas feitas ao seu número de trabalho. A equipe de assistência técnica é capaz de fazer a configuração em seu nome.

- As chamadas de Joe para seu número de trabalho estão indo para sua caixa postal móvel sempre que ele está no trabalho; no entanto, as coisas parecem estar funcionando corretamente na maioria dos outros locais. O técnico de assistência técnica é capaz de ver a configuração de roteamento de Joe e descobre que Joe tem toque simultâneo configurado para seu telefone celular. O técnico pergunta a Joe sobre a cobertura móvel em seu escritório e é capaz de determinar que a regra de toque simultâneo é o que está fazendo com que as chamadas acessem a caixa postal móvel de Joe quando sua cobertura de rede é ruim.

- Mike é um novo funcionário da Contoso e está ingressando em uma nova equipe na qual todos os membros estão configurados para chamada de equipe. Ao ser habilitado para o Skype for Business Server 2015, o administrador é capaz de definir suas configurações de grupo de chamada de equipe para incluir todos os seus novos membros da equipe, além disso, o administrador adiciona Mike como um membro do grupo de chamada de equipe para cada um dos membros em sua equipe.

- Uma prática de atendimento ao cliente no departamento de recursos humanos da Contoso é fornecer serviço pessoal para todos os chamadores desde a primeira chamada. Considerando que todos os membros do departamento ficam muito próximos uns dos outros, ter todos os telefones tocando ao mesmo tempo com a chamada de equipe é prejudicial para a equipe. Para fornecer o melhor serviço sem interromper os membros da equipe, o administrador do Skype for Business Server 2015 aproveita a funcionalidade de Recebimento de Chamadas em Grupo. O administrador adiciona todos os membros do departamento a um grupo de retirada e comunica ao departamento o número do grupo de retirada. Quando Samantha está ausente de sua mesa, Joe percebe seu telefone tocando e ele continua a atender a chamada de sua mesa.

### <a name="requirements"></a>Requisitos

A ferramenta SEFAUtil pode ser executada somente em um computador que faz parte de um Pool de Aplicativos Confiáveis. O UCMA 3.0 deve ser instalado nesse computador. Para executar a ferramenta, um novo Aplicativo Confiável com a ID do aplicativo SEFAUtil deve ser criado nesse pool.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Criando um novo aplicativo confiável para a ferramenta SEFAUtil

1. A ferramenta SEFAUTil pode ser executada somente em um computador que faz parte de um pool de aplicativos confiáveis. Se necessário, a adição de um pool como um novo pool de aplicativos confiáveis pode ser feita por meio do shell de gerenciamento do Skype for Business Server com o seguinte cmdlet:

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > O UCMA 3.0 deve ser instalado em qualquer computador que será usado para executar a ferramenta SEFAUtil.

2. Um aplicativo confiável precisa ser definido na topologia da ferramenta SEFAUtil. Para definir SEFAUtil como um novo aplicativo confiável, use o Shell de Gerenciamento Skype for Business Server e execute o seguinte cmdlet:

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > Uma porta diferente pode ser usada, se necessário.
    
    > [!NOTE]
    > FQDN do pool: o FQDN do servidor ou pool que hospedará o aplicativo SEFAUtil (geralmente um servidor Skype for Business front-end > ou pool).
    > FQDN do Registrador de Pools: o FQDN do servidor Skype for Business front-end ou pool associado a esse pool de aplicativos.
    > Site do Pool: a ID do Site do site no qual esse pool está hospedado.

3. As alterações de topologia precisam ser habilitadas. Habilitar as alterações de topologia pode ser feito por meio do Shell de Gerenciamento Skype for Business Server executando o seguinte cmdlet:

   ```powershell
   Enable-CsToplogy
   ```

4. Se necessário, instale as Ferramentas do Kit de Recursos do Skype for Business Server 2015 no servidor que será usada para executar a ferramenta SEFAUtil (o servidor deve fazer parte de um pool de aplicativos confiáveis).

5. Verifique se o SEFAUtil está em execução corretamente. Para fazer isso, execute a ferramenta em um prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamadas de um usuário na implantação. Por padrão, a ferramenta estará localizada em: "...\Arquivos de Programas\Skype for Business Server 2015\Reskit". Para exibir as configurações de encaminhamento de chamadas de um usuário, use o seguinte comando:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    As configurações de encaminhamento de chamadas do usuário devem ser exibidas.

#### <a name="group-call-pickup"></a>Recebimento de chamadas em grupo

O Recebimento de Chamadas em Grupo requer configuração adicional Skype for Business Server 2015 para que a funcionalidade seja totalmente habilitada. Antes de atribuir grupos de retirada aos usuários, consulte a documentação do produto de Recebimento de Chamadas em Grupo para obter as etapas de planejamento e implantação desse recurso.

### <a name="examples"></a>Exemplos

#### <a name="display-current-call-handling-settings"></a>Exibir o tratamento de chamadas atual Configurações

O comando a seguir exibe o tratamento de chamadas para o usuário.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> Este exemplo usa a **opção /server** para especificar o Skype for Business Server ao qual se conectar.

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Definir o encaminhamento de chamadas/nenhum destino de resposta

Este exemplo define o destino de encaminhamento/nenhuma resposta de chamada e o atraso do anel. Aqui, a opção /server não é fornecida; SEFAUtil tenta descoberta automática do Skype for Business Server 2015.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 **Saída**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>Habilitar o encaminhamento de chamadas imediatamente

Este exemplo habilita imediatamente o encaminhamento de chamadas para outro usuário.

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **Saída**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>Desabilitar o encaminhamento de chamadas imediatamente

Este exemplo desabilita imediatamente o encaminhamento de chamadas.

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 **Saída**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Adicionar um usuário como representante e configurar toque simultâneo de delegados

Este exemplo adiciona um usuário como um delegado e configura o toque simultâneo de delegados.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Alterar regra de toque simultâneo de delegados

Este exemplo altera a regra de toque simultâneo que foi definida no exemplo anterior para a regra de toque atrasada.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **Saída**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>Remover o delegado

Este exemplo remove o delegado.

> [!NOTE]
> Quando o último delegado é removido, o toque do representante é desabilitado automaticamente.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Adicionar um delegado e configurar o Call-Forward para a regra de delegados

Este exemplo adiciona um delegado e configura o encaminhamento de chamadas para a regra de delegados.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **Saída**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Habilitar toque simultâneo e definir um número de destino

Este exemplo habilita o toque simultâneo e define um número de destino de toque simultâneo.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Para alterar o número de destino de toque simultâneo de um usuário que já tem toque simultâneo habilitado, mantenha o comando com a opção /enablesimulring, caso contrário, o número de destino não será alterado.

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Desabilitar Toque Simultâneo

Este exemplo desabilita o toque simultâneo.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **Saída**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Adicionar um membro da equipe para Team-Call e configurar toque simultâneo para o grupo Team-Call membros

Este exemplo adiciona um membro da equipe ao grupo de chamada de equipe de um usuário e habilita o toque simultâneo para o grupo de chamada de equipe.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Adicionar um membro ao grupo de chamada de equipe de um usuário alternará automaticamente os settigs de toque simultâneos dos usuários para tocar simultaneamente em seu grupo de chamada de equipe.

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Remover um membro do grupo Team-Call grupo

Este exemplo remove um membro da equipe do grupo de chamada de equipe de um usuário.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Se o membro que está sendo removido for o único membro do grupo de chamada de equipe, o toque simultâneo para o grupo de chamada de equipe será desabilitado automaticamente.

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Definir o anel atrasado para o grupo Team-Call grupo

Este exemplo altera o anel atrasado para a configuração de hora do grupo de chamada de equipe.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>Habilitar Team-Call

Este exemplo habilita a chamada de equipe para um determinado usuário.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Se o grupo de chamada de equipe do usuário não tiver membros, a chamada de equipe não será habilitada.

 **Output**

#### <a name="disable-team-call"></a>Desabilitar Team-Call

Este exemplo desabilita a chamada de equipe para um determinado usuário.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **Saída**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Habilitar o recebimento de chamadas em grupo e atribuir um grupo de retirada a um usuário

Este exemplo atribui um grupo de retirada a um usuário e habilita o Recebimento de Chamadas em Grupo.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>Desabilitar Recebimento de Chamadas em Grupo

Este exemplo desabilita o Recebimento de Chamadas em Grupo para um determinado usuário.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Quando você desabilita o Recebimento de Chamadas em Grupo para um usuário, o número do grupo atribuído ao usuário não é mantido. Se posteriormente você quiser reabilitar o Recebimento de Chamadas em Grupo para esse usuário, deverá atribuir o número do grupo novamente com a opção /enablegrouppickup.

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Descrição

SYSPrep.ps1 é um script Windows PowerShell que instalará os seguintes pré-requisitos do Skype for Business Server 2015 em seu computador do sistema operacional Windows Server 2008.

- Microsoft .NET Framework 4.5

- Microsoft SQL Server Express

- Windows PowerShell versão 3.0

- Pacotes Redistribuíveis do Visual C++ 2010

- Atualizações do Servidor de Informações da Internet

- Windows Identity Foundation

- Skype for Business Server 2015 Core

  Embora o nome do script seja semelhante à Ferramenta de Preparação do Sistema para os sistemas operacionais microsoft Windows, eles são diferentes. Esse script instalará apenas os pré-requisitos necessários para Skype for Business Server 2015. Depois que esses pré-requisitos forem instalados, a ferramenta Windows SYSPrep poderá ser usada para criar uma imagem do servidor.

### <a name="requirements"></a>Requisitos

Antes de executar o script SYSPrep.ps1, você deve copiar os arquivos de pré-requisito para uma pasta local no computador do sistema operacional Windows Server 2008 (por exemplo **, D:\Setup)**. Essa pasta também deve incluir uma cópia dos arquivos Skype for Business Server 2015, especificamente **Setup.exe.** Os arquivos de pré-requisito podem ser baixados dos seguintes locais:


| **Pré-requisito**                                | **Location**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell versão 3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Pacotes Redistribuíveis do Visual C++ 2010  <br/>          | <https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0>  <br/>  |
| Atualizações do Servidor de Informações da Internet  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup.exe  <br/> | Copiar da Skype for Business Server 2015  <br/>                   |

### <a name="parameter"></a>Parâmetro

O **parâmetro -SetupFolder** usa como argumento o local do diretório dos arquivos de pré-requisito

### <a name="examples"></a>Exemplos

Para executar o script SYSPrep.ps1 e instalar os pré-requisitos do Skype for Business Server 2015, execute o seguinte comando em um prompt de comando com privilégios elevados:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Migração de comunicados de número não atribuído
<a name="UNAM"> </a>

A ferramenta Migração de Comunicados de Número Não Atribuído permite que um administrador do Skype for Business Server 2015 mova a configuração de números não atribuídos que é a serviço pelo aplicativo de comunicado de um Skype for Business Server ou pool de origem para um destino Skype for Business Server ou Pool.

### <a name="description"></a>Descrição

A ferramenta de Migração de Comunicados de Número Não Atribuído é um script Windows PowerShell que move a configuração de números não atribuídos a serviço pelo aplicativo de anúncio de um servidor ou pool de origem para um servidor ou pool diferente.

Quando executado, o script de Migração de Comunicados de Número Não Atribuído executará as seguintes operações:

1. Mova todos os arquivos de áudio usados pelos comunicados de número não atribuído do aplicativo de comunicado hospedado no servidor de origem ou pool para o repositório de arquivos do servidor ou pool de destino.

    > [!NOTE]
    > Os arquivos de áudio são removidos do pool de origem depois que são copiados para o pool de destino.

2. Mova todos os comunicados de número não atribuído configurados para o aplicativo de comunicado hospedado no servidor ou pool de origem para o servidor ou pool de destino.

3. Reatribua todos os intervalos de números não atribuídos que são a serviço pelo aplicativo de comunicado hospedado no servidor ou pool de origem para o servidor ou pool de destino.

Depois de executar o script com êxito, todos os intervalos de números não atribuídos que foram a serviço pelo aplicativo de comunicado hospedado no servidor ou pool de origem agora serão a serviço com a mesma configuração pelo servidor ou pool de destino.

### <a name="output"></a>Saída

O script **Move-CsAnnouncementConfiguration** indica na janela do Shell de Gerenciamento do Skype for Business Server de onde ele foi executado o êxito ou a falha da operação de migração.

Se a execução da operação for interrompida por qualquer erro, os intervalos de números não atribuídos que foram movidos com êxito para o destino permanecerão no destino em uma forma operacional e o restante dos intervalos de números não atribuídos a serem migrados permanecerá na origem também em uma forma operacional. Para migrar totalmente o restante da configuração, execute novamente o script depois de resolver o erro.

### <a name="purpose"></a>Objetivo

O script de Migração de Comunicados de Número Não Atribuído pode ser usado nos três cenários a seguir:

- **Migrar** definições de configuração para uma nova versão do Skype for Business Server: a Contoso está em processo de migração para o Skype for Business Server 2015 e como parte do processo de migração do Skype for Business Server  O administrador gostaria de mover a configuração de números não atribuídos a serviço pelo aplicativo de comunicado da implantação do Lync Server 2013 para a nova implantação do Skype for Business Server 2015. Para mover as definições de configuração, Skype for Business Server administrador usa a ferramenta De migração de Comunicados de Número Não Atribuído.

- Reverter uma implantação do **Skype for Business Server 2015 para o Lync Server 2013: devido a** fatores inesperados, a Contoso precisa reverter a migração para a nova implantação do Skype for Business Server 2015. Para minimizar as interrupções no serviço, o administrador do Skype for Business Server usa a ferramenta de Migração de Comunicados de Número Não Atribuído para reverter a configuração da implantação do Skype for Business Server 2015 para a implantação do Lync Server 2013.

- **Movendo dados entre implantações:** A Contoso está no processo de substituir todos os servidores de um pool por servidores mais recentes. Sua estratégia é implantar um novo pool do Skype for Business Server 2015, mover todos os dados do antigo para o novo pool e, em seguida, substituir o pool antigo. Depois que o novo pool é implantado, a ferramenta de Migração de Comunicados de Número Não Atribuído é usada para mover a configuração do pool antigo para o novo.

#### <a name="requirements"></a>Requisitos

A seguir estão os principais requisitos necessários para executar a ferramenta com êxito:

1. O script deve ser executado em um computador que tenha Skype for Business Server Shell de Gerenciamento instalado.

2. O aplicativo de comunicado deve ser implantado com êxito nos pools ou servidores de Skype for Business de origem e destino.

#### <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration script

O Move-CsAnnouncementConfiguration script requer os dois parâmetros descritos na tabela abaixo.

![Move-CsAnnouncementConfiguration parâmetros.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Exemplos

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Movendo a configuração de comunicados de número não atribuído de um pool do Lync Server 2013 para um pool Skype for Business Server 2015

Este exemplo move os anúncios de número não atribuído do pool de origem (Lync Server 2013) para o pool de destino (Skype for Business Server 2015).

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Movendo a configuração de comunicados de número não atribuído de um pool do Skype for Business Server 2015 para um pool do Lync Server 2013

Este exemplo move os anúncios de número não atribuído do pool de origem (Skype for Business Server 2015) para o pool de destino (Lync Server 2013).

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Dados de Web Conf
<a name="WebConfData"> </a>

A Ferramenta de Dados de Web Conf permite que um administrador do software de comunicações Skype for Business Server 2015 tenha mais controle sobre os dados associados às Webconferência de um organizador. Os cenários incluem a capacidade de excluir dados de reunião de um usuário específico com base em critérios de carimbo de data/hora.

### <a name="description"></a>Descrição

Essa ferramenta permite que o administrador execute as seguintes operações:

1. Localize todos os dados de webconferência associados a um único usuário.

2. Exclua todos os dados de webconferência associados a um único usuário.

3. Exclua todos os dados de webconferência associados a um único usuário mais antigo do que uma determinada data.

4. Mova todos os dados de webconferência associados a um único usuário quando esse usuário for movido de um pool para outro.

  > [!NOTE]
  > As Ferramentas do Kit de Recursos para Lync Server 2010 dão suporte à movimentação de todos os dados de webconferência associados a um único usuário quando esse usuário é movido de um pool para outro. Essa funcionalidade agora foi preterida dessa ferramenta em favor do **parâmetro MoveConferenceData** . Para obter detalhes sobre esse parâmetro, consulte o cmdlet [Move-CsUser](/powershell/module/skype/move-csuser?) .

A ferramenta exclui dados de reunião somente para reuniões que estão inativas. Reuniões ativas (ou reuniões em sessões) não podem ser excluídas.

Essa ferramenta deve ser executada em um computador que esteja no mesmo pool que o usuário de destino. O usuário cujos dados de conteúdo de reunião estão sendo gerenciados por essa ferramenta deve estar hospedado no mesmo pool de usuários.

### <a name="output"></a>Saída

Essa ferramenta gera os resultados de cada uma das operações:

- Se uma consulta for executada, a ferramenta gerará a lista de todas as pastas de dados de reunião inativas que têm esse usuário como organizador.

- Se uma exclusão for executada, a ferramenta gerará a lista de todas as pastas de dados de reunião cujos dados serão excluídos.

### <a name="requirements"></a>Requisitos

A ferramenta precisa ser executada no mesmo pool em que o organizador está hospedado no momento.

A ferramenta deve ser executada usando privilégios de administrador com acesso ao Repositório de Arquivos de Conteúdo.

### <a name="examples"></a>Exemplos

A tabela a seguir descreve os parâmetros, alguns dos quais são usados nos exemplos.

![Parâmetros da Ferramenta de Dados da Web Conf.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

O exemplo anterior mostra como um comando de consulta funcionaria. A saída desse comando seria uma lista de todas as pastas de conteúdo de reunião que seriam afetadas por essa ferramenta.

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

O anterior é um exemplo de um comando delete. O comando delete removerá todas as pastas de reunião inativas desse usuário.

### <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para administradores que precisam de um controle mais preciso sobre os dados da reunião em conferência.
