---
title: 'Lync Server 2013: configurar regiões de rede para o CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Configurar regiões de rede para o CAC no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

<div>


> [!IMPORTANT]  
> Se você já tiver criado regiões de rede para o E9-1-1 ou bypass de mídia, poderá modificar as regiões de rede existentes adicionando configurações específicas para o controle de admissão de chamadas (CAC) usando o cmdlet <STRONG>set-CsNetworkRegion</STRONG> . Para obter um exemplo de como modificar uma região de rede, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync Server 2013</A>.



</div>

*Regiões de rede* são os hubs de rede ou backbones usados na configuração do CAC, do E9-1 e do bypass de mídia. Use o procedimento a seguir para criar regiões de rede alinhadas às regiões de rede na topologia de rede de exemplo para o CAC. Para ver o exemplo de topologia de rede, consulte [exemplo: reunir seus requisitos de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) na documentação de planejamento.

O exemplo de topologia de rede para o CAC tem três regiões: América do Norte, EMEA e Ásia-Pacífico. Cada região tem um site central especificado. Para a região da América do Norte, o site central designado é chamado de CHICAGO. O procedimento a seguir mostra um exemplo de como você pode usar o cmdlet **New-CsNetworkRegion** para criar a região da América do Norte.

<div>


> [!NOTE]  
> No procedimento a seguir, o Shell de gerenciamento do Lync Server é usado para criar uma região de rede. Para obter detalhes sobre como usar o painel de controle do Lync Server para criar uma região de rede, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>Para criar uma região de rede para o controle de admissão de chamadas

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Para cada região que você precisa criar, execute o cmdlet **New-CsNetworkRegion** . Por exemplo, para criar a região da América do Norte, execute:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Repita a etapa 2 para criar as regiões de rede, EMEA e Ásia-Pacífico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

