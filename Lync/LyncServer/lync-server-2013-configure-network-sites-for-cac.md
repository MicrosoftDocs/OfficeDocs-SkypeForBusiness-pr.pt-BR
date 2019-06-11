---
title: 'Lync Server 2013: configurar sites de rede para o CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 528ed67243fb0ab0451abf504a458afc420d94ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Configurar sites de rede para o CAC no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Se você já tiver criado sites de rede para o E9-1-1 ou bypass de mídia, poderá modificar os sites de rede existentes para aplicar um perfil de política de largura de banda usando o cmdlet <STRONG>set-CsNetworkSite</STRONG> . Para obter um exemplo de como modificar um site de rede, consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync Server 2013</A>.



</div>

*Sites de rede* são os escritórios ou locais em cada região de rede do controle de admissão de chamadas (CAC), E9-1-1 e implantações de bypass de mídia. Use os procedimentos a seguir para criar sites de rede alinhados a sites de rede na topologia de rede de exemplo para o CAC. Esses procedimentos mostram como criar e configurar sites de rede que são restringidos pela largura de banda WAN e, portanto, exigem políticas de largura de banda que limitam o fluxo de tráfego de áudio ou vídeo em tempo real.

No exemplo de implantação de CAC, a região da América do Norte tem seis sites. Três desses sites são restringidos pela largura de banda de WAN: Reno, Portland e Albuquerque. Os outros três sites, que *não* são restringidos pela largura de banda de WAN: Nova York, Chicago e Detroit. Para obter um exemplo de como criar ou modificar esses outros sites de rede, consulte [criar ou modificar um site de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Para ver o exemplo de topologia de rede, consulte [exemplo: reunir seus requisitos de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) na documentação de planejamento.

<div class=" ">


> [!NOTE]  
> No procedimento a seguir, o Shell de gerenciamento do Lync Server é usado para criar um site de rede. Para obter detalhes sobre como usar o painel de controle do Lync Server para criar um site de rede, consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>Para criar sites de rede para controle de admissão de chamadas

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet **New-CsNetworkSite** para criar sites de rede e aplicar um perfil de política de largura de banda apropriado para cada site. Por exemplo, execute:
    
       ```
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Para concluir a criação de sites de rede para toda a topologia de exemplo, repita a etapa 2 para os sites de rede com largura de banda restrita nas regiões da EMEA e da Ásia-Pacífico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

