---
title: Criar ou modificar uma coleção de definições de configuração do servidor de borda A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faff058e2d4e2ef3a874ad5fcece3ad1422605c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="ca10f-102">Criar ou modificar uma coleção de definições de configuração de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca10f-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca10f-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ca10f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ca10f-p101">O serviço de Borda A/V fornece uma forma para seus usuários internos (usuários que não estão logados na sua rede organizacional) a compartilhar áudio e vídeo com usuários externos (usuários que não estão logados na sua rede organizacional). O serviço de Borda A/V é primariamente gerenciado utilizando definições de configuração de Borda A/V, configuração que pode ser definida no escopo do local ou no escopo do serviço (isto é, pode ser configurado para um serviço de Borda A/V individual.</span><span class="sxs-lookup"><span data-stu-id="ca10f-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="ca10f-106">Quando você instala o Lync Server, uma coleção global de definições de configuração de borda A/V é criada para você.</span><span class="sxs-lookup"><span data-stu-id="ca10f-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="ca10f-107">Além disso, você pode usar o Windows PowerShell e o cmdlet New-CsAVEdgeConfiguration para criar novas configurações no escopo do site ou no escopo do serviço (ou seja, para um servidor de borda A/V individual).</span><span class="sxs-lookup"><span data-stu-id="ca10f-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="ca10f-108">Se você criar novas configurações, tenha em mente que:</span><span class="sxs-lookup"><span data-stu-id="ca10f-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="ca10f-109">As definições configuradas no escopo de serviço (isto é, em um servidor individual ) têm prioridade sobre tudo.</span><span class="sxs-lookup"><span data-stu-id="ca10f-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="ca10f-p103">As definições configuradas no escopo do site têm prioridade sobre as definições configuradas no escopo global. No entanto, as definições de escopo de serviço também substituem as configurações de escopo do site.</span><span class="sxs-lookup"><span data-stu-id="ca10f-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="ca10f-112">As configurações no escopo global serão usadas somente se não há definições de serviço configuradas no servidor individual e se não há configurações de site para o site onde o servidor está localizado.</span><span class="sxs-lookup"><span data-stu-id="ca10f-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="ca10f-113">Qualquer configuração pode ser modificada utilizando o cmdlet Set-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ca10f-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="ca10f-114">Para obter mais informações, consulte os tópicos de ajuda para os cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) e [set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="ca10f-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="ca10f-115">Para criar novas definições de configuração de borda a/V no escopo do site</span><span class="sxs-lookup"><span data-stu-id="ca10f-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="ca10f-116">O comando a seguir criar uma nova coleção de definições de configuração de Borda A/V para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="ca10f-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="ca10f-117">Para criar definições de configuração de borda A/V personalizadas no escopo do site</span><span class="sxs-lookup"><span data-stu-id="ca10f-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="ca10f-p105">Por não haver parâmetros adicionais incluídos, essas novas configurações utilizarão os valores padrão para o serviço de Borda A/V. De forma alternativa, você pode adicionar parâmetros e valores de parâmetros para criar uma coleção personalizada. Por exemplo, este comando define a propriedade MaxTokenLifetime para 4 horas (04 horas : 00 minutos : 00 segundos):</span><span class="sxs-lookup"><span data-stu-id="ca10f-p105">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service. Alternatively, you can add additional parameters and parameter values to create a custom collection. For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="ca10f-121">Para criar definições de configuração de borda A/V personalizada no escopo do serviço</span><span class="sxs-lookup"><span data-stu-id="ca10f-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="ca10f-122">Este comando cria um conjunto similar aplicado ao servidor de Borda A/V atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ca10f-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="ca10f-123">Para modificar as definições de configuração de borda A/V existentes</span><span class="sxs-lookup"><span data-stu-id="ca10f-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="ca10f-124">Neste exemplo, o cmdlet Set-CsAVEdgeConfiguration é utilizado para alterar o tempo de vida máximo do token para o site Redmond para 12 horas:</span><span class="sxs-lookup"><span data-stu-id="ca10f-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca10f-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="ca10f-125">See Also</span></span>


[<span data-ttu-id="ca10f-126">Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca10f-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="ca10f-127">Excluir um conjunto existente de definições de configuração de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca10f-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="ca10f-128">Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca10f-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="ca10f-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca10f-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="ca10f-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca10f-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

