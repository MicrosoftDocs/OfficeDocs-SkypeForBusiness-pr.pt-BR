---
title: 'Lync Server 2013: modificar um tronco no construtor de topologias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e185929294aa7c40ec4157b06bfe466ce328b04a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="d5358-102">Modificar um tronco no construtor de topologias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5358-102">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5358-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d5358-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d5358-104">Siga estas etapas para modificar o endereço IP de mídia alternativo e o identificador de bypass alternativo de um tronco.</span><span class="sxs-lookup"><span data-stu-id="d5358-104">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="d5358-105">Para modificar o endereço IP de mídia alternativo de um tronco</span><span class="sxs-lookup"><span data-stu-id="d5358-105">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="d5358-106">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d5358-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d5358-107">Execute o cmdlet Set-CsPstnGateway e modifique o campo AlternateBypassId no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5358-107">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="d5358-108">Para modificar o Bypassid alternativo de um tronco</span><span class="sxs-lookup"><span data-stu-id="d5358-108">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="d5358-109">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d5358-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d5358-110">Execute o cmdlet Set-CsPstnGateway e modifique o campo AlternateBypassId no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5358-110">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

