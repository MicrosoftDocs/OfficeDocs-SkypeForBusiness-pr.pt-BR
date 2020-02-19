---
title: 'Lync Server 2013: exibir informações sobre troncos SIP individuais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bda72dbe9745ca49d90e28824ea11371fbc2c680
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="d4b13-102">Exibir informações sobre troncos SIP individuais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4b13-102">View information about individual SIP trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4b13-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d4b13-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d4b13-104">Os troncos SIP são usados para conectar a rede de telefone de voz sobre IP do Lync Server 2013 com a rede telefônica pública comutada.</span><span class="sxs-lookup"><span data-stu-id="d4b13-104">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="d4b13-105">Na versão anterior do produto, os troncos foram usados para rotear chamadas de saída de um servidor de mediação para um gateway PSTN, e cada gateway estava limitado a um único tronco.</span><span class="sxs-lookup"><span data-stu-id="d4b13-105">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="d4b13-106">Como resultado, um gateway PSTN e um tronco SIP eram essencialmente idênticos.</span><span class="sxs-lookup"><span data-stu-id="d4b13-106">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="d4b13-107">Para administradores, isso significava que poderia exibir informações sobre um tronco SIP individual simplesmente exibindo informações sobre o gateway PSTN associado.</span><span class="sxs-lookup"><span data-stu-id="d4b13-107">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="d4b13-108">No Lync Server 2013, no entanto, vários troncos agora podem ser atribuídos a um único gateway PSTN; Isso significa que os gateways e troncos não são mais um e o mesmo.</span><span class="sxs-lookup"><span data-stu-id="d4b13-108">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="d4b13-109">Por sua vez, isso significa que os administradores devem usar o novo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) para exibir informações sobre um tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="d4b13-109">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="d4b13-110">O cmdlet Get-CsTrunk pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4b13-110">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d4b13-111">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="d4b13-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="d4b13-112">Para exibir informações de todos os troncos SIP</span><span class="sxs-lookup"><span data-stu-id="d4b13-112">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="d4b13-113">O seguinte comando retorna informações sobre todos os troncos SIP em uso na sua organização:</span><span class="sxs-lookup"><span data-stu-id="d4b13-113">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="d4b13-114">Para exibir informações de um tronco SIP específico</span><span class="sxs-lookup"><span data-stu-id="d4b13-114">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="d4b13-115">Este comando retorna informações somente para o tronco SIP com a identidade PstnGateway: 192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="d4b13-115">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="d4b13-116">Exibindo informações de todos os troncos SIP atribuídos a um pool</span><span class="sxs-lookup"><span data-stu-id="d4b13-116">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="d4b13-117">Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="d4b13-117">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

