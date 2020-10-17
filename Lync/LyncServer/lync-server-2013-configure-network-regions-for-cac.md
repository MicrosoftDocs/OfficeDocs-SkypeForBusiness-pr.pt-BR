---
title: 'Lync Server 2013: configurar regiões de rede para CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c029de2a7b6296dc81d365978c55d18c817e0894
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520538"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Configurar regiões de rede para CAC no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

<div>


> [!IMPORTANT]  
> Se você já tiver criado regiões de rede para E9-1-1 ou desvio de mídia, você pode modificar as regiões de rede existentes adicionando configurações específicas ao controle de admissão de chamadas usando o cmdlet <STRONG>Set-CsNetworkRegion</STRONG>. Para obter um exemplo de como modificar uma região de rede, confira <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync Server 2013</A>.



</div>

*Regiões de rede* são hubs de rede ou backbones usados na configuração do CAC (controle de admissão de chamadas), E9-1-1 e desvio de mídia. Use os procedimentos a seguir para criar regiões de rede que alinham as regiões de rede no exemplo de topologia de rede para CAC. Para exibir a topologia de rede de exemplo, confira o [exemplo: reunindo seus requisitos para controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) na documentação de planejamento.

O exemplo de topologia de rede para CAC tem três regiões: América do Norte, EMEA e APAC. Cada região tem um site central especificado. Para a região da América do Norte, o site central designado é chamado CHICAGO. O procedimento a seguir mostra um exemplo de como é possível usar o cmdlet  **New-CsNetworkRegion** para criar a região América do Norte.

<div>


> [!NOTE]  
> No procedimento a seguir, o Shell de gerenciamento do Lync Server é usado para criar uma região de rede. Para obter detalhes sobre como usar o painel de controle do Lync Server para criar uma região de rede, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>Para criar uma região de rede para controle de admissão de chamada

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Para cada região que você precisa criar, execute o cmdlet **New-CsNetworkRegion**. Por exemplo, para criar a região América do Norte, execute:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Repita a etapa 2 para criar as regiões de rede EMEA e APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

