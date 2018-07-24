---
title: Gerenciar políticas de conferência do Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Resumo: Saiba como gerenciar políticas de conferência do Skype para Business Server.'
ms.openlocfilehash: d5fed0c6615747069d71015fca33144ca41dd64b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986654"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="d43b3-103">Gerenciar políticas de conferência do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d43b3-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="d43b3-104">**Resumo:** Saiba como gerenciar políticas de conferência do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d43b3-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="d43b3-105">Este tópico descreve como gerenciar as políticas de conferência.</span><span class="sxs-lookup"><span data-stu-id="d43b3-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="d43b3-106">Para obter mais informações sobre como planejar e implantar a conferência, consulte [Plan para conferências no Skype para Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferência no Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="d43b3-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="d43b3-p102">As políticas de conferência permitem definir uma grande variedade de opções de agendamento e participação, desde se uma reunião pode incluir vídeo e áudio IP até o número máximo de pessoas que podem participar da reunião. Você pode usar políticas de conferência para gerenciar os aspectos legais, de segurança e de banda larga de reuniões.</span><span class="sxs-lookup"><span data-stu-id="d43b3-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="d43b3-p103">Você pode definir a política de conferência em três níveis: escopo global, escopo de site e escopo de usuário. As configurações se aplicam a um usuário específico desde o menor escopo até o maior. Caso você atribua uma política a um usuário, estas configurações tem precedência. Caso você não atribua uma política de usuário, aplicam-se as definições de site. Caso políticas de usuários ou de site não sejam aplicáveis, a política global fornece as definições padrão.</span><span class="sxs-lookup"><span data-stu-id="d43b3-p103">You can define conferencing policy on three levels: global scope, site scope, and user scope. Settings apply to a specific user from the narrowest scope to the widest scope. If you assign a policy to a user, those settings take precedence. If you do not assign a user policy, site settings apply. If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="d43b3-p104">Há uma política global por padrão, portanto você não pode criar uma nova política global. Você também não pode excluir a política global existente, mas pode alterar a política global existente para personalizar suas configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="d43b3-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d43b3-116">Gerenciar políticas de conferência usando o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="d43b3-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="d43b3-117">Para gerenciar diretivas de conferência usando Skype para o painel de controle do Business Server:</span><span class="sxs-lookup"><span data-stu-id="d43b3-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="d43b3-118">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d43b3-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d43b3-119">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="d43b3-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d43b3-120">Na barra de navegação esquerda, clique em **Conferência** e, então, clique em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="d43b3-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d43b3-121">Gerenciar políticas de conferência usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="d43b3-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d43b3-122">Para gerenciar reuniões usando Skype do Shell de gerenciamento do servidor de negócios, use os cmdlets a seguir:</span><span class="sxs-lookup"><span data-stu-id="d43b3-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="d43b3-123">**Configurações de política de conferência**</span><span class="sxs-lookup"><span data-stu-id="d43b3-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="d43b3-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="d43b3-124">**Cmdlet**</span></span>|<span data-ttu-id="d43b3-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d43b3-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d43b3-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="d43b3-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="d43b3-127">Retorna informações sobre as diretivas de conferência que tenham sido configuradas para uso na organização.</span><span class="sxs-lookup"><span data-stu-id="d43b3-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="d43b3-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="d43b3-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="d43b3-129">Atribui uma diretiva de conferência em escopo por usuário.</span><span class="sxs-lookup"><span data-stu-id="d43b3-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="d43b3-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="d43b3-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="d43b3-131">Cria uma nova política de conferência para uso na organização.</span><span class="sxs-lookup"><span data-stu-id="d43b3-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="d43b3-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="d43b3-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="d43b3-133">Remove a diretiva de conferência especificada.</span><span class="sxs-lookup"><span data-stu-id="d43b3-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="d43b3-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="d43b3-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="d43b3-135">Modifica uma diretiva de conferência existente.</span><span class="sxs-lookup"><span data-stu-id="d43b3-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

