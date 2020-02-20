---
title: Configurar cenários do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e706edf9d66e3a1e9ac76eeac32ab882365e5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a>Configurar cenários do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-12-28_

Para executar a ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool), a topologia 2013 do Lync Server deve primeiro ser configurada para os cenários que serão executados. Se o Lync Server 2013 não estiver configurado ou configurado incorretamente, a simulação de carga falhará na maioria dos casos. Com a ferramenta de estresse e desempenho do Lync Server 2013, fornecemos exemplos de scripts do Shell de gerenciamento do Lync Server e arquivos de recursos básicos que podem ser usados como ponto de partida para configurar o Lync Server 2013. Este tópico descreve os exemplos do Windows PowerShell fornecidos. Observe que não é o objetivo deste tópico descrever como configurar o Lync Server 2013 em geral. Para obter detalhes sobre como trabalhar com o Windows PowerShell no Lync Server 2013, consulte a documentação do Shell <https://technet.microsoft.com/library/gg398474.aspx>de gerenciamento do Lync Server em.

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>Sobre a execução de scripts do Shell de gerenciamento do Lync Server

Fornecemos exemplos de scripts do Shell de gerenciamento do Lync Server que podem ser usados em preparação para executar a simulação de carga. Como os scripts se destinam à simulação de carga, eles são simples e permissivos e, portanto, podem não ser apropriados para produção. Todos os scripts são exemplos e devem ser revisados e, em alguns casos, modificados para refletir sua topologia. No mínimo, esperamos que o cenário do serviço de grupo de resposta (RGS) precise ser modificado para especificar os agentes atribuídos aos grupos de agentes. No entanto, você tem a opção de não simular esse carregamento.

<div>


> [!WARNING]  
> Tome cuidado ao examinar e compreender os exemplos fornecidos. Os scripts substituirão as configurações existentes na topologia.



</div>

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell e o Shell de gerenciamento do Lync Server, consulte o blog do <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>lync Server 2013 Windows PowerShell em.



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>Identificadores de versão do cliente da ferramenta de estresse e desempenho

Talvez seja necessário configurar a política de verificação de versão do cliente se você tiver alterado as configurações de valores padrão. Para obter detalhes, consulte "Configurando as versões <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>de cliente com suporte" em. A ferramenta de desempenho e stress do Lync Server 2013 usa as seguintes versões de agente de usuário por padrão ao se comunicar com o Lync Server 2013:

  - LSPT/15.0.0.0 (ferramenta de estresse e desempenho do Lync Server 2013)

  - OCPHONE/.0.522

Eles são para o cliente de mobilidade (UCWA) no LyncPerfTool:

  - Ferramenta de perf Ucwa/conferência da Web

  - Ferramenta Ucwa perf/móvel

</div>

</div>

<span> </span>

</div>

</div>

</div>

