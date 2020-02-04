---
title: Documentação de ferramentas do kit de recursos do Lync Server 2013
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
ms.openlocfilehash: 511a4ee9920237e1671a44a2f7481b40fbeb8e1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Documentação de ferramentas do kit de recursos do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-01-09_

Este tópico descreve as ferramentas que fazem parte do kit de recursos do Lync Server 2013, incluindo a finalidade de cada ferramenta e exemplos de seu uso. O Lync Server 2013, ferramentas do Resource Kit ajudam a facilitar tarefas de rotina para administradores de ti que implantam e gerenciam o Lync Server 2013. Por exemplo, a ferramenta **Web Conf Data** pode ser usada para controlar facilmente os dados carregados pelos usuários durante uma reunião online. A ferramenta **SEFAUtil** pode ser usada para configurar o encaminhamento e as respostas de chamadas de representantes para os usuários. Incentivamos os administradores de ti a usar essas ferramentas para gerenciar com mais eficiência o Lync Server 2013.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Instalação das Ferramentas do Kit de Recursos

Para instalar o Lync Server 2013, ferramentas do Resource Kit, baixe **OCSReskit. msi**. Você pode baixar o instalador de ferramentas do kit de recursos a partir [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)do centro de download em.

Execute o **OCSResKit.msi** para fazer uma instalação simples. O. msi instala todas as ferramentas no seguinte caminho: **% arquivos de programas%\\Microsoft Lync Server 2013\\reskit**. As ferramentas que são executáveis autocontidos ficam nessa pasta. As ferramentas que também têm arquivos estão em suas próprias subpastas.

</div>

<div>

## <a name="supported-environments"></a>Ambientes com suporte

Para obter o melhor desempenho, as ferramentas do Lync Server 2013, do Resource Kit devem ser instaladas no mesmo ambiente e com as mesmas especificações necessárias para o Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Visão geral das Ferramentas do Kit de Recursos

A lista a seguir descreve as ferramentas fornecidas no kit de recursos do Lync Server 2013. Uma descrição de cada ferramenta, incluindo os requisitos e o uso do exemplo são abordados na seção a seguir.

  - ABSConfig

  - Monitor de Serviço da Política de Largura de Banda

  - Analisador de Utilização de Largura de Banda

  - Estacionador de Chamadas

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - Visualizador da Configuração de Rede

  - Agente do Grupo de Resposta em Tempo Real

  - SEFAUtil

  - SYSPrep.ps1

  - Migração de Comunicados de Número não Atribuído

  - Web Conf Data

</div>

<div>

## <a name="absconfig"></a>ABSConfig

A ferramenta de configuração de serviço de catálogo de endereços (ABSConfig) é uma ferramenta administrativa que ajuda administradores a personalizar a configuração de serviço de catálogo de endereços no Lync Server 2013. Essa ferramenta também habilita os administradores do Lync Server 2013 a restaurar as configurações de serviço de catálogo de endereços padrão.

<div>

## <a name="description"></a>Descrição

O ABSConfig é um aplicativo gráfico de interface do usuário que permite aos administradores configurar os atributos dos serviços de domínio Active Directory relacionados ao serviço de catálogo de endereços.

Veja aqui os principais cenários da ferramenta:

  - Para permitir que os administradores mapeiem atributos nos serviços de domínio Active Directory para os atributos do Lync Server 2013.

  - Permitir que os administradores especifiquem os atributos do Active Directory Domain Services a serem incluídos ou excluídos dos arquivos do Serviço de Catálogo de Endereços.

  - Permitir que os administradores restaurem as configurações padrão do Serviço de Catálogo de Endereços.

A ferramenta ABSConfig pode ser iniciada usando-se o arquivo absConfig. exe. A ferramenta é aberta na guia **Configurar atributos** . Esta tabela tem opções para mapear atributos dos serviços de domínio Active Directory para os campos de atributo do Lync Server 2013 e especificar quais usuários incluir ou excluir nos arquivos do serviço de catálogo de endereços com base em filtros de atributo específicos. Ela também tem opções para personalizar quais números telefônicos serão incluídos no arquivo do Catálogo de Endereços. A opção **Restaurar Padrões** permite aos administradores restaurar os valores padrão das configurações do Serviço de Catálogo de Endereços.

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>Alterações do Lync Server 2010

No Lync Server 2013 ferramenta de configuração do ABS, os atributos (linhas) podem ser removidos desmarcando a caixa de seleção "habilitar" para o atributo. Isso tem o mesmo efeito que excluir a linha no Lync Server 2010.

<div>


> [!NOTE]  
> A caixa de seleção Habilitar está na coluna da extrema direita; Talvez seja necessário rolar para a direita para ver a coluna



</div>

</div>

<div>

## <a name="output"></a>Resultado

A ABSConfig armazena a configuração do Serviço de Catálogo de Endereços no banco de dados.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>Objetivo

O ABSConfig oferece uma maneira rápida e fácil de personalizar o serviço de catálogo de endereços do Lync Server 2013.

</div>

<div>

## <a name="requirements"></a>Requisitos

<div>

## <a name="computer"></a>Computador

O ABSConfig pode ser executado apenas em um computador associado a um domínio que tenha o Lync Server 2013 instalado. No caso do Lync Server 2013, Enterprise Edition, essa ferramenta pode ser executada em qualquer servidor front-end que tenha o serviço de catálogo de endereços habilitado durante a instalação.

</div>

<div>

## <a name="network"></a>Rede

O computador deve poder se conectar ao pool de front-ends e ao banco de dados back-end.

</div>

<div>

## <a name="software"></a>Software

Os seguintes componentes de software deverão ser instalados antes de executar a ferramenta ABSConfig:

  - Microsoft Lync Server 2013

</div>

<div>

## <a name="users"></a>Usuários

Administradores que têm as permissões necessárias para atualizar a implantação do Lync Server 2013.

</div>

</div>

<div>

## <a name="examples"></a>Exemplos

A ABSConfig pode ser iniciada digitando **ABSConfig.exe** em um prompt de comando. Abaixo é mostrada a interface do usuário da ferramenta ABSConfig.

![A ferramenta ABSConfig. exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "A ferramenta ABSConfig. exe.")

</div>

<div>

## <a name="summary"></a>Resumo

A ferramenta ABSConfig fornece aos administradores uma ferramenta rápida e fácil de usar para personalizar o serviço de catálogo de endereços do Lync Server 2013.

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>Monitor de Serviços da Política de Largura de Banda

A ferramenta Monitor de Serviços da Política de Largura de Banda permite que os administradores visualizem uma lista contendo:

1.  Todos os serviços de política de largura de banda do Lync Server 2013 configurados (autenticação e núcleo) na topologia

2.  As conexões de cada um dos serviços com outros serviços da Política de Largura de Banda e servidores de borda.

3.  Todos os links configurados contidos no documento de configuração de rede e uso de largura de banda em tempo real, conforme relatado por cada um dos serviços da Política de Largura de Banda.

<div>

## <a name="description"></a>Descrição

A ferramenta Monitor de Serviços da Política de Largura de Banda é implementada como um aplicativo baseado na GUI. Os administradores iniciam a ferramenta executando PDPMonUI.exe.

Quando a ferramenta é iniciada, ela tenta descobrir a lista dos serviços da Política de Largura de Banda na topologia. Após a conclusão da atualização inicial, o painel à esquerda da janela é populada com uma lista de serviços agrupados pelos clusters aos quais pertencem.

Quando os administradores selecionam determinado Serviço da Política de Largura de Banda, o painel à direita exibe as informações sobre o serviço. O painel também tem duas guias principais que exibem informações.

<div>

## <a name="machine-info-tab"></a>Guia Informações do Computador

A guia **Informações do Computador** mostra os detalhes do Serviço da Política de Largura de Banda selecionado, bem como a lista e o estado de todas as conexões realizadas pelo Serviço da Política de Largura de Banda selecionado com outros serviços.

</div>

<div>

## <a name="topology-info-tab"></a>Guia Informações da Topologia

A guia **Informações da Topologia** mostra uma lista de todos os links definidos nas configurações de rede. É exibida a capacidade de largura de banda de vídeo e áudio de cada link. Além disso, a largura de banda utilizada atualmente também é exibida, em Kbps e em um percentual da capacidade. A ferramenta usa codificação por cores para realçar os links cuja utilização esteja próxima do limite de capacidade, permitindo que os administradores isolem rapidamente esses links.

<div>


> [!NOTE]  
>  Se houver uma falha no Monitor de Serviços da Política de Largura de Banda ao se conectar a qualquer um dos serviços da Política de Largura de Banda configurados, as informações nas guias <STRONG>Informações do Computador</STRONG> e <STRONG>Informações da Topologia</STRONG> não serão populadas. No entanto, é possível que a ferramenta se conecte inicialmente, mas depois perca a conexão com o serviço. Nesses casos, os administradores poderão ver informações desatualizadas. Há um carimbo de data/hora <STRONG>Última Atualização</STRONG> em cada uma das guias que permite aos administradores ver quando os dados foram atualizados pela última vez para um determinado Serviço da Política de Largura de Banda.



</div>

</div>

</div>

<div>

## <a name="output"></a>Resultado

Não há nenhum resultado na linha de comando; o resultado do programa está contido dentro da GUI (interface gráfica do usuário) principal.

</div>

<div>

## <a name="purpose"></a>Objetivo

