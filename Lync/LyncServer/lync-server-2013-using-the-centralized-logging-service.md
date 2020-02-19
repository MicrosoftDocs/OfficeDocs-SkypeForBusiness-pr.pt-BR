---
title: 'Lync Server 2013: usando o serviço de registro em log centralizado'
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
ms.openlocfilehash: cf3c0cedcb45ad631464c0db648205b8421cd460
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Usando o serviço de registro em log centralizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O serviço de registro centralizado é um novo recurso no Lync Server 2013. É uma substituição melhorada para as ferramentas **OCSLogger** e **OCSTracer** fornecidas em lançamentos anteriores. Você pode usar o serviço de registro em log centralizado para executar as seguintes tarefas:

  - Faça login em um ou mais computadores e pools de um único local e comando.

  - Pare o login em um ou mais computadores e pools de um único local e comando.

  - Busque logs em um ou mais computadores e pools de um único local e comando. É possível personalizar o comando de busca para retornar todo o conjunto de logs que foram capturados e armazenados em todas as máquinas, ou retornar um resultado reduzido que capture dados específicos.

  - Configurar as sessões de login conforme segue:
    
      - Defina um **Cenário** ou use um cenário default. Um *cenário* no serviço de registro em log centralizado é feito de escopo (global ou site), um nome de cenário para identificar a finalidade do cenário e um ou mais provedores. Você pode executar dois cenários a qualquer momento em um computador.
    
      - Use um .*provedor*local ou crie um novo provedor. Um *provedor* define o que será coletado pela sessão de registro em log, qual o detalhamento, quais componentes rastrear e quais o que sinalizadores são aplicados.
        
        <div>
        

        > [!TIP]  
        > Se estiver familiarizado com OCSLogger, o termo <EM>provedores</EM> se refere à coleta de <STRONG>componentes</STRONG> (por exemplo, S4, SIPStack), um <STRONG>tipo de registro de log</STRONG> (por exemplo, WPP, EventLog ou IIS logfile), um <STRONG>nível de rastreamento</STRONG> (por exemplo, All, verbose, debug) e <STRONG>sinalizadores</STRONG> (por exemplo, TF_COMPONENT, TF_DIAG). Esses itens são definidos no provedor (uma variável do Windows PowerShell) e passados para o comando de serviço de registro em log centralizado.

        
        </div>
    
      - Configure os computadores e pools dos quais deseja coletar registros log.
    
      - Defina o escopo da sessão de registro log nas opções**Local** (executa capturas de registro log em computadores somente naquele local) ou **Global** (executa capturas de registro log em todos os computadores da implantação).

O serviço de registro em log centralizado é extremamente poderoso e pode atender a praticamente todas as necessidades de solução de problemas, grandes ou pequenos. Da análise de causa raiz para problemas de desempenho, o serviço de registro em log centralizado pode ser uma ferramenta importante para qualquer administrador. Todos os exemplos são mostrados usando o Shell de gerenciamento do Lync Server. Há um componente de linha de comando para o serviço de registro em log centralizado chamado **CLSController. exe**. A ajuda para a ferramenta de linha de comando está disponível na própria ferramenta. Por esta razão, a primeira linha neste exemplo é uma chamada ao cmdlet do nm-winshell-2nd Read-Host. Usando o Shell de gerenciamento do Lync Server, você tem acesso a um conjunto muito maior e mais configurável de recursos. Você deve sempre considerar o Shell de gerenciamento do Lync Server como o primeiro método ao usar o serviço de registro em log centralizado.

Os tópicos desta seção explicam como usar o serviço de registro em log centralizado e exemplos de como usar seus vários recursos.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Visão geral do serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Gerenciando as definições de configuração do serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Noções básicas sobre definições de configuração de serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Usando iniciar para o serviço de registro em log centralizado para capturar logs no Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Usando stop para o serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Usando a pesquisa nos logs de captura criados pelo serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Ler logs de captura do serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

