---
title: Atribuir uma Política de Roteamento de Voz
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Resumo: Leia este tópico para saber como atribuir uma política de voz para os usuários que usam o sistema telefônico no Office 365 com uma conectividade PSTN local.'
ms.openlocfilehash: 43d8939e6e0cd49f66234e127f05cb421700a15a
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569495"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="8d2b1-103">Atribuir uma Política de Roteamento de Voz</span><span class="sxs-lookup"><span data-stu-id="8d2b1-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="8d2b1-104">**Resumo:** Leia este tópico para saber como atribuir uma política de voz para os usuários que usam o sistema telefônico no Office 365 com uma conectividade PSTN local.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="8d2b1-105">Depois que um usuário estiver ligado Skype para Business Online e usando o sistema telefônico no Office 365 com conectividade PSTN de local, duas políticas de voz serão aplicadas a eles.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="8d2b1-106">Um é uma política de roteamento de voz de local que você irá atribuir no local.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="8d2b1-107">Essa diretiva pode ser global ou específico do usuário e define a quais registros de uso PSTN associados ao usuário.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="8d2b1-108">Este tópico explica como atribuir esta política.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="8d2b1-109">Política de voz define quais recursos de chamada estão disponíveis para o usuário; Essa política de voz é definida pela Microsoft e é idêntica para todos os sistema telefônico no Office 365 com usuários de conectividade PSTN local.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="8d2b1-110">Ele é automaticamente atribuído para o sistema telefônico em usuários do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="8d2b1-111">**Usuário local**</span><span class="sxs-lookup"><span data-stu-id="8d2b1-111">**On-premises user**</span></span>|<span data-ttu-id="8d2b1-112">**Sistema telefônico no Office 365 com o usuário de conectividade PSTN local**</span><span class="sxs-lookup"><span data-stu-id="8d2b1-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8d2b1-113">Recursos de chamada definidos na</span><span class="sxs-lookup"><span data-stu-id="8d2b1-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="8d2b1-114">Política de voz</span><span class="sxs-lookup"><span data-stu-id="8d2b1-114">Voice policy</span></span>  <br/> |<span data-ttu-id="8d2b1-115">Pré-definidas política de voz, atribuída automaticamente quando o usuário estiver licenciado para o sistema telefônico no Office 365.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="8d2b1-116">Registros de uso de PSTN associados a</span><span class="sxs-lookup"><span data-stu-id="8d2b1-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="8d2b1-117">Política de voz</span><span class="sxs-lookup"><span data-stu-id="8d2b1-117">Voice policy</span></span>  <br/> |<span data-ttu-id="8d2b1-118">Política de roteamento de voz, atribuída enquanto o usuário ainda está hospedado no local.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="8d2b1-119">Você execute as seguintes etapas usando sua implantação no local, enquanto o usuário ainda é hospedado na implantação no local.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="8d2b1-120">Usar uma política de roteamento de voz global</span><span class="sxs-lookup"><span data-stu-id="8d2b1-120">Using a global voice routing policy</span></span>

<span data-ttu-id="8d2b1-121">Antes de usar uma política de roteamento de voz global para seu sistema telefônico no Office 365 com usuários de conectividade PSTN local, você deve adicionar registros de uso PSTN à política.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="8d2b1-122">Atribuir registros de uso de PSTN à política de roteamento de voz global</span><span class="sxs-lookup"><span data-stu-id="8d2b1-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="8d2b1-123">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8d2b1-124">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8d2b1-125">Adicione os registros de uso PSTN à política:</span><span class="sxs-lookup"><span data-stu-id="8d2b1-125">Add the PSTN usage records to the policy:</span></span>
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
  ```

    <span data-ttu-id="8d2b1-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8d2b1-126">For example:</span></span>
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
  ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="8d2b1-127">Crie uma nova política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="8d2b1-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="8d2b1-128">Criar uma nova política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="8d2b1-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="8d2b1-129">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8d2b1-130">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8d2b1-131">Crie uma nova política de roteamento de voz:</span><span class="sxs-lookup"><span data-stu-id="8d2b1-131">Create a new voice routing policy:</span></span>
    
  ```
  New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
  ```

    <span data-ttu-id="8d2b1-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8d2b1-132">For example:</span></span>
    
  ```
  New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
  ```

<span data-ttu-id="8d2b1-133">Esse exemplo cria uma nova política de roteamento de voz, chamada HybridVoice, com dois usos de PSTN associados a ela.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="8d2b1-134">Atribuir uma política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="8d2b1-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="8d2b1-135">Para política de roteamento de voz global ou específica do usuário, use as etapas a seguir para atribuir a política a um usuário.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="8d2b1-136">Atribuir a política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="8d2b1-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="8d2b1-137">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8d2b1-138">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8d2b1-139">Atribua uma política de voz existente a um usuário:</span><span class="sxs-lookup"><span data-stu-id="8d2b1-139">Assign an existing voice policy to a user:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
  ```

    <span data-ttu-id="8d2b1-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8d2b1-140">For example:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
  ```

<span data-ttu-id="8d2b1-141">Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído à política de voz criada anteriormente com o nome HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="8d2b1-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="8d2b1-142">Para obter mais detalhes sobre as políticas de roteamento de voz, consulte [criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype para negócios 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8d2b1-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

