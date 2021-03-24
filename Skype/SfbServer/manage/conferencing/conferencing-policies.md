---
title: Gerenciar políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Resumo: Saiba como gerenciar políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 39855aac09b88852d0931c9b8fbdb8e2e9187c71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099097"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="40eb0-103">Gerenciar políticas de conferência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40eb0-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="40eb0-104">**Resumo:** Saiba como gerenciar políticas de conferência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="40eb0-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="40eb0-105">Este tópico descreve como gerenciar políticas de conferência.</span><span class="sxs-lookup"><span data-stu-id="40eb0-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="40eb0-106">Para obter mais informações sobre como planejar e implantar a conferência, consulte [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="40eb0-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="40eb0-107">As políticas de conferência permitem definir uma ampla variedade de opções de agendamento e participação, desde se uma reunião pode incluir áudio IP e vídeo até o número máximo de pessoas que podem participar.</span><span class="sxs-lookup"><span data-stu-id="40eb0-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="40eb0-108">Você pode usar políticas de conferência para gerenciar a segurança, largura de banda e aspectos legais das reuniões.</span><span class="sxs-lookup"><span data-stu-id="40eb0-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="40eb0-109">Você pode definir a política de conferência em três níveis: escopo global, escopo de site e escopo de usuário.</span><span class="sxs-lookup"><span data-stu-id="40eb0-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="40eb0-110">As configurações se aplicam a um usuário específico desde o menor escopo até o maior.</span><span class="sxs-lookup"><span data-stu-id="40eb0-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="40eb0-111">Se você atribuir uma política a um usuário, essas configurações têm precedência.</span><span class="sxs-lookup"><span data-stu-id="40eb0-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="40eb0-112">Caso você não atribua uma política de usuário, aplicam-se as definições de site.</span><span class="sxs-lookup"><span data-stu-id="40eb0-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="40eb0-113">Caso políticas de usuários ou de site não sejam aplicáveis, a política global fornece as definições padrão.</span><span class="sxs-lookup"><span data-stu-id="40eb0-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="40eb0-p104">Há uma política global por padrão, portanto você não pode criar uma nova política global. Você também não pode deletar a política global existente, mas pode alterar a política global existente para personalizar suas configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="40eb0-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="40eb0-116">Gerenciar políticas de conferência usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40eb0-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="40eb0-117">Para gerenciar políticas de conferência usando o Painel de Controle do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="40eb0-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="40eb0-118">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="40eb0-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="40eb0-119">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="40eb0-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="40eb0-120">Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**</span><span class="sxs-lookup"><span data-stu-id="40eb0-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="40eb0-121">Gerenciar políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40eb0-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="40eb0-122">Para gerenciar reuniões usando o Shell de Gerenciamento do Skype for Business Server, use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="40eb0-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="40eb0-123">**Configurações de política de conferência**</span><span class="sxs-lookup"><span data-stu-id="40eb0-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="40eb0-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="40eb0-124">**Cmdlet**</span></span>|<span data-ttu-id="40eb0-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="40eb0-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="40eb0-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="40eb0-126">Get-CsConferencingPolicy</span></span>](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="40eb0-127">Retorna informações sobre as diretivas de conferência que tenham sido configuradas para uso na organização.</span><span class="sxs-lookup"><span data-stu-id="40eb0-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="40eb0-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="40eb0-128">Grant-CsConferencingPolicy</span></span>](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="40eb0-129">Atribui uma diretiva de conferência em escopo por usuário.</span><span class="sxs-lookup"><span data-stu-id="40eb0-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="40eb0-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="40eb0-130">New-CsConferencingPolicy</span></span>](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="40eb0-131">Cria uma nova política de conferência para uso na organização.</span><span class="sxs-lookup"><span data-stu-id="40eb0-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="40eb0-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="40eb0-132">Remove-CsConferencingPolicy</span></span>](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="40eb0-133">Remove a diretiva de conferência especificada.</span><span class="sxs-lookup"><span data-stu-id="40eb0-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="40eb0-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="40eb0-134">Set-CsConferencingPolicy</span></span>](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="40eb0-135">Modifica uma diretiva de conferência existente.</span><span class="sxs-lookup"><span data-stu-id="40eb0-135">Modifies an existing conferencing policy.</span></span>  <br/> |