O objetivo da ferramenta Monitor de Serviços da Política de Largura de Banda é proporcionar aos administradores visibilidade do estado de cada um dos serviços da Política de Largura de Banda definidos na topologia. Além disso, os administradores podem ver o uso da largura de banda em tempo real de todos os links definidos no documento de configuração da rede.

</div>

<div>

## <a name="requirements"></a>Requisitos

A ferramenta de monitoração do serviço de política de largura de banda precisa ser executada em um computador que faça parte da topologia do Lync Server.

</div>

<div>

## <a name="summary"></a>Resumo

A ferramenta Monitor de Serviços da Política de Largura de Banda pode ser um recurso valioso para os administradores, pois com ela é possível inspecionar na topologia o estado de todos os serviços da Política de Largura de Banda e, o mais importante, obter a utilização da largura de banda em tempo real dos links definidos nas configurações da rede.

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>Analisador de Utilização da Largura de Banda

O Analisador de Utilização da Largura de Banda é uma ferramenta que cria relatórios sobre diversas exibições do consumo de largura de banda pelos pontos de extremidade de UC nos links WAN da rede corporativa. Esses relatórios podem ser usados para entender o padrão de consumo de largura de banda atual e auxiliar no planejamento de capacidade de largura de banda.

<div>

## <a name="description"></a>Descrição

O Analisador de Utilização da Largura de Banda é implementado como um aplicativo baseado na GUI. Essa ferramenta gera relatórios específicos para utilização de áudio na rede e ajuda no planejamento da capacidade. Também itera na capacidade de largura de banda atribuída a diversos links.

</div>

<div>

## <a name="output"></a>Resultado

O Analisador de Utilização da Largura de Banda fornece plotagens gráficas da utilização e da capacidade de largura da banda de áudio de todos os links WAN configurados no sistema.

</div>

<div>

## <a name="purpose"></a>Objetivo

Em qualquer implantação de vídeo e voz, é fundamental monitorar e entender a tendência da utilização da largura de banda do tráfego de mídia na rede corporativa. A ferramenta Analisador de Utilização da Largura de Banda permite ao administrador realizar justamente isso. Essa ferramenta faz o seguinte:

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

<div>

## <a name="applications"></a>Aplicativos

O Analisador de Utilização da Largura de Banda tem os dois aplicativos (ferramentas) abaixo:

  - **WanLinkLogCollector. exe**   esta ferramenta permite que o usuário insira as informações necessárias.

  - **BandwidthUtilizationAnalyzer. xlsm**  um relatório de software de planilha do Microsoft Excel é iniciado automaticamente por WanLinkLogCollector. exe. Este aplicativo permite ao usuário aplicar filtros ao relatório, como será mostrado posteriormente neste artigo.

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fases de uso do Analisador de Utilização da Largura de Banda

Há duas fases ao usar o Analisador de Utilização da Largura de Banda:

  - Coletar logs, o que é realizado ao usar o WanLinkLogCollector.exe.

  - Personalizar relatórios, o que é realizado ao usar o BandwidthUtilizationAnalyzer.xlsm.

<div>


> [!IMPORTANT]  
> Recomendamos que o BandwidthUtilizationAnalyzer.xlsm não seja iniciado manualmente pelos usuários finais.



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>Iniciando o Analisador de Utilização da Largura de Banda

Inicie o WanLinkLogCollector.exe no prompt de comando ou no Windows Explorer.

**Usando o WanLinkLogCollector.exe**

Há três etapas para usar o WanLinkLogCollector.exe:

1.  **Registrar a linha**   do tempo forneça a linha do tempo para a qual o relatório precisa ser gerado

2.  **Especificar os diretórios**   de arquivos fornecem informações de localização do arquivo

3.  **Coletar os logs e iniciar o visualizador**  de relatórios execute o comando para gerar o relatório

<div>

## <a name="step-1---log-the-timeline"></a>Etapa 1 – Registrar a linha do tempo

O registro da linha do tempo permite que o usuário da ferramenta especifique o seguinte, conforme mostra a figura abaixo: 

1.  **Data de início** Trata-se da data de início da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 1º de agosto de 2010.

