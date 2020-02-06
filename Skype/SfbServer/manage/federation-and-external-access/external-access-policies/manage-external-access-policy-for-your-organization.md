---
title: Gerenciar política de acesso externo para sua organização
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Após implantar um ou mais servidores de borda, você deve habilitar os tipos de acesso externo que terão suporte para a sua organização.
ms.openlocfilehash: e4405585da71dc48f5fa1790f83938a814270d84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818272"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="a8cb5-103">Gerenciar política de acesso externo para sua organização</span><span class="sxs-lookup"><span data-stu-id="a8cb5-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="a8cb5-104">Após implantar um ou mais servidores de borda, você deve habilitar os tipos de acesso externo que terão suporte para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="a8cb5-105">Por padrão, não há políticas configuradas para dar suporte a acesso externo a usuários, incluindo acesso de usuário remoto, acesso de usuário federado, mesmo que você já tenha habilitado o acesso de usuário externo à sua organização.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="a8cb5-106">Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de acesso de usuário externo com suporte para cada política.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="a8cb5-107">Os seguintes escopos de política estão disponíveis para criação e configuração.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="a8cb5-108">Por padrão, a política global é criada, mas não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="a8cb5-109">**Política global a**   política global é criada quando você implanta seus servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="a8cb5-110">Por padrão, nenhuma opção de acesso de usuário externo está habilitada na política global.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="a8cb5-111">Para dar suporte ao acesso de usuário externo no nível global, configure a política global para dar suporte a um ou mais tipos de opções de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="a8cb5-112">A política global aplica-se a todos os usuários em sua organização, mas políticas de site e políticas de usuário substituem a política global.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="a8cb5-113">Se você excluir a política global, não a removerá.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="a8cb5-114">Em vez disso, redefina-o para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="a8cb5-115">**Política de site**   você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="a8cb5-116">A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="a8cb5-117">Por exemplo, se você habilitar o acesso de usuário remoto na política global, poderá especificar uma política de site que desabilite o acesso de usuário remoto para um site específico.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="a8cb5-118">Por padrão, uma política de site é aplicada a todos os usuários do site, mas você pode atribuir uma política de usuário a um usuário para substituir a configuração de política do site.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="a8cb5-119">**Política de usuário**   você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte para acesso de usuário remoto a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="a8cb5-120">A configuração na política de usuário substitui a política global e do site, mas somente para os usuários específicos aos quais a política de usuário está atribuída.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="a8cb5-121">Por exemplo, se você habilitar o acesso de usuário remoto na política global e na política do site, poderá especificar uma política de usuário que desabilite o acesso de usuário remoto e atribua essa política de usuário a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="a8cb5-122">Se você criar uma política de usuário, deverá aplicá-la a um ou mais usuários antes de entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="a8cb5-123">As definições de política que são aplicadas em determinado nível de política podem substituir definições que são aplicadas em outro nível.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="a8cb5-124">A precedência de política do Skype for Business Server é: a política do usuário (maior influência) substitui uma política do site e, em seguida, uma política de site substitui uma política global (influência mínima).</span><span class="sxs-lookup"><span data-stu-id="a8cb5-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="a8cb5-125">Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="a8cb5-126">Essas opções incluem os seguintes tipos de acesso externo:</span><span class="sxs-lookup"><span data-stu-id="a8cb5-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="a8cb5-127">**Habilitar comunicações com usuários**   federados habilitá-lo se você quiser dar suporte ao acesso de usuários a domínios de parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="a8cb5-128">Essa configuração define a capacidade dos usuários de se comunicarem com outros domínios federados do SIP, bem como provedores hospedados como o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> 


  - <span data-ttu-id="a8cb5-129">**Habilitar comunicações com usuários**   remotos habilite essa opção se você quiser que os usuários em sua organização que estão fora do seu firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Skype for Business Server pela Internet.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="a8cb5-130">**Habilitar comunicações com usuários**   públicos habilite essa opção se você quiser que os usuários internos possam se comunicar com contatos públicos do provedor de mensagens de chat.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="a8cb5-131">Além de habilitar o suporte ao acesso do usuário externo, você também deve configurar políticas para controlar o uso do acesso de usuários externos em sua organização antes que qualquer tipo de acesso de usuário externo esteja disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="a8cb5-132">Para obter detalhes sobre como criar, configurar e aplicar políticas de acesso de usuário externo, consulte [habilitar ou desabilitar o acesso de usuários remotos](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a8cb5-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="a8cb5-133">**Para exibir as políticas de acesso externo usando cmdlets do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a8cb5-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="a8cb5-134">Você pode exibir as políticas de acesso externo usando o Shell de gerenciamento do Skype for Business Server e o cmdlet **Get-CsExternalAccessPolicy** .</span><span class="sxs-lookup"><span data-stu-id="a8cb5-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="a8cb5-135">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="a8cb5-136">Para ver as informações sobre todas as suas políticas de acesso externo, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="a8cb5-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="a8cb5-137">Este comando retorna informações semelhantes para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a8cb5-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
