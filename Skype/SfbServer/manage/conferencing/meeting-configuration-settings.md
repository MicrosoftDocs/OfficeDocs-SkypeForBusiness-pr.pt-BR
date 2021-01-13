---
title: Gerenciar definições de configuração de reunião no Skype for Business Server
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumo: Saiba como gerenciar as definições de configuração de reunião no Skype for Business Server.'
ms.openlocfilehash: c34723219839061e36b2684dff81efd5cd914843
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828081"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="5b267-103">Gerenciar definições de configuração de reunião no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5b267-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="5b267-104">**Resumo:** Saiba como gerenciar as definições de configuração de reunião no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b267-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="5b267-105">Este tópico descreve como gerenciar as definições de configuração de reunião.</span><span class="sxs-lookup"><span data-stu-id="5b267-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="5b267-106">Para obter mais informações sobre como planejar e implantar conferências, consulte [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="5b267-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="5b267-107">As definições de configuração de reunião ditam o tipo de reuniões que os usuários podem criar, além de controlar como (ou até mesmo se) usuários anônimos e usuários de conferência discada podem participar dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="5b267-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="5b267-108">Observe que essas configurações afetam apenas reuniões agendadas; elas não afetam as reuniões ad-hoc criadas clicando na opção Reunir Agora no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="5b267-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="5b267-109">As definições de configuração de reunião definem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5b267-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="5b267-110">Se os usuários que estão discando da rede pública (PSTN) vão para o lobby</span><span class="sxs-lookup"><span data-stu-id="5b267-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="5b267-111">Quem pode ser um apresentador</span><span class="sxs-lookup"><span data-stu-id="5b267-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="5b267-112">Se o tipo de conferência é atribuído por padrão</span><span class="sxs-lookup"><span data-stu-id="5b267-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="5b267-113">Se os usuários anônimos (não autenticados) são admitidos por padrão</span><span class="sxs-lookup"><span data-stu-id="5b267-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="5b267-114">Você pode definir as características das reuniões usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b267-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="5b267-115">Você pode especificar as configurações de reunião no nível global (criado por padrão), no nível do site ou no nível do pool.</span><span class="sxs-lookup"><span data-stu-id="5b267-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="5b267-116">Por padrão, as configurações globais definem a experiência da reunião.</span><span class="sxs-lookup"><span data-stu-id="5b267-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="5b267-117">Se você criar configurações a nível de pool, elas se aplicarão a todas as reuniões hospedadas pelo pool.</span><span class="sxs-lookup"><span data-stu-id="5b267-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="5b267-118">Se você não criar configurações a nível de pool, as configurações a nível local serão aplicadas, caso existam.</span><span class="sxs-lookup"><span data-stu-id="5b267-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="5b267-119">Se você não definir as configurações a nível local, as configurações globais serão aplicadas a todas as reuniões.</span><span class="sxs-lookup"><span data-stu-id="5b267-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5b267-120">Gerenciar configurações de reunião usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5b267-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="5b267-121">Para gerenciar configurações de reunião usando o Painel de Controle do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="5b267-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="5b267-122">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5b267-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="5b267-123">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b267-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5b267-124">Na barra de navegação esquerda, clique **em Conferência e** em Configuração de **Reunião.**</span><span class="sxs-lookup"><span data-stu-id="5b267-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5b267-125">Gerenciar configurações de reunião usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5b267-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5b267-126">Para gerenciar reuniões usando o Shell de Gerenciamento do Skype for Business Server, use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5b267-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="5b267-127">**Definições de configuração de reunião**</span><span class="sxs-lookup"><span data-stu-id="5b267-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="5b267-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="5b267-128">**Cmdlet**</span></span>|<span data-ttu-id="5b267-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5b267-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5b267-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="5b267-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="5b267-131">Retorna informações sobre as definições de configuração de reunião em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="5b267-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="5b267-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="5b267-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="5b267-133">Cria um novo conjunto de configurações de reunião em escopo do local ou serviço.</span><span class="sxs-lookup"><span data-stu-id="5b267-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="5b267-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="5b267-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="5b267-135">Exclui um conjunto existente de definições de configuração de reunião.</span><span class="sxs-lookup"><span data-stu-id="5b267-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="5b267-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="5b267-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="5b267-137">Modifica as definições de configuração de reunião em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="5b267-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

