---
title: Implantar Telefonar via Trabalho no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumo: Saiba como implantar chamada Via trabalho no Skype para Business Server 2015 para alguns ou todos os seus usuários.'
ms.openlocfilehash: 6b4dcb12458fb3421db5b500b550061c24d51bc1
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568246"
---
# <a name="deploy-call-via-work-in-skype-for-business-server-2015"></a><span data-ttu-id="58365-103">Implantar Telefonar via Trabalho no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="58365-103">Deploy Call Via Work in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="58365-104">**Resumo:** Aprenda a implantar chamada Via trabalho no Skype para Business Server 2015 para alguns ou todos os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="58365-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server 2015 for some or all of your users.</span></span>
  
<span data-ttu-id="58365-105">Use estas etapas para implantar a chamada Via trabalho para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="58365-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="58365-106">Considerações de planejamento são abordadas em [Planejar a chamada Via trabalho no Skype para Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="58365-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="58365-107">Nas versões anteriores de chamada remota do Lync Server controle era um recurso que permitia aos usuários controlar seus telefones PBX com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58365-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="58365-108">Skype para Business Server, esse recurso foi substituído com a chamada Via trabalho.</span><span class="sxs-lookup"><span data-stu-id="58365-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="58365-109">Pré-requisitos para chamada Via trabalho</span><span class="sxs-lookup"><span data-stu-id="58365-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="58365-110">Chamada Via trabalho usa Unified Communications Web API (UCWA), que é instalado automaticamente em todos os Skype para Business Server servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="58365-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="58365-111">Para habilitar usuários para chamada Via trabalho, você também deve ter os seguintes pré-requisitos in-loco:</span><span class="sxs-lookup"><span data-stu-id="58365-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="58365-112">Você deve ter um servidor de mediação implantados, ou como parte de um servidor Front-End ou como uma função autônomo.</span><span class="sxs-lookup"><span data-stu-id="58365-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="58365-113">Um gateway IP-PBX também deve ser implantado.</span><span class="sxs-lookup"><span data-stu-id="58365-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="58365-114">Todos os usuários que serão habilitados para chamada Via trabalho devem ter um Direct Inward Dialing (DID) no sistema telefônico PBX.</span><span class="sxs-lookup"><span data-stu-id="58365-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="58365-115">Você deve habilitar todos os usuários de chamada Via trabalho para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="58365-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="58365-116">Quando você fizer isso, você deve configurar o Skype para negócios tenha o número para cada usuário no número DID correspondente para o sistema de telefone PBX correspondente.</span><span class="sxs-lookup"><span data-stu-id="58365-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="58365-117">Todos os usuários que usarão chamada Via trabalho devem ter **A configuração automática** selecionada na opção suas **Conexões avançadas** em seu Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="58365-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="58365-118">Isso permite que o cliente descobrir as URLs do UCWA.</span><span class="sxs-lookup"><span data-stu-id="58365-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="58365-119">**Configuração automática** é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="58365-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="58365-120">Para cada usuário de chamada Via trabalho, habilite o encaminhamento de chamadas e toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="58365-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="58365-121">Para cada usuário de chamada Via trabalho, certifique-se de que a conferência discada e discar conferência estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="58365-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="58365-122">Isso permite que esses usuários obter e sair Skype para conferências de negócios.</span><span class="sxs-lookup"><span data-stu-id="58365-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="58365-123">Certifique-se de que a delegação, chamada de equipe e grupo de resposta estão desabilitados para cada usuário de chamada Via trabalho.</span><span class="sxs-lookup"><span data-stu-id="58365-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="58365-124">Implantar Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="58365-124">Deploy Call Via Work</span></span>

<span data-ttu-id="58365-125">Depois que todos os pré-requisitos forem implantados, execute as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="58365-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="58365-126">Crie um número de telefone global para sua implantação que Skype para negócios exibe na ID de chamador PBX de usuários que estão fazendo chamadas de chamada Via trabalho.</span><span class="sxs-lookup"><span data-stu-id="58365-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="58365-127">Criar uma ou mais políticas de chamada Via trabalho</span><span class="sxs-lookup"><span data-stu-id="58365-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="58365-128">Atribuir uma política de chamada Via trabalho para cada usuário que será habilitado para chamada Via trabalho</span><span class="sxs-lookup"><span data-stu-id="58365-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="58365-129">Criar o número de telefone global Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="58365-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="58365-130">Digite o seguinte cmdlet</span><span class="sxs-lookup"><span data-stu-id="58365-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="58365-131">Por exemplo, o seguinte cmdlet configura o número de telefone global para 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="58365-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="58365-132">Criar uma política Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="58365-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="58365-133">Digite o seguinte cmdlet</span><span class="sxs-lookup"><span data-stu-id="58365-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="58365-134">Por exemplo, o cmdlet a seguir cria uma política de chamada Via trabalho denominada ContosoUser1CvWP requer que o usuário usar um número de retorno de chamada de admin e define esse número de retorno de chamada para 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="58365-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="58365-135">Atribuir uma política de chamada Via trabalho a um usuário</span><span class="sxs-lookup"><span data-stu-id="58365-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="58365-136">Digite o seguinte cmdlet</span><span class="sxs-lookup"><span data-stu-id="58365-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="58365-137">Por exemplo, o cmdlet a seguir atribui a política de chamada Via trabalho "ContosoUser1CvWP" para o usuário chamado **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="58365-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="58365-138">Consulte também</span><span class="sxs-lookup"><span data-stu-id="58365-138">See also</span></span>

[<span data-ttu-id="58365-139">Planejar para chamada Via trabalho no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="58365-139">Plan for Call Via Work in Skype for Business Server 2015</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