2.  **Data de término** Trata-se da data de término da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 30 de setembro de 2010.
    
    ![Datas de início e término na utilização da largura de banda A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Datas de início e término na utilização da largura de banda A")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>Etapa 2 – Especificar os diretórios do arquivo

Os seguintes diretórios de arquivo devem ser especificados pelo usuário, como a seguir:

  - **Local dos arquivos de log do servidor** O local da pasta onde os logs do servidor de política de largura de banda são armazenados. Isso geralmente é na \<\>\\\<opção de todos os\>\\seus\\AppServerFiles de PDP do Fe.

  - **Local de armazenamento de arquivo temporário** O local do arquivo temporário onde os arquivos intermediários são armazenados enquanto o relatório está sendo gerado.

![Diretórios de arquivos no anal de utilização da largura de banda](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Diretórios de arquivos no anal de utilização da largura de banda")

<div>


> [!NOTE]  
> Forneça ao usuário da ferramenta acesso suficiente aos arquivos de logs do servidor e à pasta de repositório de arquivos temporários.



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Etapa 3 – Coletar os logs e iniciar o visualizador de relatórios

Para coletar os logs e iniciar o visualizador de relatórios, clique em **Executar**, como mostrado abaixo. Esta etapa coleta os dados necessários.

![Coletando dados na Analy de utilização da largura de banda](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Coletando dados na Analy de utilização da largura de banda")

Se a validação da entrada for bem-sucedida, a mensagem abaixo será exibida.

![Registra a notificação coletada no utilitário de largura de banda](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Registra a notificação coletada no utilitário de largura de banda")

Clique em **OK**. BandwidthUtilizationAnalyzer.xlsm será iniciado automaticamente. Siga as instrução na caixa de mensagens. Para obter mais detalhes, consulte **Uso do BandwidthUtilizationAnalyzer.xlsm ** na próxima seção.

</div>

<div>


**Uso do BandwidthUtilizationAnalyzer.xlsm**

1.  Se o BandwidthUtilizationAnalyzer.xlsm tiver sido iniciado automaticamente, clique em **Atualizar**, como a seguir.
    
    ![BandwidthUtilizationAnalyzer. xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")

2.  Quando uma pasta de arquivos for aberta, selecione consolidated.csv na localização especificada na caixa de mensagens, como a seguir. Ele também mostra o local como **C:\\Temp**.
    
    ![Abrir uma pasta no BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Abrir uma pasta no BandwidthUtilizationAnalyzer.")

3.  Clique em **Importar**.

4.  A plotagem gráfica é gerada automaticamente. Ela será disponibilizada assim que o ponteiro de trabalho em segundo plano desaparecer.
    
    ![Aplicação de filtros no modo de exibição relatório.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicação de filtros no modo de exibição relatório.")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>Aplicando filtros ao visualizador de relatórios

Os filtros que podem ser aplicados ao visualizador de relatórios, conforme mostrado abaixo, são descritos da seguinte forma:

![Aplicação de filtros no modo de exibição relatório.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicação de filtros no modo de exibição relatório.")

1.  **Nome** Filtrar por links WAN (o filtro se situa no lado direito do gráfico). O prefixo denota os tipos de links a seguir; consulte a caixa (azul) vertical:
    
      - **S Site ** O link WAN de um site da rede a uma região da rede
    
      - **IS Entre sites** O link WAN entre dois sites da rede
    
      - **R Inter-regional** O link WAN entre duas regiões da rede

2.  **Limite excedido** Filtrar por links WAN cuja utilização de largura de banda seja superior à capacidade da largura de banda

3.  **Níveis críticos** Filtrar por links WAN cuja utilização da largura de banda tenha alcançado 90% ou mais da capacidade da largura de banda

4.  **Subutilizado** Filtrar por links WAN cuja utilização da largura de banda seja inferior a 25% da capacidade da largura de banda

5.  **Tipo de link** Filtrar pelos seguintes tipos de links WAN:
    
      - 
            Tipo **Site da rede**
    
      - 
            Tipo **Entre sites**
    
      - 
            Tipo **Link inter-regional**

6.  **Região** Filtrar pela região da rede

As imagens abaixo mostram os filtros descritos anteriormente.

Filtrar por **Nome**. Selecione a lista de links que precisam ser exibidos no gráfico.

![Filtragem por nome no BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtragem por nome no BandwidthUtilizationAnalyzer.")

Filtrar por **Limite excedido**. Selecione **True** para impor o filtro.

![A filtragem excedeu o limite.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "A filtragem excedeu o limite.")

Filtrar por **Níveis críticos**. Selecione **True** para impor o filtro.

![Filtragem por níveis críticos.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtragem por níveis críticos.")

Filtrar por **Subutilizado**. Selecione **True** para impor o filtro.

![Filtragem por subutilizado.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtragem por subutilizado.")

Filtrar por **Tipo de Link**. Selecione um ou mais tipos que precisam ser exibidos.

![Filtragem por tipo de link.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtragem por tipo de link.")

Filtrar por **Região**. Selecione uma lista de regiões cujos links precisam ser exibidos.

![Filtragem por região.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtragem por região.")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>Requisitos

  - .NET Framework 3.5

  - Microsoft Excel 2010 ou Excel 2007

</div>

<div>

## <a name="summary"></a>Resumo

O Analisador de Utilização da Largura de Banda é usado para plotar a utilização da largura de banda de áudio do tráfego de UC na rede. Esta ferramenta pode ser usada também para relatar a utilização da largura de banda de vídeo na rede.

</div>

</div>

<div>

## <a name="call-parkometer"></a>Parquímetro de Chamada

O Parquímetro de Chamada é um aplicativo de linha de comando que proporciona fácil acesso ao banco de dados da Órbita do Call Park.

<div>

## <a name="description"></a>Descrição

O Parquímetro de Chamada é uma ferramenta que rastreia as chamadas estacionadas atualmente. Ele também coleta estatísticas sobre as órbitas e o uso do CPS (Servidor de Estacionamento de Chamada). Essa ferramenta de linha de comando fornece acesso de leitura e gravação ao banco de dados do SQL Server do CPS órbita a partir de um computador local ou remotamente conectado.

Todas as opções são mutuamente exclusivas. A sintaxe da linha de comando é a seguinte:

  - 
            Parâmetro **–o** – lista todos os intervalos de órbitas configurados para este pool.

  - 
            Parâmetro **–n** – lista todas as órbitas usadas atualmente neste pool. As informações são exibidas da seguinte forma:
    
      - URI (Uniform Resource Identifier) do SIP da chamada estacionada e do estacionador.
    
      - Nome do host do CPS onde a chamada está estacionada.
    
      - Carimbo de data/hora de quando a chamada foi estacionada.

  - 
            Parâmetro **–f** – lista o número de órbitas atualmente livres no pool.

  - **– o \<parâmetro\> r n** — lista \<as\> chamadas n últimas chamadas estacionadas. As informações são exibidas da seguinte forma:
    
      - URI do SIP da chamada estacionada.
    
      - URI do SIP do estacionador da chamada.
    
      - Nome do host do CPS onde a chamada foi estacionada.
    
      - Carimbo de data/hora de quando a chamada foi recuperada ou ignorada.

  - **-t\<n\> ** parâmetros-testes reservando uma órbita no banco de dados para mostrar a aleatoriedade dos números de órbita atribuídos.

</div>

<div>

## <a name="output"></a>Resultado

Dependendo dos parâmetros de entrada especificados em um prompt de comando, o Parquímetro de Chamada exibirá o seguinte resultado:

  - Todos os intervalos de órbita configurados para este pool

  - Chamadas estacionadas atualmente

  - Número de órbitas livres (disponíveis)

  - Chamadas estacionadas recentemente

  - Órbitas reservadas para testes uniformes e valores de órbita aleatórios

</div>

<div>

## <a name="purpose"></a>Objetivo

O objetivo da ferramenta CPS é fornecer acesso de linha de comando ao banco de dados do CPS. O administrador pode visualizar o CPS usado e determinar o números de órbitas atribuídas a um pool.

</div>

<div>

## <a name="requirements"></a>Requisitos

Não haverá nenhum requisito se esta ferramenta for executada no mesmo computador que estiver executando o CPS. Se essa ferramenta for executada em um computador remoto, o banco de dados do SQL Server usado pelo Lync Server 2013 deve ser configurado para permitir acesso remoto. Chame Parkometer deve ser configurado com uma cadeia de conexão de banco de dados SQL Server para se conectar ao SQL Server do pool. Esta cadeia de conexão de banco de dados do SQL Server é definida no arquivo de configuração **parkometer. exe. config**. Ele deve ser colocado no mesmo diretório em que o parkometer. exe está localizado. O arquivo XML a seguir é um exemplo de um parkometer. exe. config. Os parâmetros que devem ser configurados são o nome de usuário (por\\exemplo, administrador de mydomain), senha (por exemplo, mypassword) e nome do host (por exemplo, meuservidor).

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

Intervalos de órbitas implantados: o parâmetro –o lista todos os intervalos de órbita configurados para este pool, como a seguir:

![As faixas órbitas no Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "As faixas órbitas no Call Parkometer.")

Chamadas estacionadas atualmente: o parâmetro –n lista todas as órbitas usadas atualmente neste pool, como a seguir:

![Chamadas estacionadas no momento no Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Chamadas estacionadas no momento no Call Parkometer.")

Número de órbitas livres: o parâmetro –f lista o número de órbitas livres atualmente neste pool, como a seguir:

![Órbitas grátis no Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Órbitas grátis no Call Parkometer.")

Chamadas estacionadas recentemente: o parâmetro \<–\> r n lista \<as\> n últimas chamadas estacionadas conforme mostrado

![Chamadas estacionadas recentemente no Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Chamadas estacionadas recentemente no Call Parkometer.")

Testar reserva de órbita: os testes \<de\> parâmetro – t n reservando uma órbita no banco de dados conforme mostrado

![Teste as reservas em órbita na Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Teste as reservas em órbita na Call Parkometer.")

</div>

<div>

## <a name="summary"></a>Resumo

O Parquímetro de Chamada é uma ferramenta de linha de comando que fornece informações detalhadas sobre o Servidor de Estacionamento de Chamada.

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

A ferramenta CleanupStorageServiceData Resource Kit permite excluir dados órfãos do banco de dados usado pelo serviço de armazenamento do Lync Server (LYSS). Uma função do serviço de armazenamento é armazenar em buffer a comunicação entre o Lync Server e vários pontos de extremidade de armazenamento de dados back-end, como o SQL Server e o Exchange.

<div>

## <a name="description"></a>Descrição

Para dar suporte à alta disponibilidade, o LYSS aceita e salva cópias dos dados em vários servidores front-end no pool temporariamente, e remove esses dados após serem entregues ao seu local de armazenamento final de longo prazo. Há situações anormais que podem ocorrer durante a operação normal, quando um servidor pode falhar ou enfrentar um problema de processamento, e alguns dados podem não ser limpos corretamente. Esses dados são inofensivos, mas não consomem recursos de processamento limitados. Grande parte da manutenção de dados necessária normal é automatizada, mas essa ferramenta permite que a identificação e a remoção sejam excluídas desses dados órfãos quando a remoção automatizada não é possível. O uso dessa ferramenta é indicado quando um alerta do Gerenciador de operações do sistema de monitoramento de integridade (SCOM) é gerado, solicitando que o administrador remova os dados desnecessários dos bancos de dados do LYSS locais do pool. Haverá um evento correspondente no log de eventos do front-end que disparou o alerta. Os detalhes do evento contêm informações sobre a quantidade de dados órfãos contidos no front-end e são acionados quando esses dados excedem certos limites predefinidos

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale as ferramentas do Lync Server 2013, Resource Kit. A ferramenta é executada em máquinas Unidas a domínios nas quais o Shell de gerenciamento do Lync Server e do Lync Server 2013 está instalado. A ferramenta usa um cmdlet do Shell de gerenciamento para identificar todos os servidores de front-end do pool. Em segundo lugar, a ferramenta deve ser executada em um computador no pool em que o banco de dados do **RtcLocal** está instalado. Este banco de dados é usado pela ferramenta CleanupStorageServiceData para obter os detalhes de conexão necessários para se comunicar com o serviço de roteamento do Lync Server. por fim, a conta ou a credencial que invocar a ferramenta deve ter permissão de leitura/gravação para o compartilhamento de arquivos no qual deseja gravar o log de saída. Além disso, essa ferramenta depende do pool estar em um estado estável. Em essência, isso significa que cada servidor front-end deve estar em funcionamento, a instância LYNCLOCAL do SQL Server e o banco de dados do LYSS devem estar conectados, e cada grupo de roteamento deve ter um conjunto completo de 1 servidor front-end primário e dois front-ends secundários ervers.

</div>

<div>

## <a name="examples"></a>Exemplos

C:\\arquivos\\de programas Microsoft Lync Server\\2013\\reskit\> StorageService ImportStorageServiceData. exe

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

DBAnalyze é uma ferramenta de linha de comando que ajuda os administradores a reunir relatórios de análise sobre os bancos de dados do Lync Server 2013. O DBAnalyze tem os seguintes modos: diagnóstico, dados do usuário, conferência, MCUs e fragmentação de disco:

  - **O modo**   de diagnóstico cria um relatório que inclui informações sobre tabelas (número de registros, fragmentação, tamanho dos dados e tamanho de índice), dados e tamanhos de arquivo de log, o último tempo de backup, a distribuição de contatos entre servidores que executam o Microsoft Office Communications Server, o número médio de permissões, contatos, contêineres, assinaturas, publicações, pontos de extremidade por usuário, todos os usuários incorretos, programados para o conferências, conferências ativas e a versão do banco de dados.
    
    <div>
    

    > [!NOTE]  
    > A execução do modo de diagnóstico pode afetar o desempenho do servidor.

    
    </div>

  - O **modo**  de dados do usuário relata o contato, o contêiner, a assinatura, a publicação, a permissão e os dados do grupo de contatos para um usuário específico ou para usuários que tenham esse usuário em suas listas de contatos e permissões. Este modo também relata dados resumidos de conferências que um usuário organizou ou para as quais foi convidado.

  - **O modo**   de conferência relata dados detalhados para uma conferência específica, incluindo todos os detalhes do tempo de agendamento da conferência, a lista de convidados, a lista de tipos de mídia permitidos para a conferência, active MCUs (unidades de controle multiponto), a lista de participantes ativa e o estado de sinalização de cada participante.

  - **Decodificar a ID**  de reunião decodifica uma ID de reunião PSTN (rede telefônica pública comutada) especificada pela opção **/pstnid** , mas não se conecta ao back-end para obter informações detalhadas.

  - **Resolver a conferência**   decodifica uma ID de reunião PSTN especificada pela opção **/pstnid** e exibe informações sobre a conferência indicada pela ID.

  - **O modo**  MCUs relata a identificação, o tipo de mídia, a URL, o status de Heartbeat, a carga de conferência e a carga de participantes para cada MCU do pool.

  - **O modo**  de fragmentação de disco exibe o status de fragmentação de todos os discos.

Esta ferramenta pode ser usada para diagnosticar diversos problemas ou para ajudar os administradores no planejamento da capacidade. Por exemplo, se a maioria dos usuários hospedados no servidor A escolher como contatos usuários hospedados no servidor B, o administrador poderá mover os usuários do servidor A para o servidor B para reduzir o tráfego entre servidores.

</div>

<div>

## <a name="output"></a>Resultado

Esta ferramenta emite relatórios predefinidos sobre o banco de dados do Lync Server 2013. **Caminho:** % ProgramFiles\\% Microsoft Lync Server\\2013 reskit

</div>

<div>

## <a name="purpose"></a>Objetivo

Para instalar o Dbanalyze. exe, copie-o para uma pasta local e execute a ferramenta. Para usar a ferramenta, execute o seguinte comando a partir da linha de comando.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` As descrições das opções de linha de comando são mostradas abaixo.

![Opções da linha de comando para Dbanalyze. exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Opções da linha de comando para Dbanalyze. exe.")

</div>

<div>

## <a name="requirements"></a>Requisitos

**Computador** O DBAnalyze pode ser executado apenas em um computador associado a um domínio que tenha o Lync Server 2013 instalado.

**Rede** O computador deve poder se conectar ao banco de dados back-end.

**Software** Os componentes do software do Lync Server 2013 devem ser instalados antes de executar o DBAnalyze.

**Usuários** do A tabela a seguir mostra os administradores que têm as permissões necessárias para acessar bancos de dados do Lync Server 2013.

![Tabela de permissões para Dbanalyze. exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tabela de permissões para Dbanalyze. exe.")

<div>


> [!NOTE]  
> Uma conta de administrador local é necessária para o modo <STRONG>/report:disk</STRONG>.



</div>

</div>

<div>

## <a name="examples"></a>Exemplos

Veja abaixo exemplos de comandos válidos do Dbanalyze.exe:

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>Resumo

O DBAnalyzer fornece aos administradores um rápido e fácil de analisar bancos de dados do Lync Server 2013.

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

A ferramenta ImportStorageServiceData do kit de recursos permite reimportar os dados da fila e do ponto de extremidade que foram exportados do Serviço de Armazenamento (LYSS) para o Serviço de Armazenamento.

<div>

## <a name="description"></a>Descrição

A exportação dos dados do Serviço de Armazenamento pode ter sido automática (periodicamente) com base no status do item da fila ou no tamanho do banco de dados. Ela pode ter ocorrido devido à invocação manual do cmdlet de failover do pool ou do cmdlet StorageServiceFullFlush (invocado pelo cmdlet de failover do pool). Lembre-se de que os dados não devem ser importados novamente se qualquer um dos tamanhos de banco de dados do serviço de armazenamento (LYSS) no front-ends estiver acima do nível normal, porque isso provavelmente apenas fará com que mais dados sejam exportados. Além disso, quaisquer problemas que possam ter contribuído com erros que fizeram com que a fila do serviço de armazenamento cresça devem primeiro ser resolvidos (por exemplo, erros de ponto de extremidade do Exchange, problemas de rede ou outros problemas).

**Cenário 1:** durante o failover do pool, os arquivos poderão ser liberados do serviço de armazenamento de cada front-end. Após a conclusão do failover, a ferramenta deverá ser executada para reimportar os dados.

**Cenário 2:** os dados estão sendo exportados de maneira automática diariamente ou em resposta ao banco de dados de Serviço de Armazenamento ter excedido determinados limites de tamanho (por exemplo, 60%, 80%, 90%, capacidade total). Esses dados exportados automaticamente devem ser reimportados regularmente pelo administrador. Na situação acima, se o pacote do SCOM que está sendo monitorado não for implantado, há eventos para o serviço de armazenamento do Lync Server relacionados a dados que estão sendo liberados do serviço de armazenamento. As IDs de evento são: 32075 (operação de exportação completa iniciada), 32076 (exportação completa concluída), 32082 (exportação de nível de manutenção iniciada), 32083 (exportação de nível de manutenção concluída), 32089 (exportação ocorrida devido ao preenchimento do banco de dados). Observe que essas IDs de evento correspondem à versão do RTM. Quando um administrador vê esses eventos, isso significa que há arquivos que foram liberados. Esses dados devem ser importados rotineiramente usando essa ferramenta, por exemplo, uma vez por semana.

Para o lançamento do serviço online, se o pacote do SCOM Pack para Lync Server for implantado, há novos alertas que podem ser gerados, que pede ao administrador para reimportar os dados liberados de volta para o serviço de armazenamento. Haverá um evento correspondente no log de eventos no servidor front-end que disparou o alerta. O evento dará uma descrição do caminho pai sob o qual se encontram os arquivos de dados exportados, bem como a quantidade de arquivos existentes que cumpre os critérios do alerta. O critério de alerta é de que há X ou mais arquivos sob o caminho pai específico que tem pelo menos Y dias (em que X e Y são predefinidos dentro do StorageService, mas podem ser substituídos, alterando o arquivo APPCONFIG). Dois exemplos de eventos que podem disparar o alerta de integridade são mostrados abaixo, com a diferença sendo seu respectivo caminho pai. (por exemplo, c\\:\\ProgramData\\Microsoft Lync\\Server StorageService). O administrador executará essa ferramenta do reskit.

Essa ferramenta aumentará a carga de CPU e de E/S no front-end em que estiver sendo executada e também em outros front-ends se os dados não pertencerem ao front-end no qual a ferramenta estiver sendo executada. Recomendamos executar essa ferramenta quando os front-ends não estiverem sob uma carga de E/S e CPU pesada, por exemplo, fora dos horários de pico. Em segundo lugar, essa ferramenta leva de 2 a 3 minutos para importar um arquivo de dados. Lembre-se disso ao estimar por quanto tempo a ferramenta estará em execução. O arquivo de log detalhado gerado pela ferramenta, por padrão, será exibido no repositório de arquivos. Exclua-o se não houver nenhum erro relatado, pois o arquivo de log pode ter muitos megabytes.

![Exemplos de eventos do log de eventos do servidor de armazenamento.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Exemplos de eventos do log de eventos do servidor de armazenamento.")

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale as ferramentas do Lync Server 2013, Resource Kit. A ferramenta é executada em máquinas Unidas a domínios nas quais o Lync Server e o Shell de gerenciamento do Lync Server são instalados. A ferramenta usa um cmdlet do Shell de gerenciamento para identificar todos os servidores de front-end do pool. Em segundo lugar, a ferramenta deve ser executada em um computador no pool em que o banco de dados do **RtcLocal** está instalado. Esse banco de dados é usado pela ferramenta para recuperar a localização do compartilhamento de arquivo WEBSERVICE para o pool. Além disso, antes de usar a ferramenta, cada servidor front-end deve primeiro habilitar a comunicação remota do Windows PowerShell usando **Enable-PSRemoting** em cada servidor front-end, bem como a máquina na qual a ferramenta é executada. Caso contrário, os comandos remotos do Windows PowerShell dessa ferramenta falharão. A comunicação remota do Windows PowerShell pode ser desativada em todos os servidores de front-end do pool após o término. Por fim, a conta ou a credencial que invocar a ferramenta deve ter permissão de leitura/gravação para o compartilhamento de arquivo WebService para o pool em que ele está executando essa ferramenta. Caso contrário, a ferramenta irá falhar com erros de permissão de e/s.

<div>


> [!NOTE]  
> No Windows Server 2012, a comunicação remota do Windows PowerShell está habilitada por padrão, mas não no sistema operacional Windows Server 2008.



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

A ferramenta LCSSync ajuda a implantar o software de comunicação do Lync Server 2013 em um ambiente de várias florestas. Essa ferramenta é usada para sincronizar usuários e grupos de florestas de usuários diferentes como um objeto de contato dos serviços de domínio Active Directory para uma floresta central na qual o Lync Server 2013 está instalado.

<div>

## <a name="description"></a>Descrição

O LCSSync usa os objetos de contato sincronizados dos serviços de domínio Active Directory na floresta central para permitir que os usuários do Lync Server. Para fornecer logon único, a conta de usuário principal deve ser mapeada para o objeto de contato dos serviços de domínio Active Directory na floresta central do Lync Server 2013. Essa ferramenta ajuda a realizar esse mapeamento. Ela também fornece modelos para a criação de Agentes de Gerenciamento no Microsoft Identity Integration Server.

</div>

<div>

## <a name="summary"></a>Resumo

A ferramenta LCSSync ajuda a implantar o Lync Server em um ambiente de várias florestas.

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

A ferramenta LookupUserConsole exibe informações de roteamento internas do Lync Server sobre usuários específicos. Essas informações poderão ser úteis para o suporte pessoal da Microsoft no diagnóstico de problemas de implantação e roteamento.

<div>

## <a name="description"></a>Descrição

Executar o LookupUserConsole. exe abrirá um prompt de comando que aceita endereços SIP e tenta exibir informações internas de roteamento do Lync Server relacionadas a eles. Digite **exit** para sair da ferramenta LookupUserConsole.

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale as ferramentas do Lync Server 2013, Resource Kit. A ferramenta é executada em máquinas Unidas pelo domínio onde o Lync Server está instalado

</div>

<div>

## <a name="examples"></a>Exemplos

C:\\arquivos\\de programas Microsoft Lync Server\\2013 reskit\>LookupUserConsole. exe

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

A ferramenta MSTurnPing permite que um administrador do software de comunicação do Microsoft Lync Server 2013 Verifique o status dos servidores que estão executando a borda de áudio/vídeo e os serviços de autenticação de áudio/vídeo, bem como os servidores que estão executando os serviços de política de largura de banda na topologia.

<div>

## <a name="description"></a>Descrição

A ferramenta MSTurnPing permite que um administrador do software de comunicação do Lync Server 2013 Verifique o status dos servidores que executam a borda de áudio/vídeo e os serviços de autenticação de áudio/vídeo, bem como os servidores que estão executando os serviços de política de largura de banda na topologia.

A ferramenta permite ao administrador realizar os seguintes testes:

1.  Teste do Servidor de Borda A/V: a ferramenta realiza testes em todos os Servidores de Borda A/V na topologia fazendo o seguinte:
    
      - Verificar se o serviço de autenticação de áudio/vídeo do Lync Server foi iniciado e pode emitir credenciais adequadas.
    
      - Verificando se o serviço de borda de áudio/vídeo do Lync Server foi iniciado e pode alocar os recursos na borda externa com êxito.

2.  Teste do Serviço da Política de Largura de Banda: a ferramenta realiza testes em todos os servidores que estejam executando os Serviços da Política de Largura de Banda na topologia fazendo o seguinte:
    
      - Verificar se o serviço de política de largura de banda (autenticação) do Lync Server foi iniciado e pode emitir credenciais adequadas.
    
      - Verificando se o serviço de política de largura de banda do Lync Server (básico) foi iniciado e pode executar a verificação de largura de banda com êxito.

Essa ferramenta deve ser executada em um computador que faça parte da topologia e tenha o repositório local instalado. 

</div>

<div>

## <a name="output"></a>Resultado

Essa ferramenta gera os resultados de cada uma das operações.

  - Quando o teste **AudioVideoEdgeServer ** é realizado, a ferramenta gera o seguinte:
    
      - Os resultados do teste dos computadores que fornecem o serviço de autenticação de áudio/vídeo do Lync Server na topologia
    
      - Os resultados do teste dos computadores que fornecem o serviço de borda de áudio/vídeo do Lync Server na topologia

  - Quando o teste **BandwidthPolicyServer** é realizado, a ferramenta gera o seguinte:
    
      - Os resultados do teste dos computadores que fornecem o serviço de política de largura de banda (autenticação) do Lync Server na topologia
    
      - Os resultados do teste dos computadores que fornecem o serviço de política de largura de banda do Lync Server (básico) na topologia

</div>

<div>

## <a name="requirements"></a>Requisitos

  - Essa ferramenta deve ser executada em um computador que faça parte da topologia e tenha o repositório local instalado.

  - A ferramenta deve ser executada por um administrador que tenha acesso ao repositório local.

</div>

<div>

## <a name="examples"></a>Exemplos

Veja a seguir um exemplo de entrada de dados da ferramenta.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para os administradores do Lync Server 2013 que desejam verificar o status dos servidores que estão executando os serviços de política de áudio/vídeo e largura de banda.

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>Visualizador da Configuração de Rede

O Visualizador de configuração de rede pode ser usado pelos administradores do software de comunicações do Microsoft Lync Server 2013 para exibir a topologia de rede do controle de admissão de chamadas (CAC) para uma empresa que é fornecida para permitir sessões de comunicação em tempo real, como voz ou chamadas com vídeo com base na capacidade de largura de banda especificada. Os administradores do Lync Server 2013 definem políticas do CAC, que são impostas pelos serviços de política de largura de banda que são instalados com o Lync Server 2013.

<div>

## <a name="description"></a>Descrição

O Visualizador da Configuração de Rede (NetworkConfigurationViewer.exe) permite aos administradores executar as seguintes tarefas:

  - Carregar e exibir a topologia de rede do CAC a partir de uma implantação do Lync Server 2013 em um formato gráfico.

  - Carregar e exibir a topologia de rede do CAC de um arquivo de log do Servidor da Política de Largura de Banda em um formato gráfico.

  - Salvar e armazenar no disco a topologia de rede do CAC no formato XML.

  - Salvar e armazenar o diagrama da topologia de rede do CAC no formato JPG ou BMP.

  - Exibir os dados de configuração da topologia de rede do CAC.

  - Exibir a topologia de rede do CAC em modo de exibição de árvore.

  - Definir conectores personalizados para os links da topologia de rede do CAC (por exemplo, links de site para região, região para região e site para site).

  - Exibir as informações do site de topologia de rede do CAC, informações da região e links de rede e políticas de largura de banda provisionadas.

</div>

<div>

## <a name="purpose"></a>Objetivo

Exibir os links de topologia de rede do CAC da empresa em uma interface gráfica.

</div>

<div>

## <a name="examples"></a>Exemplos

**Carregar e exibir a topologia de rede do CAC a partir de uma implantação do Lync Server 2013 em um formato gráfico:** Os administradores do Lync Server 2013 podem carregar e exibir a configuração de topologia de rede do CAC em qualquer computador com o Lync Server 2013 usando a opção **baixar a configuração de rede** , conforme mostrado na figura abaixo. A ferramenta não fará o download ou exibirá essa configuração quando implantada em um computador que não tenha conectividade com o repositório de configuração do Lync.

![Baixando a configuração de rede.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Baixando a configuração de rede.")

**Carregar e exibir a topologia de rede do CAC de um arquivo de log do servidor de políticas de largura de banda em um formato gráfico:** Servidores de política de largura de banda do Lync Server 2013 salve a topologia de rede do CAC como parte do mecanismo de log no local de compartilhamento de arquivos do Lync Server 2013. Os administradores do Lync Server podem exibir esse arquivo em um formato gráfico usando a opção **abrir a configuração de rede** , como mostrado a seguir.

![Abrir um arquivo de log do servidor de políticas de largura de banda.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Abrir um arquivo de log do servidor de políticas de largura de banda.")

Salvar e armazenar a topologia de rede do CAC em um formato XML no disco: os administradores do Lync Server 2013 podem salvar o arquivo de configuração de topologia de rede do CAC em um formato XML usando a opção **salvar uma cópia da configuração de rede** , conforme mostrado a seguir. O arquivo de configuração salvo pode ser usado offline para fins de exibição gráfica.

![Salvando a configuração de rede como um arquivo XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Salvando a configuração de rede como um arquivo XML.")

Salvar e armazenar o diagrama de topologia de rede do CAC no formato JPG ou BMP: os administradores do Lync Server 2013 podem salvar a configuração de topologia de rede do CAC em um formato gráfico (formatos de arquivo JPG e BMP) usando a opção **salvar diagrama de configuração de rede como imagem** , conforme mostrado a seguir.

![Salvando a configuração de rede como uma imagem.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Salvando a configuração de rede como uma imagem.")

**Exibir dados de configuração de topologia de rede do CAC:** Os administradores do Lync Server 2013 podem exibir dados de configuração de rede relacionados, como regiões de rede, sites de rede, perfis de largura de banda e endereços IP de sub-rede de sites em um formato de texto usando a opção Exibir dados de configuração de rede, conforme mostrado a seguir.

![Exibir dados de configuração de rede.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Exibir dados de configuração de rede.")

**Exiba a topologia de rede do CAC em um estilo de exibição de árvore:** Os administradores do Lync Server 2013 podem exibir dados de configuração de rede relacionados em um estilo de exibição de árvore gráfica usando o painel de controle no lado esquerdo da janela da ferramenta, como mostrado abaixo.

![Exibir dados de configuração de rede em um modo de exibição de árvore.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Exibir dados de configuração de rede em um modo de exibição de árvore.")

**Definir conectores personalizados para links de topologia de rede do CAC (como links de site para região, região para região e links entre sites):** Os administradores do Lync Server 2013 podem definir conectores gráficos personalizados para o WAN links de configuração de rede do CAC usando a opção configurações, conforme mostrado a seguir. Isso ajuda a diferenciar entre os vários tipos de links de rede provisionados na configuração da rede.

![Definir conectores personalizados para a topologia de rede do CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definir conectores personalizados para a topologia de rede do CAC")

**Exibir informações do site de topologia de rede do CAC, informações de região e políticas de largura de banda provisionadas:** Os administradores do Lync Server 2013 podem exibir informações de região de rede do CAC, informações do site e informações de provisionamento de largura de banda do CAC relacionadas usando as opções mostradas abaixo. Por exemplo, clique em **Informações** em uma região da rede ou objeto do site da rede.

![Definir conectores personalizados para a sua rede.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definir conectores personalizados para a sua rede.")

</div>

<div>

## <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para os administradores do Lync Server 2013 que desejam exibir a topologia de rede do CAC para a implantação em um formato gráfico.

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>Agente do Grupo de Resposta em Tempo Real

O aplicativo Grupo de Resposta proporciona aos agentes a capacidade de acessar informações úteis em tempo real usando o serviço Web interno. Infelizmente, nenhuma exibição gráfica desses dados está disponível fora do aplicativo. A ferramenta agente do grupo de resposta do Live Resource Kit resolve esse problema fornecendo uma maneira simples e gráfica de acessar essas informações, aprimoradas com informações de software de comunicação do Microsoft Lync 2013, como a presença de outros agentes.

<div>

## <a name="description"></a>Descrição

O Agente do Grupo de Resposta em Tempo Real é um aplicativo do Windows que fornece a funcionalidade de entrar e sair e algumas informações em tempo real (como membros do grupo e número atual de chamadas) a agentes do Grupo de Resposta. Ele deve ser uma versão aprimorada da página de grupos de agente (acessível do Lync 2013.

</div>

<div>

## <a name="purpose"></a>Objetivo

O aplicativo Grupo de Resposta enfileira as chamadas recebidas e, em seguida, as encaminha para os grupos de agentes. Para tomar decisões conscientes sobre quais chamadas devem ser atendidas, os agentes podem acessar informações em tempo real sobre os grupos de agentes, como quais outros agentes estão disponíveis e quantas chamadas estão em espera em cada fila. Essas informações, inicialmente acessíveis somente por meio do serviço de Grupo de Resposta, são disponibilizadas de forma intuitiva pelo Agente do Grupo de Resposta em Tempo Real.

<div>

## <a name="features"></a>Recursos

A ferramenta de tempo de agente de grupo de resposta é criada no serviço de grupo de resposta e no SDK do Microsoft Lync 2013. Ela fornece aos agentes do Grupo de Resposta as informações e os recursos disponíveis no serviço de Grupo de Resposta (como membros do grupo, presença de outros agentes e número de chamadas em espera).

A figura abaixo ilustra a interface principal do Agente do Grupo de Resposta em Tempo Real.

![A ferramenta de tempo de agente do grupo de resposta.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "A ferramenta de tempo de agente do grupo de resposta.")

Os seguintes três recursos principais estão disponíveis para os agentes do Agente do Grupo de Resposta em Tempo Real:

  - **Entrada/saída:** Ao contrário da página grupos de agente (acessível do Lync 2013), o agente de resposta em tempo real permite que somente os agentes entrem em todos os grupos de agente ao mesmo tempo. Este aplicativo fornece três maneiras rápidas para os agentes entrarem ou sairem:
    
      - Clicar nos botões Entrar/sair (verde e vermelho) no aplicativo.
    
      - Clicar com o botão direito do mouse no ícone de bandeja do sistema e selecionar entrar ou sair.
    
      - Usar os atalhos do teclado configuráveis.

  - **Associação a um grupo:** Quando um grupo de agente é selecionado, o agente do grupo de resposta Live exibe a lista de agentes neste grupo no painel direito. Se o Lync 2013 estiver em execução no mesmo computador que este aplicativo, as informações de presença e o cartão de visita serão exibidos no agente do grupo de resposta ao vivo. Os agentes podem enviar uma mensagem instantânea ou ligar para outros agentes diretamente.

  - **Estatísticas em tempo real:** o Agente do Grupo de Resposta em Tempo Real fornece estatísticas em tempo real de todos os grupos de agentes. A frequência de atualização é de um minuto. Quando uma chamada é atendida por um Grupo de Resposta, um indicador visual é adicionado ao lado do nome do grupo com o número atual de chamadas em fila. Pausar o ponteiro sobre um grupo também exibe o tempo de espera mais longo.

</div>

</div>

<div>

## <a name="requirements"></a>Requisitos

O Agente do Grupo de Resposta em Tempo Real requer o .NET Framework 4.0. Além disso, para tirar proveito dos recursos de presença e cartão de contato, o Lync 2013 deve ser instalado localmente (e estar em execução).

<div>

## <a name="configuration"></a>Configuração

O Agente do Grupo de Resposta em Tempo Real pode ser personalizado de acordo com as preferências individuais usando a caixa de diálogo Opções no aplicativo. Além disso, o administrador pode definir o endereço de host padrão editando diretamente a propriedade defaultHostAddress do arquivo RGAgentLive.exe.config.

A figura abaixo ilustra a caixa de diálogo Opções que os agentes podem usar para configurar as teclas de atalho e o endereço de host. Essa caixa de diálogo é acessada clicando no botão Opções no canto superior direito da interface principal.

![A caixa de diálogo opções de agente do grupo de resposta em tempo real.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "A caixa de diálogo opções de agente do grupo de resposta em tempo real.")

As três configurações diferentes a seguir podem ser personalizadas na configuração do Agente do Grupo de Resposta em Tempo Real:

  - Endereço do host: normalmente este é o FQDN do pool da Web que pertence ao pool da página inicial do agente. O endereço de serviço exato do Grupo de Resposta é automaticamente derivado em segundo plano dessa informação (anexado no caminho à direita depois do host).

  - Atalhos: os atalhos exatos para entrar/sair podem ser personalizados. A única limitação é que ambos os atalhos devem conter a tecla do logotipo do Windows (além de pelo menos outra tecla).

  - Iniciar com o Windows: o aplicativo pode ser configurado para ser iniciado automaticamente com o Windows.

</div>

</div>

<div>

## <a name="examples"></a>Exemplos

A figura abaixo ilustra como chamar ou enviar uma mensagem instantânea para outro agente clicando com o botão direito do mouse no contato no painel à direita.

![Fazer uma chamada ou enviar uma mensagem instantânea.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Fazer uma chamada ou enviar uma mensagem instantânea.")

A figura abaixo ilustra como o Agente do Grupo de Resposta em Tempo Real exibe o número atual de chamadas na fila e o tempo de espera mais longo entre todas as chamadas de entrada.

![Exibir informações da fila.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Exibir informações da fila.")

</div>

<div>

## <a name="summary"></a>Resumo

Ações rápidas de entrada e saída, associação a um grupo e estatísticas básicas em tempo real são recursos interessantes do Agente do Grupo de Resposta que estão disponíveis apenas fora do aplicativo do serviço de Grupo de Resposta. Com a ferramenta de agente de resposta do Live Resource Kit, os administradores do Lync podem fornecer seus agentes com um aplicativo do Windows que permita executar tarefas de forma mais rápida e gráfica.

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

SEFAUtil (ativação de recurso de extensão secundária) é uma ferramenta de linha de comando que habilita os administradores do software de comunicações do Microsoft Lync Server 2013 e do helpdesk a configurar o toque, o encaminhamento de chamadas, o toque simultâneo, a chamada de equipe configurações e retirada de chamadas em grupo em nome de um usuário do Lync Server 2013. A ferramenta também permite que os administradores consultem as configurações de direcionamento de chamadas publicadas para um usuário específico. A ferramenta SEFAUtil permite que o administrador habilite/desabilite/modifique o encaminhamento de chamadas ou toque simultaneamente em nome do usuário. O administrador pode especificar o destino (na forma de um URI SIP) ou usar um destino que já foi publicado pelo usuário. Essa ferramenta também permite que os administradores adicionem ou removam representantes ou membros do grupo de chamada de equipe em nome do usuário. Essa ferramenta foi criada com o Microsoft Unified Communications Managed API (UCMA) 3,0 e requer que os administradores criem um aplicativo confiável no repositório de gerenciamento central para SEFAUtil

SEFAUtil (ativação de recurso de extensão secundária) permite que os administradores do Lync Server 2013 e do helpdesk configurem o recurso de toque, o encaminhamento de chamadas, o toque simultâneo, as configurações de chamada de equipe e a retirada de chamadas em grupo em nome de um usuário do Lync Server 2013 . Essa ferramenta também permite aos administradores consultar as configurações de roteamento de chamadas publicadas para determinado usuário.

<div>

## <a name="description"></a>Descrição

A versão atual de SEFAUtil é apenas uma ferramenta de linha de comando; não há nenhum suporte para interface gráfica do usuário. Esta ferramenta se baseia na API gerenciada de comunicação unificada da Microsoft (UCMA) 3,0. Os recursos dessa ferramenta permitem a administradores e agentes de assistência técnica realizar as seguintes ações:

  - Exibir todas as configurações de roteamento de chamadas de um usuário (inclui encaminhamento de chamadas, delegação, toque simultâneo, chamada de equipe e recebimento de chamada em grupo).

  - Habilitar/desabilitar/modificar a configuração de encaminhamento de chamadas (inclui temporizador sem resposta e de destino).

  - Habilitar/desabilitar/modificar configurações imediatas de encaminhamento de chamadas.

  - Habilitar/desabilitar/modificar configurações de delegação.

  - Habilitar/desabilitar/modificar configurações do grupo de chamada de equipe.
    
    <div>
    

    > [!NOTE]  
    > Novo na ferramenta SEFAUtil do Lync Server 2013

    
    </div>

  - Habilitar/desabilitar/modificar configurações de toque simultâneo (inclui destino).
    
    <div>
    

    > [!NOTE]  
    > Novo na ferramenta SEFAUtil do Lync Server 2013

    
    </div>

  - Habilitar/desabilitar/modificar configurações de recebimento de chamada em grupo.
    
    <div>
    

    > [!WARNING]  
    > Novo na ferramenta SEFAUtil do Lync Server 2013

    
    </div>

Esta ferramenta apresenta as seguintes limitações:

  - Com suporte somente para usuários hospedados em um pool do Lync Server

  - Não há suporte para edição em massa de configurações de roteamento de chamadas para diversos usuários.

</div>

<div>

## <a name="output"></a>Resultado

A versão atual desta ferramenta fornece resultados apenas na janela Prompt de Comando. Para ver detalhes, consulte a seção Exemplos mais adiante neste documento.

</div>

<div>

## <a name="purpose"></a>Objetivo

Veja a seguir alguns dos principais cenários onde esta ferramenta pode ser usada:

  - Bob é um executivo e foi movido para a telefonia do Lync Server. Ele já tem delegação em seu sistema PBX existente. Como parte da mudança para o Lync, o administrador é capaz de configurar o roteamento de Bob para refletir sua configuração de delegação já existente.

  - Brenda está viajando e aguarda uma chamada importante de um de seus clientes. No entanto, ela está em hotel e não tem acesso a computador. Ela liga para a assistência técnica e solicita que encaminhem para seu número de celular todas as chamadas feitas para seu número comercial. O pessoal da assistência técnica pode fazer a configuração em seu nome.

  - As chamadas de Vinícius para seu número comercial vão para a caixa postal de seu celular sempre que ele está no trabalho; no entanto, as coisas parecem estar funcionando corretamente na maioria dos outros locais. O técnico da assistência técnica consegue visualizar a configuração de roteamento de Vinícius e descobre que ele está com toque simultâneo configurado em seu celular. O técnico pergunta a Vinícius sobre a cobertura móvel em seu escritório e consegue determinar que a regra de toque simultâneo é o que está fazendo as chamadas irem para a caixa postal do celular de Vinícius quando sua cobertura de rede está fraca.

  - Mike é um novo funcionário da Contoso e ele está participando de uma nova equipe na qual todos os membros são configurados para chamada de equipe, quando habilitados para o Microsoft Lync, o administrador pode definir as configurações do grupo de chamada de equipe para incluir todos os novos membros da equipe, além de o administrador adiciona Mike como um membro do grupo de chamada de equipe para cada um dos membros da equipe.

  - Uma prática de atendimento ao cliente no departamento de recursos humanos da Contoso é fornecer um atendimento pessoal a todos os chamadores desde a primeira chamada. Como todos os membros do departamento sentam-se muito próximos uns dos outros, ter todos os telefones tocando ao mesmo tempo com a chamada de equipe é desconfortável para a equipe. Para fornecer o melhor serviço sem interromper os membros da equipe, o administrador do Lync aproveita o recurso de retirada de chamadas em grupo. O administrador adiciona todos os membros do departamento a um grupo de recebimento e informa o número do grupo de recebimento ao departamento. Quando Clara está fora de sua mesa, Vinícius percebe que o telefone dela está tocando e atende à chamada em sua própria mesa.

</div>

<div>

## <a name="requirements"></a>Requisitos

A ferramenta SEFAUtil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis. O UCMA 3.0 deve ser instalado nesse computador. Para executar a ferramenta, um novo aplicativo confiável com a ID do aplicativo SEFAUtil deve ser criado nesse pool.

**Criando um novo aplicativo confiável para a ferramenta SEFAUtil**

1.  A ferramenta SEFAUTil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis. Se necessário, adicionar um pool como um novo pool de aplicativos confiável pode ser feito por meio do Shell de gerenciamento do Lync Server com o seguinte cmdlet:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > O UCMA 3.0 deve ser instalado em qualquer computador que será usado para executar a ferramenta SEFAUtil.

    
    </div>

2.  Um aplicativo confiável precisa ser definido na topologia para a ferramenta SEFAUtil. Para definir SEFAUtil como um novo aplicativo confiável, use o Shell de gerenciamento do Lync Server e execute o seguinte cmdlet:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Uma porta diferente pode ser usada, se necessário.

    
    </div>

3.  As alterações de topologia precisam ser habilitadas. Habilitar as alterações de topologia pode ser feito por meio do Shell de gerenciamento do Lync Server executando o seguinte cmdlet:
    
        Enable-CsToplogy

4.  Se necessário, instale as ferramentas do Lync Server 2013 Resource Kit no servidor que serão usadas para executar a ferramenta SEFAUtil (o servidor deve fazer parte de um pool de aplicativos confiável).

5.  Verifique se o SEFAUtil está sendo executado corretamente. Para fazer isso, execute a ferramenta em um prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamadas de um usuário na implantação. Por padrão, a ferramenta estará localizada em: "... \\Arquivos\\de programa Microsoft Lync Server\\2013 reskit ". Para exibir as configurações de encaminhamento de chamadas de um usuário, use o seguinte comando:
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    As configurações de encaminhamento de chamadas do usuário devem ser exibidas.

<div>

## <a name="group-call-pickup"></a>Recebimento de Chamadas em Grupo

A retirada de chamadas em grupo requer configuração adicional no Lync Server para que a funcionalidade seja totalmente habilitada. Antes de atribuir grupos de atendimento aos usuários, consulte a documentação do produto de Recebimento de Chamadas em Grupo para ver as etapas de planejamento e implantação desse recurso.

</div>

</div>

<div>

## <a name="examples"></a>Exemplos

<div>

## <a name="display-current-call-handling-settings"></a>Exibir configurações atuais de administração de chamadas

O comando a seguir exibe a administração de chamadas do usuário. `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> Este exemplo usa a opção <STRONG>/Server</STRONG> para especificar o servidor do Lync para se conectar.



</div>

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>Definir destino de encaminhamento de chamadas/destino sem resposta

Este exemplo define o encaminhamento de chamadas/destino sem resposta e o atraso de toque. Aqui, a opção/Server não é fornecida; O SEFAUtil tenta descobrir o Lync Server.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>Habilitar o encaminhamento de chamadas imediatamente

Este exemplo habilita imediatamente o encaminhamento de chamadas para outro usuário.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**Saída**

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

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Adicionar um usuário como um representante e configurar o toque simultâneo dos representantes

Este exemplo adiciona um usuário como um representante e configura o toque simultâneo dos representantes:

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>Alterar regra de toque simultâneo dos representantes

Este exemplo altera a regra de toque simultâneo que foi definida no exemplo anterior à regra de toque atrasado.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**Resultado**

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
> Quando o ultimo representante é removido, o toque delegado é desabilitado automaticamente.



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Adicionar um representante e configurar a regra de encaminhamento de chamadas para representantes

Este exemplo adiciona um representante e configura a regra de encaminhamento de chamadas para representantes.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Habilitar toque simultâneo e definir um número de destino

Este exemplo habilita o toque simultâneo e define o número de destino do toque simultâneo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> Para alterar o número de destino do toque simultâneo de um usuário cujo toque simultâneo já está habilitado, mantenha o comando com a opção /enablesimulring; caso contrário, o número de destino não será alterado.



</div>

**Saída**

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

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Adicionar um membro da equipe para chamada de equipe e configurar toque simultâneo para o grupo de membros da chamada de equipe

Este exemplo adiciona um membro ao grupo de chamada de equipe de um usuário e habilita o toque simultâneo para o grupo de chamada de equipe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> Adicionar um membro ao grupo de chamada de equipe de um usuário mudará automaticamente as configurações de toque simultâneo dos usuários para o toque simultâneo do grupo de chamada de equipe desse membro.



</div>

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a>Remover um membro do grupo de chamada de equipe

Este exemplo remove um membro da equipe do grupo de chamada de equipe de um usuário.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> Se o membro a ser removido for o único membro do grupo de chamada de equipe, o toque simultâneo para o grupo de chamada de equipe será automaticamente desabilitado.



</div>

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>Definir toque atrasado para o grupo de chamada de equipe

Este exemplo altera o toque atrasado para a configuração de hora do grupo de chamada de equipe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a>Habilitar chamada de equipe

Isso habilita a chamada de equipe de determinado usuário.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> Se o grupo de chamada de equipe do usuário não tiver membros, a chamada de equipe não será habilitada.



</div>

**Saída**

</div>

<div>

## <a name="disable-team-call"></a>Desabilitar chamada de equipe

Este exemplo desabilita a chamada de equipe de um determinado usuário.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Habilitar recebimento de chamadas em grupo e atribuir um grupo de recebimento a um usuário

Este exemplo atribui um grupo de recebimento a um usuário e habilita o Recebimento de Chamadas em Grupo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**Saída**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a>Desabilitar recebimento de chamadas em grupo

Este exemplo desabilita o Recebimento de Chamadas em Grupo de determinado usuário.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> Ao desabilitar o Recebimento de Chamadas em Grupo de determinado usuário, o número do grupo que foi atribuído ao usuário não é retido. Se desejar habilitar novamente o Recebimento de Chamadas em Grupo para esse usuário, será necessário atribuir o numero do grupo novamente com a opção /enablegrouppickup.



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

SYSPrep. ps1 é um script do Windows PowerShell que instalará os seguintes pré-requisitos do Lync Server 2013 em seu computador do sistema operacional Windows Server 2008.

  - Microsoft .Net Framework 4.5

  - Microsoft SQL Server Express

  - Windows PowerShell versão 3.0

  - Pacotes Redistribuíveis do Visual C++ 2010

  - Atualizações do Servidor de Informações da Internet

  - Windows Identity Foundation

  - Arquivos principais do Lync Server 2013

Embora o nome do script seja semelhante à Ferramenta de Preparação do Sistema para os sistemas operacionais Microsoft Windows, eles são diferentes. Este script instalará somente os pré-requisitos obrigatórios do Lync Server 2013. Depois que esses requisitos estiverem instalados, a ferramenta SYSPrep do Windows poderá então ser usada para criar uma imagem do servidor.

</div>

<div>

## <a name="requirements"></a>Requisitos

Antes de executar o script SYSPrep. ps1, você deve copiar os arquivos de pré-requisito para uma pasta local no computador do sistema operacional Windows Server 2008 (por exemplo, **D:\\configuração)**. Essa pasta também deve incluir uma cópia dos arquivos do Lync Server 2013, especificamente **Setup. exe.** Os arquivos de pré-requisitos podem ser baixados dos seguintes locais:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pré-requisito</th>
<th>Local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .Net Framework 4.5</p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows PowerShell versão 3.0</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Pacotes Redistribuíveis do Visual C++ 2010</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Atualizações do Servidor de Informações da Internet</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Setup. exe do Lync Server 2013</p></td>
<td><p>Copiar da mídia do Lync Server 2013</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a>Parâmetro

O parâmetro **–SetupFolder** toma como argumento o local do diretório dos arquivos de pré-requisitos.

</div>

<div>

## <a name="examples"></a>Exemplos

Para executar o script SYSPrep. ps1 e instalar os pré-requisitos do Lync Server 2013, execute o seguinte comando em um prompt de comando elevado:

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>Migração de Comunicados de Número Não Atribuído

A ferramenta de migração de anúncios de número não atribuído permite que um administrador do Lync mova a configuração de números não atribuídos que é atendida pelo aplicativo de anúncio de um servidor ou de um servidor Lync de origem para um servidor ou grupo Lync de destino.

<div>

## <a name="description"></a>Descrição

A ferramenta de Migração de Comunicados de Número Não Atribuído é um script do Windows PowerShell que move a configuração de números não atribuídos atendidos pelo aplicativo de comunicados de um servidor ou pool de origem para outro servidor ou pool.

Quando executado, o script da Migração de Comunicados de Número não Atribuído realizará as seguintes operações:

1.  Mover todos os arquivos de áudio usados pelos comunicados de números não atribuídos do aplicativo de comunicado hospedado no servidor ou pool de origem para o repositório de arquivos do servidor ou pool de destino.
    
    <div>
    

    > [!NOTE]  
    > os arquivos de áudio são removidos do pool de origem quando são copiados para o pool de destino.

    
    </div>

2.  Mover todos os comunicados de números não atribuídos configurados do aplicativo de comunicados hospedado no servidor ou pool de origem para o servidor ou pool de destino.

3.  Atribuir novamente todos os intervalos de números não atribuídos que são atendidos pelo aplicativo de comunicados hospedado no servidor ou pool de origem ao servidor ou pool de destino.

Depois de executar o script com êxito, todos os intervalos de números não atribuídos que eram atendidos pelo aplicativo de comunicados hospedado no servidor ou pool de origem agora serão atendidos com a mesma configuração pelo servidor ou pool de destino.

</div>

<div>

## <a name="output"></a>Resultado

O script **move-CsAnnouncementConfiguration** indica na janela do Shell de gerenciamento do Lync a partir de onde ele é executado o êxito ou falha da operação de migração.

Se a execução da operação for interrompida por qualquer erro, os intervalos de números não atribuídos que foram movidos com êxito para o destino permanecerão no destino de uma forma operacional, e o restante dos intervalos de números não atribuídos a serem migrados permanecerá na origem também em uma forma operacional. Para migrar totalmente o restante da configuração, execute novamente o script depois de resolver o erro.

</div>

<div>

## <a name="purpose"></a>Objetivo

O script de Migração de Comunicados de Número Não Atribuído pode ser usado nos três cenários a seguir:

  - **Migrando definições de configuração para uma nova versão do Lync Server:** A Contoso está em processo de migração para o Lync Server 2013 e, como parte do processo de migração, o administrador do Lync Server gostaria de mover a configuração de números não atribuídas atendida pelo aplicativo de anúncio da implantação do Lync Server 2010 para a nova implantação do Lync Server 2013. Para mover as definições de configuração, o administrador do Lync Server usa a ferramenta de migração de anúncios de número não atribuído.

  - Reverter **uma implantação do Lync server 2013 para o Lync server 2010:** Devido a fatores inesperados, a contoso tem que reverter a migração para a nova implantação do Lync Server 2013. Para minimizar as interrupções do serviço, o administrador do Lync Server usa a ferramenta de migração de anúncios de número não atribuído para reverter a configuração da implantação do Lync Server 2013 para a implantação do Lync Server 2010.

  - **Mover dados entre implantações do Lync:** A Contoso está em processo de substituição de todos os servidores de um pool por servidores mais recentes. Sua estratégia é implantar um novo pool do Lync Server 2013, mover todos os dados do antigo para o novo pool e, em seguida, substituir o pool antigo. Depois que o novo pool é implantado, a ferramenta de migração anúncios de número não atribuído é usada para mover a configuração do pool antigo para o novo.

<div>

## <a name="requirements"></a>Requisitos

Os principais requisitos necessários para executar a ferramenta com êxito são os seguintes:

1.  O script deve ser executado em um computador com o Shell de gerenciamento do Lync Server 2013 instalado.

2.  O aplicativo de anúncio precisa ser implantado com êxito nos servidores ou pools de origem e de destino.

<div>

## <a name="move-csannouncementconfiguration-script"></a>Script Move-CsAnnouncementConfiguration

O script Move-CsAnnouncementConfiguration exige os dois parâmetros descritos na tabela abaixo. 

![Parâmetros move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Parâmetros move-CsAnnouncementConfiguration.")

</div>

</div>

</div>

<div>

## <a name="examples"></a>Exemplos

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>Mover a configuração de anúncios de número não atribuído de um pool do Lync Server 2010 para um pool do Lync Server 2013

Este exemplo move os anúncios de número não atribuído do pool de origem (Lync Server 2010) para o pool de destino (Lync Server 2013).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>Mover a configuração de anúncios de número não atribuído de um pool do Lync Server 2013 para um pool do Lync Server 2010

Este exemplo move os anúncios de número não atribuído do pool de origem (Lync Server 2013) para o pool de destino (Lync Server 2010).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>Web Conf Data

A ferramenta Web conf data permite que um administrador do software de comunicação do Lync Server 2013 tenha mais controle sobre os dados associados às conferências da Web do organizador. Os cenários incluem a capacidade de excluir os dados da reunião de um usuário específico com base em um critério de carimbo de data/hora.

<div>

## <a name="description"></a>Descrição

Esta ferramenta permite ao administrador executar as seguintes operações:

1.  Encontrar todos os dados de webconferência associados a um único usuário.

2.  Excluir todos os dados de webconferência associados a um único usuário.

3.  Excluir todos os dados de webconferência associados a um único usuário que sejam anteriores à determinada data.

4.  Mover todos os dados de webconferência associados a um único usuário quando o usuário for movido de um pool para outro.

<div>


> [!NOTE]  
> As ferramentas do kit de recursos para Lync Server 2010 têm suporte para mover todos os dados de Webconferência associados a um único usuário quando esse usuário é movido de um pool para outro. Essa funcionalidade agora foi preterida nesta ferramenta em favor do parâmetro <STRONG>MoveConferenceData</STRONG>. Para obter detalhes sobre esse parâmetro, consulte o cmdlet <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">move-CsUser</A> .



</div>

A ferramenta exclui dados apenas de reuniões que estejam inativas. As reuniões ativas (ou reuniões em sessões) não podem ser excluídas.

Essa ferramenta deve ser executada em um computador que esteja no mesmo pool do usuário de destino. O usuário cujos dados de conteúdo de reuniões estiverem sendo gerenciados por essa ferramenta deverá ser hospedado no mesmo pool de usuários.

</div>

<div>

## <a name="output"></a>Resultado

Essa ferramenta gera os resultados de cada uma das operações:

  - Se uma consulta é executada, a ferramenta gera a lista de todas as pastas de dados de reuniões inativas que tenham esse usuário como organizador.

  - Se uma exclusão é realizada, a ferramenta gera a lista de todas as pastas de dados de reuniões cujos dados serão excluídos.

</div>

<div>

## <a name="requirements"></a>Requisitos

A ferramenta deve ser executada no mesmo pool onde o organizador está hospedado.

A ferramenta deve ser executada com privilégios de administrador com acesso ao repositório de arquivos de conteúdo.

</div>

<div>

## <a name="examples"></a>Exemplos

A tabela a seguir descreve os parâmetros, alguns dos quais são usados nos exemplos.

![Parâmetros da ferramenta de dados Web conf.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parâmetros da ferramenta de dados Web conf.")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

O exemplo anterior mostra como um comando de consulta funcionaria. O resultado desse comando seria uma lista de todas as pastas de conteúdo de reuniões que seriam afetadas por essa ferramenta.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

O exemplo anterior mostra um comando de exclusão (delete), que removerá todas as pastas de reuniões inativas deste usuário.

</div>

<div>

## <a name="summary"></a>Resumo

Essa ferramenta pode ser um recurso valioso para os administradores que precisam de um controle mais preciso sobre os dados de reuniões realizadas em chamadas em conferência.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
