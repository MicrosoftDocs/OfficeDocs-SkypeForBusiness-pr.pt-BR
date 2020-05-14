---
title: Gerenciar a política de acesso externo da sua organização
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
description: Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso externo que terão suporte na sua organização.
ms.openlocfilehash: e3feecfffa591df5433ce45526ec236ca6ef8b42
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221655"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="0b334-103">Gerenciar a política de acesso externo da sua organização</span><span class="sxs-lookup"><span data-stu-id="0b334-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="0b334-104">Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso externo que terão suporte na sua organização.</span><span class="sxs-lookup"><span data-stu-id="0b334-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="0b334-p101">Por padrão, não há políticas configuradas para suportar o acesso de usuário externo, incluindo o acesso de usuário remoto, acesso de usuário federado, mesmo que você já tenha habilitado o suporte de acesso de usuário externo para sua organização. Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de acesso de usuário externo suportado para cada política. Os escopos da política a seguir estão disponíveis para criação e configuração. Por padrão, a política global é criada, mas não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="0b334-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="0b334-109">**Política global**   A política global é criada quando você implanta seus Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="0b334-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="0b334-110">Por padrão, nenhuma opção de acesso do usuário externo está habilitada na política global.</span><span class="sxs-lookup"><span data-stu-id="0b334-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="0b334-111">Para suportar o acesso do usuário externo a nível global, você deve configurar a política global para suportar um ou mais tipos de opções de acesso do usuário externo.</span><span class="sxs-lookup"><span data-stu-id="0b334-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="0b334-112">A política global se aplica a todos os usuários na sua organização, mas as políticas locais e as políticas de usuário substituem a política global.</span><span class="sxs-lookup"><span data-stu-id="0b334-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="0b334-113">Ao excluir a política global, ela não é removida.</span><span class="sxs-lookup"><span data-stu-id="0b334-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="0b334-114">Ao invés, é redefinida para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="0b334-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="0b334-115">**Política de site**   Você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos.</span><span class="sxs-lookup"><span data-stu-id="0b334-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="0b334-116">A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política.</span><span class="sxs-lookup"><span data-stu-id="0b334-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="0b334-117">Por exemplo, se você ativar o acesso de usuário remoto na política global, pode especificar uma política de local que o desative para um local específico.</span><span class="sxs-lookup"><span data-stu-id="0b334-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="0b334-118">Por padrão, a política de local é aplicada a todos os usuários do local, mas você pode atribuir uma política de usuário para substituir a configuração da política de local.</span><span class="sxs-lookup"><span data-stu-id="0b334-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="0b334-119">**Política de usuário**   Você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte ao acesso de usuário remoto a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="0b334-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="0b334-120">A configuração da política de usuário substitui a política global e a do local, mas apenas para usuários específicos aos quais a política de usuário é atribuída.</span><span class="sxs-lookup"><span data-stu-id="0b334-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="0b334-121">Por exemplo, se você ativar o acesso de usuário remoto na política global e na de local, deve especificar uma política de usuário que a desative e depois atribuir essa política de usuário a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="0b334-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="0b334-122">Se você criar uma política de usuário, deve aplicá-la a um ou mais usuários antes que ela surta efeito.</span><span class="sxs-lookup"><span data-stu-id="0b334-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="0b334-123">As configurações de política aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="0b334-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="0b334-124">A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência).</span><span class="sxs-lookup"><span data-stu-id="0b334-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="0b334-125">Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="0b334-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="0b334-126">Essas opções incluem os seguintes tipos de acesso externo:</span><span class="sxs-lookup"><span data-stu-id="0b334-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="0b334-127">**Habilitar comunicações com usuários federados**   Habilite esta opção se desejar oferecer suporte para o acesso de usuários a domínios parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="0b334-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="0b334-128">Essa configuração configura a capacidade de os usuários se comunicarem com outros domínios federados SIP, bem como provedores hospedados como o Microsoft 365 ou o Office 365.</span><span class="sxs-lookup"><span data-stu-id="0b334-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365 or Office 365.</span></span> 


  - <span data-ttu-id="0b334-129">**Habilitar comunicações com usuários remotos**   Habilite esta opção se desejar que os usuários da sua organização que estejam fora do firewall, como telecomutadores e usuários que estejam viajando, possam se conectar ao Skype for Business Server pela Internet.</span><span class="sxs-lookup"><span data-stu-id="0b334-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="0b334-130">**Habilitar comunicações com usuários públicos**   Habilite esta opção se desejar que os usuários internos possam se comunicar com os contatos públicos do provedor de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="0b334-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="0b334-131">Além de habilitar o suporte ao acesso de usuário externo, você também deve configurar políticas para controlar o uso do acesso de usuário externo na organização antes de qualquer tipo de acesso de usuário externo estar disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="0b334-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="0b334-132">Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte [Habilitar ou desabilitar o acesso de usuário remoto](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0b334-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="0b334-133">**Para exibir políticas de acesso externo usando os cmdlets do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0b334-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="0b334-134">Você pode exibir políticas de acesso externo usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Get-CsExternalAccessPolicy**.</span><span class="sxs-lookup"><span data-stu-id="0b334-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="0b334-135">Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b334-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="0b334-136">Para exibir informações sobre todas as suas políticas de acesso externo, digite o seguinte comando no Shell de Gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="0b334-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="0b334-137">Esse comando retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="0b334-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
