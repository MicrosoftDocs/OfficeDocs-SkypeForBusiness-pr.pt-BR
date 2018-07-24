---
title: Gerenciar configurações de reunião no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumo: Aprenda a gerenciar configurações de reunião no Skype para Business Server.'
ms.openlocfilehash: 28f0dc37579f762b8ae3b0ac8ac58440c6ce5e24
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966063"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="3a635-103">Gerenciar configurações de reunião no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3a635-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="3a635-104">**Resumo:** Saiba como gerenciar configurações de reunião no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a635-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="3a635-105">Este tópico descreve como gerenciar as definições das configurações de reunião.</span><span class="sxs-lookup"><span data-stu-id="3a635-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="3a635-106">Para obter mais informações sobre como planejar e implantar a conferência, consulte [Plan para conferências no Skype para Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferência no Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="3a635-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="3a635-107">As definições das configurações de reunião informam o tipo de reuniões que os usuários podem criar, além de controlar como (ou até se) usuários anônimos e usuários de conferência discada podem participar dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="3a635-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="3a635-108">Observe que essas configurações só afetam reuniões programadas; eles não afetam as reuniões ad hoc criados clicando-se a opção reunir agora Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="3a635-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="3a635-109">As definições das configurações de reunião definem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3a635-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="3a635-110">Se os usuários discando de uma rede telefônica pública comutada (PSTN) vão para o lobby</span><span class="sxs-lookup"><span data-stu-id="3a635-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="3a635-111">Quem pode ser um apresentador</span><span class="sxs-lookup"><span data-stu-id="3a635-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="3a635-112">Se o tipo de conferência é atribuído por padrão</span><span class="sxs-lookup"><span data-stu-id="3a635-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="3a635-113">Se usuários anônimos (não autenticados) são admitidos por padrão</span><span class="sxs-lookup"><span data-stu-id="3a635-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="3a635-114">Você pode definir as características de reuniões usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3a635-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="3a635-115">Você pode especificar configurações no nível global (criada por padrão) da reunião, nível de site ou nível de pool.</span><span class="sxs-lookup"><span data-stu-id="3a635-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="3a635-116">Por padrão, as configurações globais definem a experiência de reunião.</span><span class="sxs-lookup"><span data-stu-id="3a635-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="3a635-117">Se você criar configurações no nível de pool, elas serão aplicadas a todas as reuniões hospedadas pelo pool.</span><span class="sxs-lookup"><span data-stu-id="3a635-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="3a635-118">Se você não criar configurações no nível de pool, as configurações do nível local serão aplicadas, caso existam.</span><span class="sxs-lookup"><span data-stu-id="3a635-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="3a635-119">Se você não definir as configurações de nível local, as configurações globais serão aplicadas a todas as reuniões.</span><span class="sxs-lookup"><span data-stu-id="3a635-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3a635-120">Gerenciar configurações de reunião usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="3a635-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="3a635-121">Para gerenciar configurações de reunião usando o Skype para o painel de controle do Business Server:</span><span class="sxs-lookup"><span data-stu-id="3a635-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="3a635-122">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3a635-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="3a635-123">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3a635-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3a635-124">Na barra de navegação à esquerda, clique em **Conferência**e em **Configuração da reunião**.</span><span class="sxs-lookup"><span data-stu-id="3a635-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3a635-125">Gerenciar configurações de reunião usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="3a635-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3a635-126">Para gerenciar reuniões usando Skype do Shell de gerenciamento do servidor de negócios, use os cmdlets a seguir:</span><span class="sxs-lookup"><span data-stu-id="3a635-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="3a635-127">**Definições de configuração de reunião**</span><span class="sxs-lookup"><span data-stu-id="3a635-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="3a635-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="3a635-128">**Cmdlet**</span></span>|<span data-ttu-id="3a635-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3a635-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3a635-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a635-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="3a635-131">Retorna informações sobre as definições de configuração de reunião em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="3a635-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="3a635-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a635-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="3a635-133">Cria uma nova coleção de configurações de reunião em escopo do site ou serviço.</span><span class="sxs-lookup"><span data-stu-id="3a635-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="3a635-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a635-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="3a635-135">Exclui um conjunto existente de configurações de reunião.</span><span class="sxs-lookup"><span data-stu-id="3a635-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="3a635-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a635-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="3a635-137">Modifica as definições de configuração de reunião em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="3a635-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

