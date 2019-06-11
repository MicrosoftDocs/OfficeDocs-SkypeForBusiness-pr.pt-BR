---
title: Excluir uma coleção existente de definições de configuração de um servidor de borda A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af42c338cb7032231ce562ac2227ff4089729ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="fb5d6-102">Excluir uma coleção existente de configurações de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5d6-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb5d6-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fb5d6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fb5d6-104">O serviço de borda A/V fornece uma maneira para seus usuários internos (usuários que estão conectados à sua rede organizacional) para compartilhar áudio e vídeo com usuários externos (usuários que não estão conectados à sua rede organizacional).</span><span class="sxs-lookup"><span data-stu-id="fb5d6-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="fb5d6-105">O serviço de borda A/V é gerenciado principalmente pelo uso de configurações de borda A/V, a configuração que pode ser configurada no escopo do site ou no escopo do serviço (ou seja, pode ser configurada para um servidor de borda A/V individual).</span><span class="sxs-lookup"><span data-stu-id="fb5d6-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="fb5d6-106">Quando você instala o Lync Server, uma coleção global de definições de configuração de borda A/V é criada para você.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="fb5d6-107">Esta coleção global não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="fb5d6-108">No entanto, você pode usar o Windows PowerShell e o cmdlet Remove-CsAVEdgeConfiguration para "redefinir" a coleção global; Isso simplesmente significa que todos os valores de propriedade na coleção global serão redefinidos para o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="fb5d6-109">Por exemplo, se você tiver definido a propriedade MaxTokenLifetime para 16 horas, essa propriedade será redefinida para o valor padrão de 8 horas.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="fb5d6-110">No entanto, as coleções de configurações personalizadas que você criou em um escopo de site ou o escopo do serviço podem ser excluídas usando o cmdlet Remove-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-110">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="fb5d6-111">Se você excluir configurações de site, os servidores de borda A/V nesse site serão gerenciados pelas configurações globais.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-111">If you delete site settings then A/V Edge servers in that site will be managed by the global settings.</span></span> <span data-ttu-id="fb5d6-112">Se você excluir as configurações de escopo de serviço, esse servidor será gerenciado por suas configurações de site, se existirem, ou pelas configurações globais, se nenhuma configuração de site estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-112">If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="fb5d6-113">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="fb5d6-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="fb5d6-114">Para redefinir a coleção global</span><span class="sxs-lookup"><span data-stu-id="fb5d6-114">To reset the global collection</span></span>

  - <span data-ttu-id="fb5d6-115">O comando a seguir redefine a coleção global de definições de configuração de borda A/V:</span><span class="sxs-lookup"><span data-stu-id="fb5d6-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="fb5d6-116">Para remover uma coleção do escopo do site</span><span class="sxs-lookup"><span data-stu-id="fb5d6-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="fb5d6-117">Este comando remove as configurações de borda a/V aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="fb5d6-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="fb5d6-118">Para remover uma coleção do escopo do serviço</span><span class="sxs-lookup"><span data-stu-id="fb5d6-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="fb5d6-119">Este comando remove as configurações aplicadas à atl-edge-001.litwareinc.com do servidor de borda a/V:</span><span class="sxs-lookup"><span data-stu-id="fb5d6-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb5d6-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="fb5d6-120">See Also</span></span>


[<span data-ttu-id="fb5d6-121">Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5d6-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="fb5d6-122">Criar ou modificar um conjunto de configurações de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5d6-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="fb5d6-123">Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5d6-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="fb5d6-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb5d6-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

