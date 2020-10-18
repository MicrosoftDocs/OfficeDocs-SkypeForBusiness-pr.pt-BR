---
title: Documentação das ferramentas do kit de recursos do Lync Server 2013
description: Documentação das ferramentas do kit de recursos do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6866e04615014daa7e93f7e7f1081b10325d087d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573557"
---
# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Documentação das ferramentas do kit de recursos do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-01-09_

Este tópico descreve as ferramentas que fazem parte do Lync Server 2013 Resource Kit, incluindo o propósito de cada ferramenta e exemplos de uso. O Lync Server 2013, ferramentas do kit de recursos ajudam a tornar tarefas rotineiras mais fáceis para os administradores de ti que implantam e gerenciam o Lync Server 2013. Por exemplo, a ferramenta **Web conf data** pode ser usada para controlar facilmente os dados que são carregados pelos usuários durante uma reunião online. A ferramenta **SEFAUtil** pode ser usada para configurar o encaminhamento de chamadas de representante e a resposta para usuários. Incentivamos os administradores de ti a usar essas ferramentas para gerenciar com mais eficiência o Lync Server 2013.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Instalação das ferramentas do kit de recursos

Para instalar o Lync Server 2013, ferramentas do kit de recursos, **OCSReskit.msi**de download. Você pode baixar o instalador de ferramentas do kit de recursos do centro de download em [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429) .

Execute **OCSResKit.msi** para fazer uma instalação simples. O. msi instala todas as ferramentas no seguinte caminho: **% Program Files% \\ Microsoft Lync Server 2013 \\ reskit**. As ferramentas que são executáveis independentes estão nessa pasta. As ferramentas que também têm arquivos estão em suas próprias subpastas.

</div>

<div>

## <a name="supported-environments"></a>Ambientes com suporte

Para obter o desempenho ideal, o Lync Server 2013, ferramentas do Resource Kit devem ser instalados no mesmo ambiente e com as mesmas especificações necessárias para o Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Visão geral das ferramentas do kit de recursos

A lista a seguir descreve as ferramentas fornecidas no Lync Server 2013 Resource Kit. Uma descrição de cada ferramenta, incluindo os requisitos e o uso de exemplo, é abordada na seção a seguir.

  - ABSConfig

  - Monitor de serviço de política de largura de banda

  - Analisador de utilização de largura de banda

  - Chamar estacionador chamadas

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - Visualizador de configuração de rede

  - Agente de grupo de resposta Live

  - SEFAUtil

  - SYSPrep.ps1

  - Migração de comunicados de número não atribuído

  - Dados de conferência da Web

</div>

<div>

## <a name="absconfig"></a>ABSConfig

A ferramenta de configuração do serviço de catálogo de endereços (ABSConfig) é uma ferramenta administrativa que ajuda os administradores a personalizar a configuração do serviço de catálogo de endereços no Lync Server 2013. Essa ferramenta também permite que os administradores do Lync Server 2013 restaurem as configurações padrão do serviço de catálogo de endereços.

<div>

## <a name="description"></a>Descrição

O ABSConfig é um aplicativo de interface gráfica do usuário que permite que os administradores configurem atributos de serviços de domínio do Active Directory relacionados ao serviço de catálogo de endereços.

Os principais cenários da ferramenta são os seguintes:

  - Para permitir que os administradores mapeiem atributos nos serviços de domínio do Active Directory para os atributos do Lync Server 2013.

  - Para permitir que os administradores especifiquem o atributo de serviços de domínio Active Directory a ser incluído ou excluído nos arquivos de serviço do catálogo de endereços.

  - Para permitir que os administradores restaurem as configurações padrão do serviço de catálogo de endereços.

A ferramenta ABSConfig pode ser iniciada usando o arquivo absConfig.exe. A ferramenta é aberta para a guia **Configurar atributos** . Esta tabela tem opções para mapear atributos de serviços de domínio do Active Directory para os campos de atributo do Lync Server 2013 e especificar quais usuários serão incluídos ou excluídos nos arquivos de serviço de catálogo de endereços com base em filtros de atributo específicos. Também tem opções para personalizar o valor do número de telefone a ser incluído no arquivo do catálogo de endereços. A opção **Restaurar padrões** permite que os administradores restaurem os valores padrão das configurações do serviço de catálogo de endereços.

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>Alterações do Lync Server 2010

Na ferramenta de configuração de ABS do Lync Server 2013, os atributos (linhas) podem ser removidos desmarcando a caixa de seleção "habilitar" para o atributo. Isso tem o mesmo efeito que excluir a linha no Lync Server 2010.

<div>


> [!NOTE]  
> A caixa de seleção Habilitar está na coluna extrema direita; Talvez seja necessário rolar para a direita para ver a coluna



</div>

</div>

<div>

## <a name="output"></a>Saída

ABSConfig armazena a configuração do serviço de catálogo de endereços no banco de dados.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>Finalidade

O ABSConfig fornece uma maneira rápida e fácil de personalizar o serviço de catálogo de endereços do Lync Server 2013.

</div>

<div>

## <a name="requirements"></a>Requisitos

<div>

## <a name="computer"></a>Computador

O ABSConfig pode ser executado apenas de um computador associado ao domínio que tenha o Lync Server 2013 instalado. No caso do Lync Server 2013, Enterprise Edition, essa ferramenta pode ser executada em qualquer servidor front-end que tenha o serviço de catálogo de endereços habilitado durante a instalação.

</div>

<div>

## <a name="network"></a>Rede

O computador deve poder se conectar ao pool de front-ends e ao banco de dados back-end.

</div>

<div>

## <a name="software"></a>Software

Os seguintes componentes de software devem ser instalados antes de executar a ferramenta ABSConfig:

  - Microsoft Lync Server 2013

</div>

<div>

## <a name="users"></a>Usuários

Administradores que têm as permissões necessárias para atualizar a implantação do Lync Server 2013.

</div>

</div>

<div>

## <a name="examples"></a>Exemplos

O ABSConfig pode ser iniciado digitando **ABSConfig.exe** em um prompt de comando. Mostrado abaixo é a interface do usuário da ferramenta ABSConfig.

![A ferramenta ABSConfig.exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "A ferramenta ABSConfig.exe.")

</div>

<div>

## <a name="summary"></a>Resumo

A ferramenta ABSConfig fornece aos administradores uma ferramenta rápida e fácil de usar para personalizar o serviço de catálogo de endereços do Lync Server 2013.

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>Monitor de serviço de política de largura de banda

A ferramenta Monitor de serviço de política de largura de banda destina-se a permitir que os administradores exibam uma lista dos seguintes:

1.  Todos os serviços de política de largura de banda do Lync Server 2013 (autenticação e núcleo) configurados na topologia

2.  As conexões que cada serviço faz para outros serviços de política de largura de banda e para os servidores de borda

3.  Todos os links que são configurados no documento de configuração de rede e uso de largura de banda em tempo real conforme relatado por cada um dos serviços de política de largura de banda

<div>

## <a name="description"></a>Descrição

A ferramenta Monitor de serviço de política de largura de banda é implementada como um aplicativo baseado em GUI. Os administradores iniciam a ferramenta executando o PDPMonUI.exe.

Quando a ferramenta é iniciada, tenta descobrir a lista de serviços de política de largura de banda na topologia. Depois que a atualização inicial for concluída, o painel à esquerda da janela será preenchido com uma lista de serviços que são agrupados pelos clusters aos quais pertencem.

Quando os administradores selecionam um serviço de política de largura de banda específico, o painel à direita exibe as informações sobre esse serviço específico. Esse painel também tem duas guias principais que exibem informações.

<div>

## <a name="machine-info-tab"></a>Guia informações do computador

A guia **informações do computador** mostra os detalhes do serviço de política de largura de banda selecionado e a lista e o estado de todas as conexões feitas pelo serviço de política de largura de banda selecionado para outros serviços.

</div>

<div>

## <a name="topology-info-tab"></a>Guia informações de topologia

A guia **informações da topologia** mostra uma lista de todos os links que são configurados nas definições de configuração da rede. Para cada link, a capacidade de largura de banda de áudio e vídeo é exibida. Além disso, a largura de banda atualmente utilizada é exibida, tanto em Kbps quanto como uma porcentagem da capacidade. A ferramenta usa codificação de cores para realçar os links que têm utilização próxima à capacidade, permitindo que os administradores isolem rapidamente esses links.

<div>


> [!NOTE]  
> Se a ferramenta de monitoração do serviço de política de largura de banda apresentar falha ao se conectar a qualquer um dos serviços de política de largura de banda configurados, as informações nas guias informações sobre a <STRONG>máquina</STRONG> e <STRONG>informações de topologia</STRONG> não serão preenchidas. No entanto, é possível que a ferramenta possa se conectar inicialmente, mas, em seguida, perder a conexão com o serviço. Nesses casos, os administradores podem ver informações desatualizadas. Há um carimbo de data/hora <STRONG>atualizado</STRONG> em cada uma das guias que podem permitir que os administradores vejam quando os dados foram atualizados pela última vez para um serviço de política de largura de banda específico.



</div>

</div>

</div>

<div>

## <a name="output"></a>Saída

Não há nenhuma saída de linha de comando; a saída do programa está contida na GUI (interface gráfica do usuário) principal.

</div>

<div>

## <a name="purpose"></a>Finalidade

