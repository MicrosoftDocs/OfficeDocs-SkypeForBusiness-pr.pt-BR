---
title: 'Lync Server 2013: retornar informações de configuração do servidor de borda A/V'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea7d7ed1ef74c092dac60ecfb2f009219564455
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="5e486-102">Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e486-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e486-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5e486-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5e486-104">O serviço de borda A/V fornece uma maneira para seus usuários internos (usuários que estão conectados à sua rede organizacional) para compartilhar áudio e vídeo com usuários externos (usuários que não estão conectados à sua rede organizacional).</span><span class="sxs-lookup"><span data-stu-id="5e486-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="5e486-105">O serviço de borda A/V é gerenciado principalmente pelo uso de configurações de borda A/V, a configuração que pode ser configurada no escopo do site ou no escopo do serviço (ou seja, pode ser configurada para um servidor de borda A/V individual).</span><span class="sxs-lookup"><span data-stu-id="5e486-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="5e486-106">Para retornar informações sobre as configurações de borda a/V em uso em sua organização, você deve usar o Windows PowerShell e o cmdlet Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5e486-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="5e486-107">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="5e486-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="5e486-108">As informações retornadas pelo cmdlet Get-CsAVEdgeConfiguration terão uma aparência semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="5e486-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="5e486-109">Para retornar informações de todas as suas configurações de borda A/V</span><span class="sxs-lookup"><span data-stu-id="5e486-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="5e486-110">O comando a seguir retorna informações sobre todas as configurações de borda a/V em uso no momento em sua organização:</span><span class="sxs-lookup"><span data-stu-id="5e486-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="5e486-111">Para retornar informações para configurações de borda com escopo de site A/V</span><span class="sxs-lookup"><span data-stu-id="5e486-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="5e486-112">Para retornar informações sobre uma coleção específica de definições de configuração de borda A/V, especifique a identidade dessa coleção ao executar o cmdlet Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5e486-112">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="5e486-113">Por exemplo, esse comando retorna informações somente para as configurações aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="5e486-113">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="5e486-114">Para retornar informações para configurações de borda de A/V com escopo de serviço</span><span class="sxs-lookup"><span data-stu-id="5e486-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="5e486-115">E esse comando retorna informações somente para configurações aplicadas a um servidor de borda A/V específico:</span><span class="sxs-lookup"><span data-stu-id="5e486-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e486-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="5e486-116">See Also</span></span>


[<span data-ttu-id="5e486-117">Criar ou modificar um conjunto de configurações de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e486-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="5e486-118">Excluir uma coleção existente de configurações de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e486-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="5e486-119">Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e486-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

