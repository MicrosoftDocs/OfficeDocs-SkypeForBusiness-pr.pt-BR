---
title: Implantar chamada por meio do trabalho no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumo: saiba como implantar a chamada por meio do trabalho no Skype for Business Server para alguns ou todos os seus usuários.'
ms.openlocfilehash: d989c05b6b2b3e01a3a96e66133ec314029329e1
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002701"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="64335-103">Implantar chamada por meio do trabalho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="64335-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="64335-104">**Resumo:** Saiba como implantar a chamada por meio do trabalho no Skype for Business Server para alguns ou todos os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="64335-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="64335-105">Use estas etapas para implantar a chamada por meio do trabalho para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="64335-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="64335-106">As considerações de planejamento são discutidas no [plano de chamada por meio do trabalho no Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="64335-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="64335-107">Em versões anteriores do controle de chamada remota do Lync Server era um recurso que permitia aos usuários controlar os telefones PBX com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64335-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="64335-108">No Skype for Business Server, este recurso foi substituído por meio da chamada por meio do trabalho.</span><span class="sxs-lookup"><span data-stu-id="64335-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="64335-109">Pré-requisitos para ligar pelo trabalho</span><span class="sxs-lookup"><span data-stu-id="64335-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="64335-110">A chamada via trabalho usa a API da Web de comunicação unificada (UCWA), que é instalada automaticamente em todos os servidores de front-end do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="64335-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="64335-111">Para permitir que os usuários liguem por meio do trabalho, você também deve ter os seguintes pré-requisitos em vigor:</span><span class="sxs-lookup"><span data-stu-id="64335-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="64335-112">Você deve ter um servidor de mediação implantado, seja como parte de um servidor front-end ou como uma função autônoma.</span><span class="sxs-lookup"><span data-stu-id="64335-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="64335-113">Um gateway IP-PBX também deve ser implantado.</span><span class="sxs-lookup"><span data-stu-id="64335-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="64335-114">Todos os usuários que serão habilitados para a chamada por meio do trabalho deverão ter uma discagem direta (DID) no sistema de telefonia PBX.</span><span class="sxs-lookup"><span data-stu-id="64335-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="64335-115">Você deve habilitar toda a chamada por meio de usuários de trabalho do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="64335-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="64335-116">Ao fazer isso, você deve configurar o Skype for Business para que cada usuário tenha o número DID correspondente para o sistema telefônico PBX correspondente.</span><span class="sxs-lookup"><span data-stu-id="64335-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="64335-117">Todos os usuários que usarão a chamada por meio do trabalho deverão ter a **configuração automática** selecionada na opção **conexões avançadas** no cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="64335-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="64335-118">Isso permite que o cliente descubra as URLs do UCWA.</span><span class="sxs-lookup"><span data-stu-id="64335-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="64335-119">**Configuração automática** é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="64335-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="64335-120">Para cada chamada por usuário de trabalho, ative o encaminhamento de chamadas e o toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="64335-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="64335-121">Para cada chamada por usuário do trabalho, verifique se a conferência discada e a conferência discada está habilitada.</span><span class="sxs-lookup"><span data-stu-id="64335-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="64335-122">Isso permite que esses usuários entrem e entrem em conferências do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="64335-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="64335-123">Verifique se a delegação, a chamada de equipe e o grupo de resposta estão desabilitados para cada chamada por meio de um usuário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="64335-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="64335-124">Implantar Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="64335-124">Deploy Call Via Work</span></span>

<span data-ttu-id="64335-125">Depois que todos os pré-requisitos forem implantados, execute as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="64335-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="64335-126">Crie um número de telefone global para sua implantação do qual o Skype for Business é exibido na identificação de chamadas do PBX de usuários que estão chamando via chamadas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="64335-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="64335-127">Criar uma ou mais chamadas via políticas de trabalho</span><span class="sxs-lookup"><span data-stu-id="64335-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="64335-128">Atribuir uma chamada via política de trabalho a cada usuário que será habilitado para fazer uma chamada via trabalho</span><span class="sxs-lookup"><span data-stu-id="64335-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="64335-129">Criar o número de telefone global Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="64335-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="64335-130">Digite o seguinte cmdlet</span><span class="sxs-lookup"><span data-stu-id="64335-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="64335-131">Por exemplo, o seguinte cmdlet configura o número de telefone global para 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="64335-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="64335-132">Criar uma política Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="64335-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="64335-133">Digite o seguinte cmdlet</span><span class="sxs-lookup"><span data-stu-id="64335-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="64335-134">Por exemplo, o cmdlet a seguir cria uma chamada via política de trabalho chamada ContosoUser1CvWP, requer que o usuário use um número de retorno de chamada de administrador e define esse número de retorno de chamada para 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="64335-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="64335-135">Atribuir uma chamada via política de trabalho a um usuário</span><span class="sxs-lookup"><span data-stu-id="64335-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="64335-136">Digite o seguinte cmdlet</span><span class="sxs-lookup"><span data-stu-id="64335-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="64335-137">Por exemplo, o cmdlet a seguir atribui a chamada via política de trabalho "ContosoUser1CvWP" ao usuário chamado **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="64335-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="64335-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="64335-138">See also</span></span>

[<span data-ttu-id="64335-139">Planejar a chamada por meio do trabalho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="64335-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

