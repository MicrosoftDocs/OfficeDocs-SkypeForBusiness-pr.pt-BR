---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daa85bae73df45fe8252973a3bf4d4e0690ec4a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="69810-102">Migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="69810-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69810-103">_**Última modificação do tópico:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="69810-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="69810-104">O Lync Server oferece suporte para dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="69810-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="69810-105">Especificamente, os dispositivos analógicos suportados são fones de áudio e faxes analógicos.</span><span class="sxs-lookup"><span data-stu-id="69810-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="69810-106">Você pode configurar os gateways qualificados para suportar o uso de dispositivos analógicos no seu ambiente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69810-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="69810-107">Após migrar do Lync Server 2010 para o Lync Server 2013, você também deve migrar os objetos de contato associados aos dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="69810-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="69810-108">Use o Shell de gerenciamento do Lync Server para recuperar primeiro todos os objetos de contato associados aos dispositivos analógicos do Lync Server 2010 e mova esses objetos para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69810-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="69810-109">Para migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="69810-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="69810-110">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="69810-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="69810-111">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="69810-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="69810-112">Verifique se todos os objetos de contato foram movidos para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69810-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="69810-113">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="69810-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="69810-114">Verifique se todos os objetos de contato agora estão associados ao pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69810-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

