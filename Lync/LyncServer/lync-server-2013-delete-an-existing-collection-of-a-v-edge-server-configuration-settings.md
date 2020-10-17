---
title: Excluir um conjunto existente de definições de configuração do servidor de borda A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80a90e58c1dee8aacae052f916c6fdf6e260b7ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514688"
---
# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="86a19-102">Excluir um conjunto existente de definições de configuração de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86a19-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86a19-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="86a19-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="86a19-p101">O serviço de Borda A/V fornece uma forma para seus usuários internos (usuários que não estão logados na sua rede organizacional) a compartilhar áudio e vídeo com usuários externos (usuários que não estão logados na sua rede organizacional). O serviço de Borda A/V é primariamente gerenciado utilizando definições de configuração de Borda A/V, configuração que pode ser definida no escopo do local ou no escopo do serviço (isto é, pode ser configurado para um serviço de Borda A/V individual.</span><span class="sxs-lookup"><span data-stu-id="86a19-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="86a19-106">Quando você instala o Lync Server, uma coleção global de definições de configuração de borda A/V é criada para você.</span><span class="sxs-lookup"><span data-stu-id="86a19-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="86a19-107">Esta coleção global não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="86a19-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="86a19-108">No entanto, você pode usar o Windows PowerShell e o cmdlet Remove-CsAVEdgeConfiguration para "redefinir" a coleção global; Isso simplesmente significa que todos os valores de propriedade na coleção global serão redefinidos para o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="86a19-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="86a19-109">Por exemplo, se você tiver definido a propriedade MaxTokenLifetime para 16 horas, essa propriedade será redefinida com o valor padrão de 8 horas.</span><span class="sxs-lookup"><span data-stu-id="86a19-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="86a19-110">No entanto, as coleções de configurações personalizadas criadas no escopo do site ou no escopo do serviço podem ser excluídas usando o cmdlet Remove-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="86a19-110">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="86a19-111">Se você excluir as configurações do site, os servidores de borda A/V desse site serão gerenciados pelas configurações globais.</span><span class="sxs-lookup"><span data-stu-id="86a19-111">If you delete site settings then A/V Edge servers in that site will be managed by the global settings.</span></span> <span data-ttu-id="86a19-112">Se você excluir as configurações de escopo de serviço, esse servidor será gerenciado por suas configurações de site, se existirem, ou pelas configurações globais, se nenhuma configuração de site estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="86a19-112">If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="86a19-113">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="86a19-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="86a19-114">Para redefinir a coleção global</span><span class="sxs-lookup"><span data-stu-id="86a19-114">To reset the global collection</span></span>

  - <span data-ttu-id="86a19-115">O comando a seguir redefine o conjunto global de definições de configuração de borda A/V:</span><span class="sxs-lookup"><span data-stu-id="86a19-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="86a19-116">Para remover uma coleção do escopo do site</span><span class="sxs-lookup"><span data-stu-id="86a19-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="86a19-117">Este comando remove as definições de configuração de borda A/V aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="86a19-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="86a19-118">Para remover uma coleção do escopo do serviço</span><span class="sxs-lookup"><span data-stu-id="86a19-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="86a19-119">Este comando remove as configurações aplicadas ao servidor de borda A/V atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="86a19-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86a19-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="86a19-120">See Also</span></span>


[<span data-ttu-id="86a19-121">Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86a19-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="86a19-122">Criar ou modificar uma coleção de definições de configuração de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86a19-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="86a19-123">Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86a19-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="86a19-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="86a19-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

