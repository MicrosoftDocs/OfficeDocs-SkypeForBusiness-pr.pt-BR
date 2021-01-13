---
title: Implantar Telefonar via Trabalho no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumo: saiba como implantar o Telefonar via Trabalho no Skype for Business Server para alguns ou todos os seus usuários.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825001"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="fb8dd-103">Implantar Telefonar via Trabalho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb8dd-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="fb8dd-104">**Resumo:** Saiba como implantar o Telefonar via Trabalho no Skype for Business Server para alguns ou todos os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="fb8dd-105">Use estas etapas para implantar o Telefonar via Trabalho para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="fb8dd-106">Considerações de planejamento são discutidas no [Plano para Telefonar via Trabalho no Skype for Business Server.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)</span><span class="sxs-lookup"><span data-stu-id="fb8dd-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="fb8dd-107">Em versões anteriores do Lync Server, o controle de chamada remota era um recurso que permitia que os usuários controlas seus telefones PBX com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="fb8dd-108">No Skype for Business Server, esse recurso foi substituído pelo Telefonar via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="fb8dd-109">Pré-requisitos para Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="fb8dd-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="fb8dd-110">O Telefonar via Trabalho usa o Unified Communications Web API (UCWA), que é instalado automaticamente em todos os Servidores Front-End do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="fb8dd-111">Para habilitar os usuários para Telefonar via Trabalho, você também deve ter os seguintes pré-requisitos no local:</span><span class="sxs-lookup"><span data-stu-id="fb8dd-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="fb8dd-112">Você deve ter um Servidor de Mediação implantado, como parte de um Servidor Front-End ou como uma função autônoma.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="fb8dd-113">Você também deve implantar um gateway IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="fb8dd-114">Todos os usuários que serão habilitados para Telefonar via Trabalho devem ter um DID (Discagem Direta interna) no sistema de telefonia PBX.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="fb8dd-115">Você deve habilitar todos os usuários telefonar via trabalho para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="fb8dd-116">Ao fazer isso, você deve configurar o número DID do Skype for Business para cada usuário para o número DID correspondente para o sistema de telefonia PBX correspondente.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="fb8dd-117">Todos os usuários que usarão  o Telefonar via Trabalho devem ter a Configuração Automática selecionada na opção **Conexões** Avançadas no cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="fb8dd-118">Isso permite que o cliente descubra as URLs do UCWA.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="fb8dd-119">**A Configuração** Automática é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="fb8dd-120">Para cada usuário do Telefonar via Trabalho, habilita o encaminhamento de chamada e o toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="fb8dd-121">Para cada usuário da Chamada via Trabalho, verifique se a conferência discada e a discagem estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="fb8dd-122">Isso permite que esses usuários entre e saim de conferências do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="fb8dd-123">Verifique se a delegação, a chamada de equipe e o grupo de resposta estão desabilitados para cada usuário do Telefonar via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="fb8dd-124">Implantar Chamada via Trabalho</span><span class="sxs-lookup"><span data-stu-id="fb8dd-124">Deploy Call Via Work</span></span>

<span data-ttu-id="fb8dd-125">Após os pré-requisitos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb8dd-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="fb8dd-126">Crie um número de telefone global para sua implantação que o Skype for Business exibe na ID de chamadas PBX dos usuários que estão fazendo chamadas Telefonar via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="fb8dd-127">Criar uma ou mais políticas telefonar via trabalho</span><span class="sxs-lookup"><span data-stu-id="fb8dd-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="fb8dd-128">Atribuir uma política telefonar via trabalho a cada usuário que será habilitado para Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="fb8dd-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="fb8dd-129">Criar o número de telefone global Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="fb8dd-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="fb8dd-130">Digite o cmdlet a seguir</span><span class="sxs-lookup"><span data-stu-id="fb8dd-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="fb8dd-131">Por exemplo, o cmdlet a seguir define o número de telefone global como 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="fb8dd-132">Criar uma política telefonar via trabalho</span><span class="sxs-lookup"><span data-stu-id="fb8dd-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="fb8dd-133">Digite o cmdlet a seguir</span><span class="sxs-lookup"><span data-stu-id="fb8dd-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="fb8dd-134">Por exemplo, o cmdlet a seguir cria uma política Telefonar via Trabalho chamada ContosoUser1CvWP, exige que o usuário use um número de retorno de chamada de administrador e define esse número de retorno de chamada como 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="fb8dd-135">Atribuir uma política telefonar via trabalho a um usuário</span><span class="sxs-lookup"><span data-stu-id="fb8dd-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="fb8dd-136">Digite o cmdlet a seguir</span><span class="sxs-lookup"><span data-stu-id="fb8dd-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="fb8dd-137">Por exemplo, o cmdlet a seguir atribui a política Telefonar via Trabalho "ContosoUser1CvWP" ao usuário chamado **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="fb8dd-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="fb8dd-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="fb8dd-138">See also</span></span>

[<span data-ttu-id="fb8dd-139">Planejar o Telefonar via Trabalho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb8dd-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

