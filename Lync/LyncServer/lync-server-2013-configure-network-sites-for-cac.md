---
title: 'Lync Server 2013: configurar sites de rede para CAC'
description: 'Lync Server 2013: configurar sites de rede para CAC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24adbbb1f5ee46618c685e072d519a338cb9b0af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564997"
---
# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Configurar sites de rede para CAC no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Se você já tiver criado sites de rede para o E9-1-1 ou bypass de mídia, poderá modificar os sites de rede existentes para aplicar um perfil de política de largura de banda usando o cmdlet <STRONG>set-CsNetworkSite</STRONG> . Para obter um exemplo de como modificar um site de rede, confira <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync Server 2013</A>.



</div>

Os *sites de rede* são os escritórios ou locais dentro de cada região de rede do CAC (controle de admissão de chamadas), E9-1-1 e implantações de bypass de mídia. Use os procedimentos a seguir para criar sites de rede que se alinhem a sites de rede no exemplo de topologia de rede para CAC. Estes procedimentos mostram como criar e configurar sites de rede que são restritos pela largura de banda WAN e, portanto, exigem políticas de largura de banda que limitam o fluxo de tráfego de áudio ou vídeo em tempo real.

No exemplo de implantação do CAC, a região da América do Norte tem seis sites. Três desses sites são restritos pela largura de banda de WAN: Reno, Portland e Albuquerque. Os outros três sites, que *não* são restritos pela largura de banda de WAN: Nova York, Chicago e Detroit. Para obter um exemplo de como criar ou modificar outros sites de rede, confira [criar ou modificar um site de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Para exibir a topologia de rede de exemplo, confira o [exemplo: reunindo seus requisitos para controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) na documentação de planejamento.

<div class=" ">


> [!NOTE]  
> No procedimento a seguir, o Shell de gerenciamento do Lync Server é usado para criar um site de rede. Para obter detalhes sobre como usar o painel de controle do Lync Server para criar um site de rede, consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">create or Modify a Network site in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>Para criar sites de rede para controle de admissão de chamadas

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet **New-CsNetworkSite** para criar sites de rede e aplicar um perfil de política de largura de banda apropriado a cada site. Por exemplo, execute:
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Para concluir a criação de sites de rede para toda a topologia de exemplo, repita a etapa 2 para os sites de rede com restrição de largura de banda nas regiões da EMEA e da África.

</div>

</div>

<span> </span>

</div>

</div>

</div>