O objetivo da ferramenta Monitor de serviço de política de largura de banda é permitir a visibilidade dos administradores no estado de cada um dos serviços de política de largura de banda definidos na topologia. Além disso, os administradores podem ver o uso da largura de banda em tempo real para todos os links definidos no documento de configuração de rede.

</div>

<div>

## <a name="requirements"></a>Requisitos

A ferramenta Monitor de serviço de política de largura de banda precisa ser executada em um computador que faça parte da topologia do Lync Server.

</div>

<div>

## <a name="summary"></a>Resumo

A ferramenta Monitor de serviço de política de largura de banda pode ser um recurso valioso para os administradores para que eles possam inspecionar o estado de todos os serviços de política de largura de banda na topologia, e o mais importante: eles podem obter a utilização de largura de banda em tempo real para os links definidos nas definições de configuração de rede.

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>Analisador de utilização de largura de banda

O analisador de utilização de largura de banda é uma ferramenta que cria relatórios sobre vários modos de exibição de consumo de largura de banda pelos pontos de extremidade UC nos links WAN na rede corporativa. Esses relatórios podem ser usados para entender o padrão atual de consumo de largura de banda e para ajudar no planejamento da capacidade de largura de banda.

<div>

## <a name="description"></a>Descrição

O analisador de utilização de largura de banda é implementado como um aplicativo baseado em GUI. Essa ferramenta gera relatórios específicos para a utilização de áudio na rede e ajuda no planejamento da capacidade. Ele também itera na capacidade de largura de banda atribuída a vários links.

</div>

<div>

## <a name="output"></a>Saída

O analisador de utilização de largura de banda oferece plotagens em formato gráfico Al de capacidade de largura de banda e utilização de áudio para todos os links WAN que são configurados no sistema.

</div>

<div>

## <a name="purpose"></a>Finalidade

Em qualquer implantação de voz e vídeo, é fundamental monitorar e entender a tendência da utilização de largura de banda de tráfego de mídia na rede corporativa. A ferramenta Analisador de utilização da largura de banda permite que um administrador realize apenas isso. Esta ferramenta faz o seguinte:

  - Gera relatórios específicos para a utilização de áudio na rede

  - Ajuda no planejamento de capacidade mais eficaz e na iteração na capacidade de largura de banda atribuída a vários links

O analisador de utilização de largura de banda pode gerar gráficos de capacidade de largura de banda e relatórios de utilização; Eles são os seguintes:

  - Todos os links WAN na rede corporativa

  - Filtrado por links WAN selecionados que foram escolhidos

  - Filtrado por links WAN que excederam a capacidade de link

  - Filtrado por links WAN que estão subutilizando a largura de banda provisionada

  - Filtrar por links WAN que atingiram níveis críticos (uma utilização de largura de banda maior que 90% da capacidade de largura de banda do link WAN)

  - Filtrado por tipo de link WAN — links de site de rede, links entre regiões e links em um site

  - Filtrado por região de rede

<div>

## <a name="applications"></a>Aplicativos

O analisador de utilização da largura de banda tem os dois aplicativos a seguir (ferramentas):

  - **WanLinkLogCollector.exe**     Esta ferramenta permite que o usuário insira as informações necessárias.

  - **BandwidthUtilizationAnalyzer.xlsm**    Um relatório de software de planilha do Microsoft Excel é iniciado automaticamente pelo WanLinkLogCollector.exe. Este aplicativo permite que o usuário Aplique filtros ao relatório, conforme mostrado posteriormente neste artigo.

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fases de uso do analisador de utilização de largura de banda

Há duas fases ao usar o analisador de utilização da largura de banda:

  - Coletar logs, que é executado usando o WanLinkLogCollector.exe

  - Personalizar relatórios, que é executado usando BandwidthUtilizationAnalyzer.xlsm

<div>


> [!IMPORTANT]  
> É altamente recomendável que BandwidthUtilizationAnalyzer.xlsm não seja iniciado manualmente por usuários finais.



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>Iniciando analisador de utilização da largura de banda

Inicie WanLinkLogCollector.exe no prompt de comando ou usando o Windows Explorer.

**Usando WanLinkLogCollector.exe**

Há três etapas para usar WanLinkLogCollector.exe:

1.  **Registrar a linha do tempo**     Forneça a linha do tempo para a qual o relatório precisa ser gerado

2.  **Especificar os diretórios**     de arquivos Fornecer informações de local de arquivo

3.  **Coletar os logs e iniciar o visualizador**    de relatórios Executar o comando para gerar o relatório

<div>

## <a name="step-1---log-the-timeline"></a>Etapa 1-registrar a linha do tempo

O registro da linha do tempo permite que o usuário da ferramenta especifique o seguinte, conforme mostrado na figura abaixo.

1.  **Data de início** Esta é a data de início da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 1º de agosto de 2010.

