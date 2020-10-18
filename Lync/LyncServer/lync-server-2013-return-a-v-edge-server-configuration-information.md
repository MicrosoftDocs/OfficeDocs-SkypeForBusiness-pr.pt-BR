---
title: 'Lync Server 2013: retornar informações de configuração do servidor de borda A/V'
description: 'Lync Server 2013: retornar informações de configuração do servidor de borda A/V.'
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
ms.openlocfilehash: f4f72fccfe51b946dc0dc285aee12a07e59c844b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575437"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="8a4b7-103">Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4b7-103">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a4b7-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8a4b7-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8a4b7-p101">O serviço de Borda A/V fornece uma forma para seus usuários internos (usuários que não estão logados na sua rede organizacional) a compartilhar áudio e vídeo com usuários externos (usuários que não estão logados na sua rede organizacional). O serviço de Borda A/V é primariamente gerenciado utilizando definições de configuração de Borda A/V, configuração que pode ser definida no escopo do local ou no escopo do serviço (isto é, pode ser configurado para um serviço de Borda A/V individual.</span><span class="sxs-lookup"><span data-stu-id="8a4b7-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="8a4b7-107">Para retornar informações sobre as definições de configuração de borda A/V em uso na sua organização, você deve usar o Windows PowerShell e o cmdlet Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="8a4b7-107">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="8a4b7-108">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="8a4b7-108">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="8a4b7-109">As informações retornadas pelo cmdlet Get-CsAVEdgeConfiguration terão uma aparência semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="8a4b7-109">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="8a4b7-110">Para retornar informações de todas as suas definições de configuração de borda A/V</span><span class="sxs-lookup"><span data-stu-id="8a4b7-110">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="8a4b7-111">O comando a seguir retorna informações sobre todas as definições de configuração de borda A/V atualmente em uso na sua organização:</span><span class="sxs-lookup"><span data-stu-id="8a4b7-111">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="8a4b7-112">Para retornar informações para definições de configuração de borda A/V com escopo de site</span><span class="sxs-lookup"><span data-stu-id="8a4b7-112">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="8a4b7-113">Para retornar informações sobre uma coleção específica de definições de configuração de borda A/V, especifique a identidade dessa coleção ao executar o cmdlet Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="8a4b7-113">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="8a4b7-114">Por exemplo, este comando retorna informações somente para as configurações aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="8a4b7-114">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="8a4b7-115">Para retornar informações para definições de configuração de borda de A/V de escopo de serviço</span><span class="sxs-lookup"><span data-stu-id="8a4b7-115">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="8a4b7-116">E este comando retorna informações somente para as configurações aplicadas a um servidor de borda A/V específico:</span><span class="sxs-lookup"><span data-stu-id="8a4b7-116">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a4b7-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="8a4b7-117">See Also</span></span>


[<span data-ttu-id="8a4b7-118">Criar ou modificar uma coleção de definições de configuração de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4b7-118">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="8a4b7-119">Excluir um conjunto existente de definições de configuração de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4b7-119">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="8a4b7-120">Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a4b7-120">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

