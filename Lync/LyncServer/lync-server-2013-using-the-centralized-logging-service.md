---
title: 'Lync Server 2013: usando o serviço de log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb3687d036f7d72160c8af0e168a40d09c84e4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Usar o serviço de log centralizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

O serviço de log centralizado é um novo recurso do Lync Server 2013. É uma substituição aprimorada para as ferramentas **OCSLogger** e **OCSTracer** fornecidas em versões anteriores. Você pode usar o serviço de log centralizado para executar as seguintes tarefas:

  - Comece a fazer logon em um ou mais computadores e pools a partir de um único local e comando.

  - Parar de fazer logon em um ou mais computadores e pools a partir de um único local e comando.

  - Pesquisar logs em um ou mais computadores e pools para um único local e comando. Você pode personalizar o comando Pesquisar para retornar toda a agregação de registros que foram capturados e armazenados em todas as máquinas ou retornar um resultado aparado que captura dados específicos.

  - Configurar as sessões de registro em log conforme segue:
    
      - Definir um **Cenário** ou usar um cenário padrão. Um *cenário* no serviço de log centralizado é composto de escopo (global ou de site), um nome de cenário para identificar a finalidade do cenário e um ou mais provedores. Você pode executar dois cenários a qualquer momento em um computador.
    
      - Usar um *provedor* local ou criar um novo provedor. Um *provedor* define o que será coletado pela sessão de registro em log, o nível de detalhamento, quais componentes serão rastreados e quais sinalizadores serão aplicados.
        
        <div>
        

        > [!TIP]  
        > Se estiver familiarizado com OCSLogger, o termo <EM>provedores</EM> se refere à coleta de <STRONG>componentes</STRONG> (por exemplo, S4, SIPStack), um <STRONG>tipo de registro de log</STRONG> (por exemplo, WPP, EventLog ou IIS logfile), um <STRONG>nível de rastreamento</STRONG> (por exemplo, All, verbose, debug) e <STRONG>sinalizadores</STRONG> (por exemplo, TF_COMPONENT, TF_DIAG). Esses itens são definidos no provedor (uma variável do Windows PowerShell) e passados para o comando de serviço de log centralizado.

        
        </div>
    
      - Configurar os computadores e os pools dos quais você deseja coletar logs.
    
      - Defina o escopo da sessão de log no **site** de opções (execute o log de capturas somente em computadores nesse site) ou **global** (execute a captura de log em todos os computadores na implantação).

O serviço de registro centralizado é extremamente eficiente e atende a praticamente todas as necessidades para solucionar problemas, sejam grandes ou pequenos. Da análise de causa raiz para problemas de desempenho, o serviço de registro em log centralizado pode ser uma ferramenta importante para qualquer administrador. Todos os exemplos são exibidos usando o Shell de gerenciamento do Lync Server. Há um componente de linha de comando para o serviço de log centralizado chamado **CLSController. exe**. A ajuda é fornecida para a ferramenta de linha de comando por meio da própria ferramenta. No entanto, há um conjunto limitado de funções que você pode executar a partir da linha de comando. Ao usar o Shell de gerenciamento do Lync Server, você tem acesso a um conjunto muito maior e muito mais configurável de recursos. Você sempre deve considerar o Shell de gerenciamento do Lync Server como o principal método ao usar o serviço de log centralizado.

Os tópicos desta seção explicam como usar o serviço de log centralizado e exemplos de como usar seus muitos recursos.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Visão geral do serviço de log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Gerenciar as configurações centralizadas de configuração do serviço de log no Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Compreendendo as configurações centralizadas de configuração do serviço de log no Lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Usar o Start para o serviço de log centralizado para capturar logs no Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Usar stop para o serviço de log centralizado no Lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Usar a pesquisa em logs de captura criados pelo serviço de log centralizado no Lync Server 2013](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Ler logs de captura do serviço de log centralizado no Lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

