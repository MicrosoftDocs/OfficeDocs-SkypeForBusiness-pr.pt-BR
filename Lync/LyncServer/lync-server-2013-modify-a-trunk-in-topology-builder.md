---
title: 'Lync Server 2013: modificar um tronco no construtor de topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 001a94927d6160d138d344bf1a8fffcf519b58b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534388"
---
# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="541ab-102">Modificar um tronco no construtor de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="541ab-102">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="541ab-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="541ab-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="541ab-104">Siga estes passos para modificar o endereço IP de mídia alternativa e identificador alternativo de bypass de um tronco.</span><span class="sxs-lookup"><span data-stu-id="541ab-104">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="541ab-105">Para modificar o endereço IP de mídia alternativa de um tronco</span><span class="sxs-lookup"><span data-stu-id="541ab-105">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="541ab-106">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="541ab-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="541ab-107">Execute o cmdlet Set-CsPstnGateway e modifique o campo AlternateBypassId no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="541ab-107">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="541ab-108">Para modificar o BypassID alternativo de um tronco</span><span class="sxs-lookup"><span data-stu-id="541ab-108">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="541ab-109">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="541ab-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="541ab-110">Execute o cmdlet Set-CsPstnGateway e modifique o campo AlternateBypassId no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="541ab-110">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