2.  **Data de término** Esta é a data de término da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 30 de setembro de 2010.
    
    ![Datas de início e de término na utilização de largura de banda](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Datas de início e de término na utilização de largura de banda")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>Etapa 2-especificar os diretórios de arquivo

Os seguintes diretórios de arquivos podem ser especificados pelo usuário, conforme mostrado.

  - **Local dos arquivos de log do servidor** O local da pasta onde os logs do servidor de política de largura de banda estão armazenados. Em geral, isso ocorre no \<fileserver\> \\ \<choice of FE\> \\ AppServerFiles \\ PDP.

  - **Local de armazenamento de arquivos temporários** O local do arquivo temporário onde os arquivos intermediários são armazenados enquanto o relatório está sendo gerado.

![Diretórios de arquivos no análise de utilização da largura de banda](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Diretórios de arquivos no análise de utilização da largura de banda")

<div>


> [!NOTE]  
> Certifique-se de que o acesso de arquivo suficiente aos logs de servidor e à pasta de repositório de arquivos temporários seja fornecido para o usuário da ferramenta.



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Etapa 3: coletar os logs e iniciar o Visualizador de relatórios

Para coletar os logs e iniciar o Visualizador de relatórios, clique em **executar** , conforme mostrado abaixo. Esta etapa coleta os dados necessários.

![Coletando dados na análise de utilização da largura de banda](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Coletando dados na análise de utilização da largura de banda")

Quando a validação de entrada for bem-sucedida, a mensagem mostrada abaixo será exibida.

![Registra a notificação coletada no utilitário de largura de banda](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Registra a notificação coletada no utilitário de largura de banda")

Clique em **OK**. BandwidthUtilizationAnalyzer.xlsm é iniciado automaticamente. Siga as instruções na caixa de mensagem. Para obter detalhes, consulte **usando BandwidthUtilizationAnalyzer.xlsm** na próxima seção.

</div>

<div>


**Usando BandwidthUtilizationAnalyzer.xlsm**

1.  Quando BandwidthUtilizationAnalyzer.xlsm for iniciado automaticamente, clique em **Atualizar** , conforme mostrado abaixo.
    
    ![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")

2.  Quando uma pasta de arquivos for aberta, selecione consolidated.csv do local especificado na caixa de mensagem, conforme mostrado abaixo. Também mostra o local como **C: \\ Temp**.
    
    ![Abrir uma pasta no BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Abrir uma pasta no BandwidthUtilizationAnalyzer.")

3.  Clique em **Importar**.

4.  A plotagem gráfica é gerada automaticamente. Ela estará disponível quando o ponteiro de trabalho em segundo plano desaparecer.
    
    ![Aplicando filtros no modo de exibição de relatório.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicando filtros no modo de exibição de relatório.")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>Aplicando filtros ao modo de exibição de relatório

Os filtros que podem ser aplicados ao modo de exibição de relatório, conforme mostrado abaixo, são descritos a seguir:

![Aplicando filtros no modo de exibição de relatório.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicando filtros no modo de exibição de relatório.")

1.  **Nome** Filtrar por links WAN (o filtro está no lado direito do gráfico). O prefixo indica os seguintes tipos de link; Confira a caixa vertical (azul):
    
      - **S site** O link WAN de um site de rede para uma região de rede
    
      - **É entre sites** O link WAN entre dois sites de rede
    
      - **R inter-Region** O link WAN entre duas regiões de rede

2.  **Limite excedido** Filtrar por links WAN cuja utilização de largura de banda é maior do que a capacidade de largura de banda

3.  **Níveis críticos** Filtrar por links WAN cuja utilização da largura de banda alcançou 90% ou mais da capacidade da largura de banda

4.  **Subutilizado** Filtrar por links WAN cuja utilização da largura de banda tenha sido inferior a 25% da capacidade da largura de banda

5.  **Tipo de link** Filtrar pelos seguintes tipos de links de WAN:
    
      - Tipo de **site de rede**
    
      - Tipo **entre sites**
    
      - Tipo **de link entre regiões**

6.  **Região** Filtrar por região de rede

As figuras a seguir mostram os filtros descritos anteriormente.

Filtrar por **nome**. Selecione a lista de links que precisam ser exibidos no gráfico.

![Filtragem por nome no BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtragem por nome no BandwidthUtilizationAnalyzer.")

Filtrar por **limite excedido**. Selecione **verdadeiro** para impor o filtro.

![Filtragem por limite excedido.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtragem por limite excedido.")

Filtrar por **níveis críticos**. Selecione **verdadeiro** para impor o filtro.

![Filtragem por níveis críticos.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtragem por níveis críticos.")

Filtrar por **subutilizado**. Selecione **verdadeiro** para impor o filtro.

![Filtragem por subutilizado.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtragem por subutilizado.")

Filtrar por **tipo de link**. Selecione o tipo ou tipos que precisam ser exibidos.

![Filtragem por tipo de link.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtragem por tipo de link.")

Filtrar por **região**. Selecione uma lista de regiões cujos vínculos precisam ser exibidos.

![Filtragem por região.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtragem por região.")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>Requisitos

  - O .NET Framework 3,5

  - Microsoft Excel 2010 ou Excel 2007

</div>

<div>

## <a name="summary"></a>Resumo

O analisador de utilização de largura de banda é usado para plotar a utilização de largura de banda de áudio para tráfego UC na rede. Essa ferramenta também pode ser usada para relatar a utilização da largura de banda de vídeo na rede.

</div>

</div>

<div>

## <a name="call-parkometer"></a>Chamar estacionador chamadas

Call estacionador chamadas é um aplicativo de linha de comando que fornece fácil acesso ao banco de dados de órbita de estacionamento de chamada.

<div>

## <a name="description"></a>Descrição

O estacionador chamadas de chamada é uma ferramenta para rastrear chamadas estacionadas no momento. Ele também coleta estatísticas sobre órbitas e uso do servidor de estacionamento de chamada (CPS). Essa ferramenta de linha de comando fornece acesso de leitura e gravação ao banco de dados do SQL Server do CPS órbita de um computador local ou conectado remotamente.

Todas as opções são mutuamente exclusivas. A sintaxe da linha de comando é a seguinte:

  - **– o** Parameter — lista todos os intervalos de órbita configurados para este pool.

  - **– n** parâmetro — lista todas as órbitas atualmente usadas neste pool. As informações exibidas são as seguintes:
    
      - Identificador de recurso uniforme (URI) SIP do estacionamento e do estacionador.
    
      - Nome do host do CPS onde a chamada está estacionada.
    
      - Carimbo de data/hora de quando a chamada foi estacionada.

  - **– f** parâmetro — lista o número de órbitas livres no momento no pool.

  - **– r \<n\> ** parâmetro — lista as \<n\> últimas chamadas estacionadas. As informações exibidas são as seguintes:
    
      - URI do SIP do estacionamento.
    
      - Estacionador URI do SIP.
    
      - Nome do host do CPS onde a chamada foi estacionada.
    
      - Carimbo de data/hora de quando a chamada foi recuperada ou cancelada.

  - **-t \<n\> ** parâmetros-testes reservem uma órbita no banco de dados para mostrar a aleatoriedade dos números de órbita atribuídos.

</div>

<div>

## <a name="output"></a>Saída

Dependendo dos parâmetros de entrada que são especificados em um prompt de comando, Call estacionador chamadas exibe o seguinte resultado:

  - Todos os intervalos de órbita configurados para este pool

  - Chamadas estacionadas atualmente

  - Número de órbitas livres (disponíveis)

  - Chamadas estacionadas recentemente

  - Órbitas reservados para testar valores de órbita uniformes e aleatórios

</div>

<div>

## <a name="purpose"></a>Finalidade

O objetivo da ferramenta CPS é fornecer acesso de linha de comando para o banco de dados CPS. O administrador pode exibir o uso do CPS e determinar o número de órbitas atribuídas a um pool.

</div>

<div>

## <a name="requirements"></a>Requisitos

Não há requisitos se essa ferramenta for executada no mesmo computador que está executando o CPS. Se essa ferramenta for executada em um computador remoto, o banco de dados do SQL Server usado pelo Lync Server 2013 deve ser configurado para permitir o acesso remoto. O estacionador chamadas de chamada deve ser configurado com uma cadeia de conexão de banco de dados do SQL Server para se conectar ao SQL Server do pool. Esta sequência de conexão de banco de dados do SQL Server está definida no arquivo de configuração **parkometer.exe.config**. Ele deve ser colocado no mesmo diretório onde parkometer.exe está localizado. O arquivo XML a seguir é um exemplo de um parkometer.exe.config. Os parâmetros que devem ser configurados são o nome de usuário (por exemplo, administrador de mydomain \\ ), a senha (por exemplo, mypassword) e o nome do host (por exemplo, meuservidor).

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

</div>

<div>

## <a name="examples"></a>Exemplos

Intervalos de órbita implantados: o parâmetro – o lista todos os intervalos de órbita configurados para este pool, conforme mostrado

![Intervalos de órbita na chamada estacionador chamadas.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Intervalos de órbita na chamada estacionador chamadas.")

Chamadas estacionadas atualmente: o parâmetro – n lista todas as órbitas usadas atualmente neste pool, conforme mostrado

![Chamadas estacionadas no momento em Call estacionador chamadas.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Chamadas estacionadas no momento em Call estacionador chamadas.")

Número de órbitas livres: o parâmetro – f lista o número de órbitas livres no pool, conforme mostrado

![Órbitas livres no estacionador chamadas de chamada.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Órbitas livres no estacionador chamadas de chamada.")

Chamadas estacionadas recentemente: o parâmetro – r \<n\> lista as \<n\> últimas chamadas estacionadas, conforme mostrado

![Chamadas estacionadas recentemente em Call estacionador chamadas.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Chamadas estacionadas recentemente em Call estacionador chamadas.")

Testar reserva de órbita: os testes de parâmetro – t \<n\> reservem uma órbita no banco de dados, conforme mostrado

![Testar reservas em Call estacionador chamadas.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Testar reservas em Call estacionador chamadas.")

</div>

<div>

## <a name="summary"></a>Resumo

Call estacionador chamadas é uma ferramenta de linha de comando que fornece informações detalhadas sobre o servidor de estacionamento de chamada.

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

A ferramenta CleanupStorageServiceData Resource Kit permite a exclusão de dados órfãos do banco de dados usado pelo serviço de armazenamento do Lync Server (LYSS). Uma função do serviço de armazenamento é armazenar em buffer a comunicação entre o Lync Server e vários pontos de extremidade de armazenamento de dados back-end, como o SQL Server e o Exchange.

<div>

## <a name="description"></a>Descrição

Para oferecer suporte à alta disponibilidade, o LYSS aceita e salva cópias dos dados em vários servidores front-end no pool temporariamente e remove esses dados depois de serem entregues ao seu local de armazenamento final de longo prazo. Há situações incomuns que podem ocorrer durante a operação normal, quando um servidor pode falhar ou enfrentar um problema de processamento, e alguns dados podem não ser limpos corretamente. Esses dados são inofensivos, mas eles consomem recursos de processamento limitado. Grande parte da manutenção de dados normal é automatizada, mas essa ferramenta permite a identificação e remoção segura de dados órfãos quando a remoção automatizada não é possível. O uso dessa ferramenta é indicado quando um alerta do System Center Operations Manager (SCOM) de monitoramento de integridade é gerado, solicitando que o administrador remova os dados desnecessários dos bancos de dados do LYSS local no pool. Haverá um evento correspondente no log de eventos no front-end que disparou o alerta. Os detalhes do evento conterão informações sobre a quantidade de dados órfãos contidos no front-end e são disparados quando esses dados excedem determinados limites de pré-determinação

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale as ferramentas do Lync Server 2013, Resource Kit. A ferramenta é executada em máquinas associadas a um domínio onde o Lync Server e o Shell de gerenciamento do Lync Server 2013 estão instalados. A ferramenta usa um cmdlet do Shell de gerenciamento para identificar todos os servidores front-end no pool. Em segundo lugar, a ferramenta deve ser executada em um computador no pool que tenha o banco de dados **RtcLocal** instalado. Este banco de dados é usado pela ferramenta CleanupStorageServiceData para obter os detalhes de conexão necessários para se comunicar com o serviço de roteamento do Lync Server. por fim, a conta ou a credencial que invocar a ferramenta deve ter permissão de leitura/gravação para o compartilhamento de arquivo no qual deseja gravar o log de saída. Além disso, essa ferramenta depende do pool estar em um estado estável. Em essência, isso significa que todos os servidores front-end devem ser ativados e em execução, a instância do SQL Server LYNCLOCAL e o banco de dados do LYSS devem estar conectados ao e cada grupo de roteamento deve ter um conjunto completo de 1 servidores front-end primários e dois servidores front-end secundários.

</div>

<div>

## <a name="examples"></a>Exemplos

C: \\ arquivos de programa \\ Microsoft Lync Server 2013 \\ reskit \\ StorageService \> ImportStorageServiceData.exe

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a>DBAnalyze

<div>

## <a name="description"></a>Descrição

DBAnalyze é uma ferramenta de linha de comando que ajuda os administradores a coletar relatórios de análise sobre os bancos de dados do Lync Server 2013. O DBAnalyze tem os seguintes modos: diagnóstico, dados do usuário, conferência, MCUs e fragmentação de disco:

  - **Modo**     de diagnóstico Cria um relatório que inclui informações sobre as tabelas (número de registros, fragmentação, tamanho dos dados e tamanho do índice), tamanhos de arquivos de dados e de log o último tempo de backup, distribuição de contatos entre servidores que estão executando o Microsoft Office Communications Server, o número médio de permissões, contatos, contêineres, assinaturas, publicações, pontos de extremidade por usuário, todos os usuários hospedados incorretamente, usuários que não podem ser roteados, o número médio de conferências organizadas por usuário, conferências agendadas, conferências ativas e a versão do banco
    
    <div>
    

    > [!NOTE]  
    > Executar o modo de diagnóstico pode afetar o desempenho do servidor.

    
    </div>

  - Modo de dados do **usuário**   Relata os dados de contato, contêiner, assinatura, publicação, permissão e grupo de contato para um usuário especificado ou para usuários que tenham esse usuário em suas listas de permissões e contatos. Este modo também relata dados de resumo para conferências que um usuário organiza ou é convidado.

  - **Modo**     de conferência Relata dados detalhados para uma conferência específica, incluindo todos os detalhes de tempo de agenda da conferência, a lista de convidados, a lista de tipos de mídia permitidos para a conferência, active MCUs (unidades de controle multiponto), a lista de participantes ativa e o estado de sinalização de cada participante.

  - **Decodificar ID**    da reunião Decodifica uma ID de reunião PSTN (rede telefônica pública comutada) especificada pela opção **/pstnid** , mas não se conecta ao back-end para obter informações detalhadas.

  - **Resolver conferência**     Decodifica uma ID de reunião PSTN especificada pela opção **/pstnid** e exibe informações sobre a conferência indicada pela ID.

  - **Modo MCUs**    Relata a ID, o tipo de mídia, a URL, o status de pulsação, a carga de conferência e a carga de participante de cada MCU no pool.

  - Modo de fragmentação de **disco**    Exibe o status de fragmentação de todos os discos.

Essa ferramenta pode ser usada para diagnosticar vários problemas ou para ajudar os administradores com o planejamento de capacidade. Por exemplo, se a maioria dos usuários hospedados no servidor A escolher usuários hospedados no servidor B como seus contatos, o administrador pode mover os usuários no servidor A para o servidor B para reduzir o tráfego entre servidores.

</div>

<div>

## <a name="output"></a>Saída

Esta ferramenta produz relatórios predefinidos sobre o banco de dados do Lync Server 2013. **Caminho:** % ProgramFiles% \\ Microsoft Lync Server 2013 \\ reskit

</div>

<div>

## <a name="purpose"></a>Finalidade

Para instalar o Dbanalyze.exe, copie-o para uma pasta local e execute a ferramenta. Para usar a ferramenta, execute o seguinte comando a partir da linha de comando.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` As descrições para as opções de linha de comando são mostradas abaixo.

![Opções de linha de comando para Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Opções de linha de comando para Dbanalyze.exe.")

</div>

<div>

## <a name="requirements"></a>Requisitos

**Computador** O DBAnalyze pode ser executado apenas de um computador associado ao domínio que tenha o Lync Server 2013 instalado.

**Rede** O computador deve poder se conectar ao banco de dados back-end.

**Software** Os componentes de software do Lync Server 2013 devem ser instalados antes de executar o DBAnalyze.

**Usuários** do A tabela abaixo mostra os administradores que têm as permissões necessárias para acessar os bancos de dados do Lync Server 2013.

![Tabela de permissões para Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tabela de permissões para Dbanalyze.exe.")

<div>


> [!NOTE]  
> Uma conta de administrador local é necessária para <STRONG>/Report:</STRONG> modo de disco.



</div>

</div>

<div>

## <a name="examples"></a>Exemplos

Veja a seguir exemplos de comandos válidos do Dbanalyze.exe:

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>Resumo

O DBAnalyzer fornece aos administradores uma rápida e fácil análise de bancos de dados do Lync Server 2013.

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

A ferramenta ImportStorageServiceData Resource Kit permite a reimportação da fila e dos dados de ponto de extremidade que foram liberados do serviço de armazenamento (LYSS) de volta para o serviço de armazenamento.

<div>

## <a name="description"></a>Descrição

Os dados liberados do serviço de armazenamento podem ter sido automáticos (periódicos) com base no status do item da fila ou no tamanho do banco de dados. Isso pode ter acontecido devido à invocação manual do cmdlet de failover do pool ou do cmdlet StorageServiceFullFlush (que o cmdlet de failover do pool invoca). Observe que, preferencialmente, os dados não devem ser importados se qualquer tamanho do banco de dados do serviço de armazenamento (LYSS) no front-ends estiver acima do nível normal, porque isso provavelmente fará com que mais dados sejam exportados de volta. Além disso, qualquer problema que possa ter contribuído com erros que fizeram com que a fila de serviço de armazenamento cresça deve primeiro ser resolvido (por exemplo, erros de ponto de extremidade do Exchange, problemas de rede ou outros problemas).

**Cenário 1:** durante o failover do pool, os arquivos podem ser liberados do serviço de armazenamento para cada front-end. Após a conclusão do failover, a ferramenta deve ser executada para reimportar os dados.

**Cenário 2:** os dados estão sendo liberados automaticamente todos os dias ou em resposta ao banco de dados do serviço de armazenamento excedendo determinados limites de tamanho (por exemplo, 60%, 80%, 90% completo). Os dados automaticamente liberados devem ser reimportados rotineiramente pelo administrador. Na situação acima, se o pacote SCOM que está sendo monitorado não for implantado, haverá eventos para o serviço de armazenamento do Lync Server relacionado aos dados que estão sendo liberados do serviço de armazenamento. IDs de evento de 32075 (operação de liberação completa iniciada), 32076 (Full flush concluído), 32082 (liberação de nível de manutenção iniciada), 32083 (liberação de nível de manutenção concluída), 32089 (liberação ocorrida devido ao preenchimento de banco de dados). Observação essas IDs de evento correspondem à versão RTM. Quando um administrador vê esses eventos, significa que há arquivos que foram liberados. Esses dados devem ser importados rotineiramente de volta usando essa ferramenta, por exemplo, uma vez por semana.

Para a versão de serviço online, se o monitoramento de integridade do SCOM Pack para Lync Server for implantado, há novos alertas que podem ser gerados, o que pede ao administrador para reimportar novamente os dados liberados para o serviço de armazenamento. Haverá um evento correspondente no log de eventos do servidor front-end que disparou o alerta. O evento fornecerá uma descrição do caminho pai no qual os arquivos de dados liberados estão localizados, bem como o número de arquivos que atendem aos critérios de alerta. Os critérios de alerta é que há X ou mais arquivos sob o caminho pai específico, que têm pelo menos Y dias (onde X e Y são predefinidos no StorageService, mas podem ser substituídos alterando o arquivo APPCONFIG.) Dois exemplos de eventos que podem acionar o alerta de integridade são mostrados abaixo, com a diferença que é o caminho pai. Uma possibilidade está no compartilhamento de arquivos do serviço Web, enquanto a outra possibilidade é o diretório de dados do aplicativo local de cada front-end. (por exemplo c: \\ ProgramData \\ Microsoft \\ Lync Server \\ StorageService). O administrador executará essa ferramenta reskit.

Essa ferramenta aumentará a carga de CPU e de e/s no front-end em que está sendo executado, bem como outros front-ends, na situação em que os dados não são de Propriedade do front-end em que a ferramenta é executada. É recomendável executar esta ferramenta quando os front-ends não estão sob carga intensa de CPU e e/s, por exemplo fora do horário de pico. Em segundo lugar, essa ferramenta pode ser de 2 a 3 minutos para importar um arquivo de dados. Tenha isso em mente ao estimar por quanto tempo a ferramenta será executada. O arquivo de log detalhado gerado pela ferramenta será exibido, por padrão, no repositório de arquivos. Exclua-o se não houver erros relatados, pois o arquivo de log pode ter dezenas de MB ou mais.

![Exemplos de eventos do log de eventos do servidor de armazenamento.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Exemplos de eventos do log de eventos do servidor de armazenamento.")

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale as ferramentas do Lync Server 2013, Resource Kit. A ferramenta é executada em máquinas Unidas por domínio onde o Lync Server e o Shell de gerenciamento do Lync Server estão instalados. A ferramenta usa um cmdlet do Shell de gerenciamento para identificar todos os servidores front-end no pool. Em segundo lugar, a ferramenta deve ser executada em um computador no pool que tenha o banco de dados **RtcLocal** instalado. Este banco de dados é usado pela ferramenta para recuperar o local do compartilhamento de arquivo WEBSERVICE do pool. Além disso, antes de usar a ferramenta, cada servidor front-end deve primeiro habilitar a comunicação remota do Windows PowerShell usando **Enable-PSRemoting** em cada servidor de front-end, bem como a máquina da qual a ferramenta é executada. Caso contrário, os comandos remotos do Windows PowerShell dessa ferramenta falharão. A comunicação remota do Windows PowerShell pode ser desativada em todos os servidores front-end no pool após sua conclusão. Por fim, a conta ou a credencial que invoca a ferramenta deve ter permissão de leitura/gravação no compartilhamento de arquivo WebService para o pool em que eles estão executando essa ferramenta. Caso contrário, a ferramenta irá falhar com erros de permissão de es.

<div>


> [!NOTE]  
> No Windows Server 2012, o Windows PowerShell Remoting é habilitado por padrão, mas não no sistema operacional Windows Server 2008.



</div>

</div>

<div>

## <a name="examples"></a>Exemplos

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

</div>

</div>

<div>

## <a name="lcssync"></a>LCSSync

A ferramenta LCSSync ajuda a implantar o software de comunicação do Lync Server 2013 em um ambiente de várias florestas. Essa ferramenta é usada para sincronizar usuários e grupos de florestas de usuários diferentes como um objeto de contato dos serviços de domínio Active Directory para uma floresta central onde o Lync Server 2013 está instalado.

<div>

## <a name="description"></a>Descrição

O LCSSync usa os objetos de contato do serviços de domínio do Active Directory sincronizados na floresta central para habilitar usuários para o Lync Server. Para fornecer logon único, a conta de usuário principal deve ser mapeada para o objeto de contato dos serviços de domínio Active Directory na floresta central do Lync Server 2013. Essa ferramenta ajuda a executar esse mapeamento. Esta ferramenta fornece modelos para a criação de agentes de gerenciamento no Microsoft Identity Integration Server.

</div>

<div>

## <a name="summary"></a>Resumo

A ferramenta LCSSync ajuda a implantar o Lync Server em um ambiente de várias florestas.

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

A ferramenta LookupUserConsole exibe informações de roteamento internas do Lync Server sobre usuários específicos. Essas informações podem ser úteis para o suporte pessoal da Microsoft no diagnóstico de problemas de implantação e roteamento.

<div>

## <a name="description"></a>Descrição

A execução de LookupUserConsole.exe abrirá um prompt de comando que aceita endereços SIP e tenta exibir informações de roteamento internas do Lync Server relacionadas a eles. Digite **Exit** para sair da ferramenta LookupUserConsole.

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale as ferramentas do Lync Server 2013, Resource Kit. A ferramenta é executada em máquinas Unidas por domínio onde o Lync Server está instalado

</div>

<div>

## <a name="examples"></a>Exemplos

C: \\ arquivos de programa \\ Microsoft Lync Server 2013 \\ reskit \>LookupUserConsole.exe

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

</div>

</div>

<div>

## <a name="msturnping"></a>MsTurnPing

A ferramenta MSTurnPing permite que um administrador do software de comunicações do Microsoft Lync Server 2013 Verifique o status dos servidores que executam o perímetro de áudio/vídeo e os serviços de autenticação de áudio/vídeo, bem como os servidores que estão executando os serviços de política de largura de banda na topologia.

<div>

## <a name="description"></a>Descrição

A ferramenta MSTurnPing permite que um administrador do software de comunicações do Lync Server 2013 Verifique o status dos servidores que executam o perímetro de áudio/vídeo e os serviços de autenticação de áudio/vídeo, bem como os servidores que estão executando os serviços de política de largura de banda na topologia.

A ferramenta permite que o administrador execute os seguintes testes:

1.  Teste de servidor de borda a/V: a ferramenta realiza testes em todos os servidores de borda a/V na topologia fazendo o seguinte:
    
      - Verificar se o serviço de autenticação de áudio/vídeo do Lync Server foi iniciado e se pode emitir credenciais adequadas.
    
      - Verificando se o serviço de borda de áudio/vídeo do Lync Server foi iniciado e pode alocar os recursos na borda externa com êxito.

2.  Teste do serviço de política de largura de banda: a ferramenta realiza testes em todos os servidores que estão executando os serviços de política de largura de banda na topologia fazendo o seguinte:
    
      - Verificar se o serviço de política de largura de banda (autenticação) do Lync Server foi iniciado e pode emitir credenciais adequadas.
    
      - Verificando se o serviço de política de largura de banda (núcleo) do Lync Server foi iniciado e pode executar a verificação de largura de banda com êxito.

Essa ferramenta deve ser executada em um computador que faça parte da topologia e tenha o repositório local instalado.

</div>

<div>

## <a name="output"></a>Saída

A ferramenta gera os resultados de cada uma das operações.

  - Se o teste **AudioVideoEdgeServer** for executado, a ferramenta produzirá o seguinte:
    
      - Os resultados do teste dos computadores que fornecem o serviço de autenticação de áudio/vídeo do Lync Server na topologia
    
      - Os resultados do teste dos computadores que fornecem o serviço de borda de áudio/vídeo do Lync Server na topologia

  - Se o teste **BandwidthPolicyServer** for executado, a ferramenta produzirá o seguinte:
    
      - Os resultados do teste dos computadores que fornecem o serviço de política de largura de banda (autenticação) do Lync Server na topologia
    
      - Os resultados do teste dos computadores que fornecem o serviço de política de largura de banda (principal) do Lync Server na topologia

</div>

<div>

## <a name="requirements"></a>Requisitos

  - Essa ferramenta deve ser executada em um computador que esteja na topologia e que tenha o repositório local.

  - A ferramenta deve ser executada como administrador que tenha acesso ao repositório local.

</div>

<div>

## <a name="examples"></a>Exemplos

Veja a seguir um exemplo de entrada da ferramenta.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para os administradores do Lync Server 2013 que desejam verificar o status dos servidores que estão executando o áudio/vídeo e serviços de política de largura de banda.

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>Visualizador de configuração de rede

O Visualizador de configuração de rede pode ser usado pelos administradores do software de comunicações do Microsoft Lync Server 2013 para exibir a topologia de rede do controle de admissão de chamadas (CAC) para uma empresa que é configurada para permitir sessões de comunicação em tempo real, como chamadas de voz ou vídeo com base na capacidade de largura de banda especificada. Lync Server 2013 os administradores definem políticas de CAC, que são impostas pelos serviços de política de largura de banda que são instalados com o Lync Server 2013.

<div>

## <a name="description"></a>Descrição

O Visualizador de configuração de rede (NetworkConfigurationViewer.exe) permite que os administradores realizem as seguintes tarefas:

  - Carregar e exibir a topologia de rede do CAC de uma implantação do Lync Server 2013 em um formato gráfico.

  - Carregar e exibir a topologia de rede do CAC de um arquivo de log do servidor de política de largura de banda em um formato gráfico.

  - Salve e armazene a topologia de rede do CAC em um formato XML no disco.

  - Salve e armazene o diagrama de topologia de rede do CAC no formato JPG ou BMP.

  - Exibir dados de configuração da topologia de rede do CAC.

  - Exibir a topologia de rede do CAC em um estilo de exibição de árvore.

  - Definir conectores personalizados para links de topologia de rede do CAC (por exemplo, links de site para região, região para região e site para site).

  - Exibir as informações do site de topologia de rede do CAC, as informações de região e as políticas de largura de banda e os links de rede provisionados.

</div>

<div>

## <a name="purpose"></a>Finalidade

Exibir links de topologia de rede do CAC Enterprise em uma interface gráfica.

</div>

<div>

## <a name="examples"></a>Exemplos

**Carregar e exibir a topologia de rede do CAC de uma implantação do Lync Server 2013 em um formato gráfico:** Lync Server 2013 os administradores podem carregar e exibir a configuração da topologia de rede do CAC em qualquer computador do Lync Server 2013 usando a opção de **download de configuração de rede** , conforme mostrado na figura abaixo. A ferramenta falhará ao baixar ou exibir essa configuração quando implantada em um computador que não tenha conectividade com o repositório de configuração do Lync.

![Baixar a configuração de rede.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Baixar a configuração de rede.")

**Carregar e exibir a topologia de rede do CAC de um arquivo de log do servidor de política de largura de banda em um formato gráfico:** Servidores de política de largura de banda do Lync Server 2013 salve a topologia de rede do CAC como parte do mecanismo de log no local de compartilhamento de arquivos do Lync Server 2013. Os administradores do Lync Server podem exibir esse arquivo em um formato gráfico usando a opção **abrir configuração de rede** , conforme mostrado abaixo.

![Abrir um arquivo de log do servidor de política de largura de banda.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Abrir um arquivo de log do servidor de política de largura de banda.")

Salvar e armazenar a topologia de rede do CAC em um formato XML no disco: os administradores do Lync Server 2013 podem salvar o arquivo de configuração da topologia de rede do CAC em um formato XML usando a opção **salvar uma cópia da configuração de rede** , conforme mostrado abaixo. O arquivo de configuração salvo pode ser usado offline para fins de exibição gráfica.

![Salvar a configuração de rede como um arquivo XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Salvar a configuração de rede como um arquivo XML.")

Salvar e armazenar o diagrama de topologia de rede do CAC no formato JPG ou BMP: os administradores do Lync Server 2013 podem salvar a configuração da topologia de rede do CAC em um formato gráfico (formatos de arquivo JPG e BMP) usando a opção **salvar diagrama de configuração de rede como imagem** , conforme mostrado abaixo.

![Salvar a configuração de rede como uma imagem.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Salvar a configuração de rede como uma imagem.")

**Exibir dados de configuração de topologia de rede do CAC:** Lync Server 2013 os administradores podem exibir dados de configuração de rede relacionados, como regiões de rede, sites de rede, perfis de largura de banda e endereços IP de sub-rede de site em um formato textual, usando a opção Exibir dados de configuração de rede, conforme mostrado abaixo.

![Exibir dados de configuração de rede.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Exibir dados de configuração de rede.")

**Exibir a topologia de rede do CAC em um estilo de exibição de árvore:** Lync Server 2013 os administradores podem exibir dados de configuração de rede relacionados em um estilo de exibição de árvore gráfica usando o painel de controle no lado esquerdo da janela da ferramenta, conforme mostrado abaixo.

![Exibir dados de configuração de rede em um modo de exibição de árvore.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Exibir dados de configuração de rede em um modo de exibição de árvore.")

**Definir conectores personalizados para links de topologia de rede do CAC (como links de site a região, região para região e site a site):** Lync Server 2013 os administradores podem definir conectores gráficos personalizados para os links WAN de configuração de rede do CAC usando a opção configurações, conforme mostrado abaixo. Isso ajuda a diferenciar entre vários tipos de links de rede que são provisionados na configuração de rede.

![Definir conectores personalizados para a topologia de rede do CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definir conectores personalizados para a topologia de rede do CAC")

**Exibir as informações do site de topologia de rede do CAC, as informações de região e as políticas de largura de banda provisionadas:** Lync Server 2013 os administradores podem exibir informações de região de rede do CAC relacionadas, informações do site e informações de provisionamento de largura de banda do CAC usando opções mostradas abaixo. (Por exemplo, clique em **informações** em uma região de rede ou em um objeto de site de rede.)

![Definir conectores personalizados para sua rede.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definir conectores personalizados para sua rede.")

</div>

<div>

## <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para os administradores do Lync Server 2013 que gostariam de exibir a topologia de rede do CAC para sua implantação em um formato gráfico.

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>Agente de grupo de resposta Live

O aplicativo grupo de resposta oferece aos agentes a capacidade de acessar informações úteis em tempo real usando seu serviço Web interno. Infelizmente, nenhuma exibição gráfica desses dados está disponível fora do aplicativo. A ferramenta agente de grupo de resposta Live Resource Kit resolve esse problema fornecendo uma maneira simples e gráfica de acessar essas informações, aprimoradas com informações de software de comunicações do Microsoft Lync 2013 em tempo real, como a presença de outros agentes.

<div>

## <a name="description"></a>Descrição

Agente de grupo de resposta Live é um aplicativo do Windows que fornece a funcionalidade de entrada e de saída e algumas informações em tempo real (como associação de grupo e número atual de chamadas) para os agentes de grupo de resposta. Ele deve ser uma versão avançada da página de grupos de agentes (acessível do Lync 2013.

</div>

<div>

## <a name="purpose"></a>Finalidade

O aplicativo grupo de resposta enfileira as chamadas de entrada e roteia-as para os grupos de agentes. Para tomar decisões informadas sobre quais chamadas de serviço, os agentes podem acessar informações em tempo real sobre seus grupos de agentes, como quais outros agentes estão disponíveis e quantas chamadas estão aguardando em cada fila. Essas informações, inicialmente acessíveis apenas através do serviço de grupo de resposta, são disponibilizadas de forma intuitiva por agente de grupo de resposta ao vivo.

<div>

## <a name="features"></a>Recursos

A ferramenta agente de grupo de resposta do Live é criada no serviço do grupo de resposta e no SDK do Microsoft Lync 2013. Ele fornece aos agentes do grupo de resposta as informações e os recursos disponíveis no serviço do grupo de resposta (como associação de grupo, presença de outros agentes e número de chamadas em espera).

A figura abaixo ilustra a interface principal do agente do grupo de resposta em tempo real.

![A ferramenta agente de grupo de resposta ao vivo.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "A ferramenta agente de grupo de resposta ao vivo.")

Os três recursos principais a seguir estão disponíveis para agentes no agente de grupo de resposta em tempo real:

  - **Entrada/saída:** Ao contrário da página de grupos de agentes (acessível no Lync 2013), o agente de grupo de resposta Live permite que somente os agentes entrem ou de todos os grupos de agente ao mesmo tempo. Este aplicativo fornece três maneiras rápidas para que os agentes entrem ou esgotam:
    
      - Clique nos botões de entrada/saída (verde e vermelho) no aplicativo.
    
      - Clique com o botão direito do mouse no ícone da bandeja do sistema e selecione entrar ou sair.
    
      - Usando atalhos de teclado configuráveis.

  - **Associação de Grupo:** Quando um grupo de agentes é selecionado, o agente de grupo de resposta Live exibe a lista de agentes desse grupo no painel direito. Se o Lync 2013 estiver em execução no mesmo computador que este aplicativo, as informações de presença e o cartão de visita serão exibidos no agente do grupo de resposta em tempo real. Os agentes podem enviar uma mensagem instantânea ou ligar para outros agentes diretamente de lá.

  - **Estatísticas em tempo real:** Agente de grupo de resposta Live fornece estatísticas em tempo real para todos os grupos de agentes. A frequência de atualização é um minuto. Quando uma chamada é atendida por um grupo de resposta, um indicador visual é adicionado ao lado do nome do grupo com o número atual de chamadas em fila. Pausar o ponteiro sobre um grupo também exibe o tempo de espera mais longo.

</div>

</div>

<div>

## <a name="requirements"></a>Requisitos

O agente de grupo de resposta Live requer o .NET Framework 4,0. Além disso, para aproveitar os recursos de cartão de visita e presença, o Lync 2013 deve estar instalado localmente (e estar sendo executado).

<div>

## <a name="configuration"></a>Configuração

O agente de grupo de resposta Live pode ser personalizado para preferências individuais usando a caixa de diálogo opções no aplicativo. Além disso, o administrador pode definir o endereço de host padrão editando diretamente a propriedade defaultHostAddress do arquivo RGAgentLive.exe.config.

A figura abaixo ilustra a caixa de diálogo opções que os agentes podem usar para configurar o endereço do host e as teclas de atalho. Essa caixa de diálogo é acessada clicando-se no botão Opções no canto superior direito da interface principal.

![A caixa de diálogo opções do agente de grupo de resposta.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "A caixa de diálogo opções do agente de grupo de resposta.")

As três configurações a seguir podem ser personalizadas na configuração do agente de grupo de resposta:

  - Endereço do host: normalmente, esse é o FQDN do pool da Web pertencente ao pool inicial do agente. O endereço do serviço do grupo de resposta exato é automaticamente derivado do plano de fundo nessas informações (acrescentando o caminho correto após o host).

  - Atalhos: os atalhos exatos para entrar/sair podem ser personalizados. A única limitação é que ambos os atalhos devem conter a chave "logotipo do Windows" (além de pelo menos outra chave).

  - Comece com o Windows: o aplicativo pode ser configurado para iniciar automaticamente com o Windows.

</div>

</div>

<div>

## <a name="examples"></a>Exemplos

A figura abaixo ilustra como chamar ou enviar uma mensagem instantânea para outro agente clicando com o botão direito do mouse no contato no painel direito.

![Fazer uma chamada ou enviar uma mensagem instantânea.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Fazer uma chamada ou enviar uma mensagem instantânea.")

A figura abaixo ilustra como o agente de grupo de resposta Live exibe o número atual de chamadas na fila e o tempo de espera mais longo entre todas essas chamadas de entrada.

![Exibir informações da fila.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Exibir informações da fila.")

</div>

<div>

## <a name="summary"></a>Resumo

Entrada e saída rápidas, associação de grupo e estatísticas básicas em tempo real são recursos interessantes de agente de grupo de resposta que estão disponíveis apenas fora do aplicativo do serviço de grupo de resposta. Com a ferramenta de agente de grupo de resposta Live Resource Kit, os administradores do Lync podem fornecer seus agentes com um aplicativo do Windows que permite que eles realizem tarefas de forma mais rápida e gráfica.

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

SEFAUtil (ativação de recurso de extensão secundária) é uma ferramenta de linha de comando que permite que os administradores de software de comunicações e assistência técnica do Microsoft Lync Server 2013 configurem o toque, o encaminhamento de chamada, o toque simultâneo, as configurações de chamada de equipe e o recebimento de chamadas em grupo em nome de um usuário do Lync Server 2013. A ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico. A ferramenta SEFAUtil permite que o administrador ative/desative/modifique o encaminhamento de chamadas ou tocando simultaneamente em nome do usuário. O administrador pode especificar o destino (na forma de um URI SIP) ou usar um destino que já tenha sido publicado pelo usuário. Essa ferramenta também permite que os administradores adicionem ou removam representantes ou membros do grupo de chamada de equipe em nome do usuário. Essa ferramenta foi criada com o Microsoft Unified Communications Managed API (UCMA) 3,0 e exige que os administradores criem um aplicativo confiável no repositório de gerenciamento central para o SEFAUtil

SEFAUtil (ativação de recurso de extensão secundária) permite que os administradores do Lync Server 2013 e do helpdesk configurem o toque, o encaminhamento de chamada, o toque simultâneo, as configurações de chamada de equipe e o recebimento de chamadas em grupo em nome de um usuário do Lync Server 2013. Essa ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico.

<div>

## <a name="description"></a>Descrição

A versão atual do SEFAUtil é apenas uma ferramenta de linha de comando; Não há interface gráfica de usuário de suporte. Essa ferramenta é baseada na API gerenciada de comunicações unificadas da Microsoft (UCMA) 3,0. Os recursos desta ferramenta permitem que os administradores e os agentes de assistência técnica façam o seguinte:

  - Exibir todas as configurações de roteamento de chamadas para um usuário (inclui encaminhamento de chamada, delegação, toque simultâneo, chamada de equipe e recebimento de chamadas de grupo)

  - Habilitar/desabilitar/modificar a configuração de encaminhamento de chamadas (inclui destino e timer sem resposta)

  - Habilitar/Desabilitar/Modificar configurações imediatas de encaminhamento de chamadas

  - Habilitar/Desabilitar/Modificar configurações de delegação

  - Habilitar/Desabilitar/Modificar configurações do grupo de chamada de equipe
    
    <div>
    

    > [!NOTE]  
    > Novo no Lync Server 2013 SEFAUtil Tool

    
    </div>

  - Habilitar/Desabilitar/Modificar configurações de toque simultâneo (inclui destino)
    
    <div>
    

    > [!NOTE]  
    > Novo no Lync Server 2013 SEFAUtil Tool

    
    </div>

  - Habilitar/Desabilitar/Modificar configurações de recebimento de chamadas de grupo
    
    <div>
    

    > [!WARNING]  
    > Novo no Lync Server 2013 SEFAUtil Tool

    
    </div>

Esta ferramenta tem as seguintes limitações:

  - Suportado somente para usuários hospedados em um pool do Lync Server

  - Não há suporte para a edição em massa das configurações de roteamento de chamadas para vários usuários

</div>

<div>

## <a name="output"></a>Saída

A versão atual desta ferramenta fornece somente a saída na janela de prompt de comando. Para obter detalhes, consulte a seção exemplos mais adiante neste documento.

</div>

<div>

## <a name="purpose"></a>Finalidade

A seguir estão alguns dos principais cenários em que essa ferramenta pode ser usada:

  - Bob é um executivo e foi movido para a telefonia do Lync Server. Ele tem delegação em seu sistema PBX existente. Como parte da migração para o Lync, o administrador pode configurar o roteamento de Bob para refletir sua configuração de delegação pré-existente.

  - Alice é viajantes e percebe que está esperando uma chamada importante de um de seus clientes. No entanto, ela está em um hotel e não tem acesso a um computador. Ele chama o helpdesk e solicita que eles encaminhem para seu número de celular todas as chamadas feitas para seu número de trabalho. O pessoal da assistência técnica pode fazer a configuração em seu nome.

  - As chamadas de Joe para seu número de trabalho estão indo para sua caixa postal móvel sempre que estiver trabalhando; no entanto, as coisas parecem estar funcionando corretamente na maioria dos outros locais. O técnico da assistência técnica pode exibir a configuração de roteamento de Joe e descobre que Joe tem o toque simultâneo configurado para seu celular. O técnico faz uma Joe sobre a cobertura móvel em seu escritório e é capaz de determinar que a regra de toque simultâneo é o que está fazendo com que as chamadas vá para a caixa postal móvel de Joe, quando sua cobertura de rede for ruim.

  - Mike é um novo funcionário da Contoso e ele está ingressando em uma nova equipe na qual todos os membros estão configurados para chamada em equipe, quando habilitados para o Microsoft Lync, o administrador pode definir as configurações do grupo de chamada de equipe para incluir todos os membros da equipe, além disso, o administrador adiciona Mike como um membro do grupo de chamada de equipe para cada um dos membros em

  - Uma prática de atendimento ao cliente no departamento de recursos humanos da Contoso é fornecer serviço pessoal para todos os chamadores desde a primeira chamada. Como todos os membros do departamento ficam muito próximos uns dos outros, ter todos os telefones tocando ao mesmo tempo com a chamada de equipe é muito prejudicial para a equipe. Para fornecer o melhor serviço sem interromper os membros da equipe, o administrador do Lync aproveita o recurso de recebimento de chamadas em grupo. O administrador adiciona todos os membros do departamento a um grupo de retirada e se comunica com o número do grupo de recebimento do departamento. Quando Paula estiver ausente da sua mesa, Joe notificará o toque do telefone e continuará a responder à chamada em sua mesa.

</div>

<div>

## <a name="requirements"></a>Requisitos

A ferramenta SEFAUtil pode ser executada apenas em um computador que faz parte de um pool de aplicativos confiáveis. UCMA 3,0 deve ser instalado no computador. Para executar a ferramenta, um novo aplicativo confiável com a ID do aplicativo SEFAUtil deve ser criado nesse pool.

**Criar um novo aplicativo confiável para a ferramenta SEFAUtil**

1.  A ferramenta SEFAUTil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis. Se necessário, a adição de um pool como um novo pool de aplicativos confiáveis pode ser feita por meio do Shell de gerenciamento do Lync Server com o seguinte cmdlet:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > O UCMA 3,0 deve ser instalado em qualquer computador que será usado para executar a ferramenta SEFAUtil.

    
    </div>

2.  Um aplicativo confiável precisa ser definido na topologia da ferramenta SEFAUtil. Para definir o SEFAUtil como um novo aplicativo confiável, use o Shell de gerenciamento do Lync Server e execute o seguinte cmdlet:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Uma porta diferente pode ser usada, se necessário.

    
    </div>

3.  As alterações de topologia precisam ser habilitadas. Habilitar as alterações de topologia pode ser feito por meio do Shell de gerenciamento do Lync Server executando o seguinte cmdlet:
    
        Enable-CsToplogy

4.  Se necessário, instale as ferramentas do kit de recursos do Lync Server 2013 no servidor que será usado para executar a ferramenta SEFAUtil (o servidor deve fazer parte de um pool de aplicativos confiáveis).

5.  Verifique se o SEFAUtil está funcionando corretamente. Para fazer isso, execute a ferramenta a partir de um prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamadas de um usuário na implantação. Por padrão, a ferramenta estará localizada em: "... \\ Arquivos de programa \\ Microsoft Lync Server 2013 \\ reskit ". Para exibir as configurações de encaminhamento de chamadas de um usuário, use o seguinte comando:
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    As configurações de encaminhamento de chamadas do usuário devem ser exibidas.

<div>

## <a name="group-call-pickup"></a>Recebimento de chamadas em grupo

O recebimento de chamadas de grupo requer configuração adicional no Lync Server para que o recurso seja totalmente habilitado. Antes de atribuir grupos de recebimento aos usuários, consulte a documentação do produto de recebimento de chamadas em grupo para obter as etapas de planejamento e implantação desse recurso.

</div>

</div>

<div>

## <a name="examples"></a>Exemplos

<div>

## <a name="display-current-call-handling-settings"></a>Exibir as configurações de tratamento de chamadas atuais

O comando a seguir exibe o tratamento de chamadas para o usuário. `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> Este exemplo usa a opção <STRONG>/Server</STRONG> para especificar o Lync Server ao qual se conectar.



</div>

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>Definir o destino de chamada para encaminhamento/sem resposta

Este exemplo define o destino de chamada de encaminhamento/sem resposta e o atraso de anel. Aqui, a opção/Server não é fornecida; O SEFAUtil tenta descobrir a descoberta automática do Lync Server.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>Habilitar o encaminhamento de chamadas imediatamente

Este exemplo habilita imediatamente o encaminhamento de chamada para outro usuário.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a>Desabilitar o encaminhamento de chamadas imediatamente

Este exemplo desabilita imediatamente o encaminhamento de chamadas.

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Adicionar um usuário como um representante e configurar o toque simultâneo dos representantes

Este exemplo adiciona um usuário como um representante e configura o toque simultâneo dos representantes.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>Alterar regra de toque simultâneo dos representantes

Este exemplo altera a regra de toque simultâneo definida no exemplo anterior para a regra de toque atrasado.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a>Remover o representante

Este exemplo remove o representante.

<div>


> [!NOTE]  
> Quando o último representante é removido, o toque de representante é automaticamente desabilitado.



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Adicionar um representante e configurar a regra de Call-Forward para representantes

Este exemplo adiciona um representante e configura a regra de direcionamento de chamada para representantes.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Habilitar o toque simultâneo e definir um número de destino

Este exemplo habilita o toque simultâneo e define um número de destino de toque simultâneo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> Para alterar o número de destino de toque simultâneo de um usuário que já tenha o toque simultâneo habilitado, mantenha o comando com a opção/enablesimulring, caso contrário, o número de destino não será alterado.



</div>

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a>Desabilitar toque simultâneo

Este exemplo desabilita o toque simultâneo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Adicionar um membro da equipe para Team-Call e configurar o toque simultâneo para o grupo de membros Team-Call

Este exemplo adiciona um membro da equipe ao grupo de chamada de equipe de um usuário e habilita o toque simultâneo para o grupo de chamada de equipe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> A adição de um membro ao grupo de chamada de equipe de um usuário alternará automaticamente a simultâneo de toque simultâneo dos usuários para toque simultâneo o grupo de chamada de equipe.



</div>

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a>Remover um membro do grupo de Team-Call

Este exemplo remove um membro da equipe do grupo de chamada de equipe de um usuário.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> Se o membro que está sendo removido for o único membro do grupo de chamada de equipe, tocar simultaneamente no grupo de chamada de equipe será automaticamente desabilitado.



</div>

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>Definir o toque atrasado para o grupo de Team-Call

Este exemplo altera o anel atrasado para a configuração de tempo do grupo de chamada de equipe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a>Habilitar Team-Call

Este exemplo habilita a chamada de equipe para um determinado usuário.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> Se o grupo de chamada de equipe do usuário não tiver membros, a chamada de equipe não será habilitada.



</div>

**Output**

</div>

<div>

## <a name="disable-team-call"></a>Desabilitar Team-Call

Este exemplo desabilita a chamada de equipe para um determinado usuário.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Habilitar o recebimento de chamadas em grupo e atribuir um grupo de recebimento a um usuário

Este exemplo atribui um grupo de recebimento a um usuário e habilita o recebimento de chamadas em grupo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a>Desabilitar o recebimento de chamadas em grupo

Este exemplo desabilita o recebimento de chamadas em grupo para um determinado usuário.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> Quando você desabilita o recebimento de chamadas em grupo para um usuário, o número do grupo que foi atribuído ao usuário não é mantido. Se, subsequentemente, você quiser reabilitar o recebimento de chamadas em grupo para esse usuário, você deve atribuir o número de grupo novamente com a opção/enablegrouppickup.



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a>SYSPrep.ps1

<div>

## <a name="description"></a>Descrição

SYSPrep.ps1 é um script do Windows PowerShell que instalará os seguintes pré-requisitos do Lync Server 2013 no seu computador do sistema operacional Windows Server 2008.

  - Microsoft .NET Framework 4,5

  - Microsoft SQL Server Express

  - Windows PowerShell versão 3,0

  - Visual C++ 2010 Redistributable

  - Atualizações do Internet Information Server

  - Windows Identity Foundation

  - Arquivos principais do Lync Server 2013

Embora o nome do script seja semelhante à ferramenta de preparação do sistema para os sistemas operacionais Microsoft Windows, eles são diferentes. Este script só instalará os pré-requisitos necessários para o Lync Server 2013. Após a instalação desses pré-requisitos, a ferramenta SYSPrep do Windows pode ser usada para criar uma imagem do servidor.

</div>

<div>

## <a name="requirements"></a>Requisitos

Antes de executar o script SYSPrep.ps1, você deve copiar os arquivos de pré-requisito para uma pasta local no computador do sistema operacional Windows Server 2008 (por exemplo, **D: \\ configuração)**. Essa pasta também deve incluir uma cópia dos arquivos do Lync Server 2013, especificamente **Setup.exe.** Os arquivos de pré-requisito podem ser baixados dos seguintes locais:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Requisito</th>
<th>Local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .NET Framework 4,5</p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows PowerShell versão 3,0</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual C++ 2010 Redistributable</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Atualizações do Internet Information Server</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup.exe</p></td>
<td><p>Copiar da mídia do Lync Server 2013</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a>Parâmetro

O parâmetro **– SetupFolder** aceita como um argumento o local do diretório dos arquivos de pré-requisito

</div>

<div>

## <a name="examples"></a>Exemplos

Para executar o script SYSPrep.ps1 e instalar os pré-requisitos do Lync Server 2013, execute o seguinte comando em um prompt de comando elevado:

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>Migração de comunicados de número não atribuído

A ferramenta de migração de comunicados de número não atribuído permite que um administrador do Lync mova a configuração de números não atribuídos que é atendida pelo aplicativo de comunicado de um pool ou servidor do Lync de origem para um servidor ou pool Lync de destino.

<div>

## <a name="description"></a>Descrição

A ferramenta de migração de comunicados de número não atribuído é um script do Windows PowerShell que move a configuração de números não atribuídos atendida pelo aplicativo de comunicado de um pool ou servidor de origem para um servidor ou pool diferente.

Quando executado, o script de migração de comunicados de número não atribuído executará as seguintes operações:

1.  Mova todos os arquivos de áudio usados pelos comunicados de número não atribuído do aplicativo de comunicado hospedado no servidor ou pool de origem para o repositório de arquivos do pool ou servidor de destino.
    
    <div>
    

    > [!NOTE]  
    > os arquivos de áudio são removidos do pool de origem depois que são copiados para o pool de destino.

    
    </div>

2.  Mova todos os comunicados de número não atribuídos configurados para o aplicativo de comunicado hospedado no servidor ou pool de origem para o servidor ou pool de destino.

3.  Reatribua todos os intervalos de números não atribuídos que são atendidos pelo aplicativo de comunicado hospedado no servidor ou pool de origem para o servidor de destino ou pool.

Depois de executar o script com êxito, todos os intervalos de números não atribuídos que foram atendidos pelo aplicativo de anúncio hospedado no servidor de origem ou pool serão agora atendidos com a mesma configuração pelo servidor ou pool de destino.

</div>

<div>

## <a name="output"></a>Saída

O script **move-CsAnnouncementConfiguration** indica na janela do Shell de gerenciamento do Lync de onde ele é executado com êxito ou falha da operação de migração.

Se a execução da operação for interrompida por qualquer erro, os intervalos de números não atribuídos que foram movidos com êxito para o destino permanecerão no destino em um formulário operacional e o restante dos intervalos de números não atribuídos a serem migrados permanecerá na origem também em um formulário operacional. Para migrar completamente o restante da configuração, execute novamente o script após resolver o erro.

</div>

<div>

## <a name="purpose"></a>Finalidade

O script de migração de comunicados de número não atribuído pode ser usado nos três cenários a seguir:

  - **Migrando definições de configuração para uma nova versão do Lync Server:** A Contoso está em processo de migração para o Lync Server 2013 e como parte do processo de migração o administrador do Lync Server gostaria de mover a configuração de números não atribuídos atendida pelo aplicativo comunicado da implantação do Lync Server 2010 para a nova implantação do Lync Server 2013. Para mover as definições de configuração, o administrador do Lync Server usa a ferramenta de migração de comunicados de número não atribuído.

  - Reverter **uma implantação do Lync server 2013 para o Lync server 2010:** Fatores de devido inesperados, a contoso tem que reverter a migração para a nova implantação do Lync Server 2013. Para minimizar as interrupções do serviço, o administrador do Lync Server usa a ferramenta de migração de comunicados de número não atribuído para reverter a configuração da implantação do Lync Server 2013 para a implantação do Lync Server 2010.

  - **Movimentação de dados entre implantações do Lync:** A Contoso está no processo de substituição de todos os servidores de um pool por servidores mais recentes. Sua estratégia é implantar um novo pool do Lync Server 2013, mover todos os dados do antigo para o novo pool e, em seguida, substituir o pool antigo. Depois que o novo pool é implantado, a ferramenta de migração de comunicados de número não atribuído é usada para mover a configuração do pool antigo para o novo.

<div>

## <a name="requirements"></a>Requisitos

Estes são os principais requisitos necessários para executar a ferramenta com êxito:

1.  O script deve ser executado em um computador que tenha o Shell de gerenciamento do Lync Server 2013 instalado.

2.  O aplicativo de anúncio deve ser implantado com êxito nos servidores ou pools de origem e destino.

<div>

## <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration script

O script Move-CsAnnouncementConfiguration requer os dois parâmetros descritos na tabela abaixo.

![Parâmetros move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parâmetros.")

</div>

</div>

</div>

<div>

## <a name="examples"></a>Exemplos

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>Mover a configuração de comunicados de número não atribuído de um pool do Lync Server 2010 para um pool do Lync Server 2013

Este exemplo move os anúncios de número não atribuído do pool de origem (Lync Server 2010) para o pool de destino (Lync Server 2013).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>Mover a configuração de comunicados de número não atribuído de um pool do Lync Server 2013 para um pool do Lync Server 2010

Este exemplo move os anúncios de número não atribuído do pool de origem (Lync Server 2013) para o pool de destino (Lync Server 2010).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>Dados de conferência da Web

A ferramenta Web conf data permite que um administrador do software de comunicações do Lync Server 2013 tenha mais controle sobre os dados associados a webconferências do organizador. Os cenários incluem a capacidade de excluir dados de reunião de um usuário específico com base em um critério de carimbo de data/hora.

<div>

## <a name="description"></a>Descrição

Essa ferramenta permite ao administrador executar as seguintes operações:

1.  Localizar todos os dados de Webconferência associados a um único usuário.

2.  Excluir todos os dados de Webconferência associados a um único usuário.

3.  Excluir todos os dados de Webconferência associados a um único usuário que seja mais antigo do que uma determinada data.

4.  Mova todos os dados de Webconferência associados a um único usuário quando esse usuário é movido de um pool para outro.

<div>


> [!NOTE]  
> As ferramentas do kit de recursos do Lync Server 2010 suportavam a transferência de todos os dados de Webconferência associados a um único usuário quando esse usuário é movido de um pool para outro. Essa funcionalidade foi agora preterida dessa ferramenta em favor do parâmetro <STRONG>MoveConferenceData</STRONG> . Para obter detalhes sobre esse parâmetro, consulte o cmdlet <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">move-CsUser</A> .



</div>

A ferramenta exclui dados de reunião somente para reuniões que estão inativas. As reuniões ativas (ou reuniões em sessões) não podem ser excluídas.

Essa ferramenta deve ser executada em um computador que esteja no mesmo pool do usuário de destino. O usuário cujos dados de conteúdo da reunião estão sendo gerenciados por essa ferramenta deve estar hospedado no mesmo pool de usuários.

</div>

<div>

## <a name="output"></a>Saída

Esta ferramenta gera os resultados de cada uma das operações:

  - Se uma consulta for executada, a ferramenta produzirá a lista de todas as pastas de dados de reunião inativas que têm esse usuário como organizador.

  - Se uma exclusão for executada, a ferramenta produzirá a lista de todas as pastas de dados de reunião cujos dados serão excluídos.

</div>

<div>

## <a name="requirements"></a>Requisitos

A ferramenta precisa ser executada no mesmo pool em que o organizador está hospedado no momento.

A ferramenta deve ser executada usando privilégios de administrador com acesso ao repositório de arquivos de conteúdo.

</div>

<div>

## <a name="examples"></a>Exemplos

A tabela a seguir descreve os parâmetros, alguns dos quais são usados nos exemplos.

![Parâmetros da ferramenta de dados de Webconferência.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parâmetros da ferramenta de dados de Webconferência.")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

O exemplo anterior mostra como funciona um comando de consulta. A saída de tal comando seria uma lista de todas as pastas de conteúdo de reunião que seriam afetadas por essa ferramenta.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

O anterior é um exemplo de um comando delete. O comando excluir removerá todas as pastas de reunião inativas deste usuário.

</div>

<div>

## <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para os administradores que precisam de controle mais preciso sobre os dados da reunião de conferência.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
