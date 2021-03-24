---
title: Atribuir uma política de roteamento de voz
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Resumo: leia este tópico para saber como atribuir uma política de voz para usuários que usam o Sistema de Telefonia com conectividade PSTN local.'
ms.openlocfilehash: 43e2b560cc0886bacd6faaec6c113ee1f237eff7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092959"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="44d8e-103">Atribuir uma política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="44d8e-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="44d8e-104">O Skype for Business Online será retirado em 31 de julho de 2021 após o qual o serviço não estará mais acessível.</span><span class="sxs-lookup"><span data-stu-id="44d8e-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="44d8e-105">Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá mais suporte.</span><span class="sxs-lookup"><span data-stu-id="44d8e-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="44d8e-106">Saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto](/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="44d8e-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="44d8e-107">**Resumo:** Leia este tópico para saber como atribuir uma política de voz para usuários que usam o Sistema de Telefonia com conectividade PSTN local.</span><span class="sxs-lookup"><span data-stu-id="44d8e-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="44d8e-108">Quando um usuário está no Skype for Business Online e usa o Sistema de Telefonia com conectividade PSTN local, duas políticas de voz serão aplicadas a eles.</span><span class="sxs-lookup"><span data-stu-id="44d8e-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="44d8e-109">Um deles é uma política de roteamento de voz local que você atribuirá no local.</span><span class="sxs-lookup"><span data-stu-id="44d8e-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="44d8e-110">Essa política pode ser global ou específica do usuário e define quais registros de uso PSTN estão associados ao usuário.</span><span class="sxs-lookup"><span data-stu-id="44d8e-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="44d8e-111">Este tópico explica como atribuir essa política.</span><span class="sxs-lookup"><span data-stu-id="44d8e-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="44d8e-112">A outra política de voz define quais recursos de chamada estão disponíveis para o usuário; essa política de voz é definida pela Microsoft e é idêntica para todos os sistemas de telefonia com usuários de conectividade PSTN locais.</span><span class="sxs-lookup"><span data-stu-id="44d8e-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="44d8e-113">Ele é atribuído automaticamente aos usuários do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="44d8e-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="44d8e-114">**Usuário local**</span><span class="sxs-lookup"><span data-stu-id="44d8e-114">**On-premises user**</span></span>|<span data-ttu-id="44d8e-115">**Sistema de Telefonia com usuário de conectividade PSTN local**</span><span class="sxs-lookup"><span data-stu-id="44d8e-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44d8e-116">Recursos de chamada definidos em</span><span class="sxs-lookup"><span data-stu-id="44d8e-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="44d8e-117">Política de voz</span><span class="sxs-lookup"><span data-stu-id="44d8e-117">Voice policy</span></span>  <br/> |<span data-ttu-id="44d8e-118">Política de voz pré-definida, atribuída automaticamente quando o usuário é licenciado para o Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="44d8e-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="44d8e-119">Registros de uso de PSTN associados</span><span class="sxs-lookup"><span data-stu-id="44d8e-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="44d8e-120">Política de voz</span><span class="sxs-lookup"><span data-stu-id="44d8e-120">Voice policy</span></span>  <br/> |<span data-ttu-id="44d8e-121">Política de roteamento de voz, atribuída enquanto o usuário ainda está no local.</span><span class="sxs-lookup"><span data-stu-id="44d8e-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="44d8e-122">Execute as etapas a seguir usando sua implantação local, enquanto o usuário ainda está na implantação local.</span><span class="sxs-lookup"><span data-stu-id="44d8e-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="44d8e-123">Usando uma política de roteamento de voz global</span><span class="sxs-lookup"><span data-stu-id="44d8e-123">Using a global voice routing policy</span></span>

<span data-ttu-id="44d8e-124">Antes de usar uma política de roteamento de voz global para seu Sistema de Telefonia com usuários de conectividade PSTN locais, você deve adicionar registros de uso PSTN à política.</span><span class="sxs-lookup"><span data-stu-id="44d8e-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="44d8e-125">Para atribuir registros de uso PSTN à política de roteamento de voz global</span><span class="sxs-lookup"><span data-stu-id="44d8e-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="44d8e-126">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="44d8e-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="44d8e-127">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="44d8e-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="44d8e-128">Adicione os registros de uso PSTN à política:</span><span class="sxs-lookup"><span data-stu-id="44d8e-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="44d8e-129">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="44d8e-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="44d8e-130">Criando uma nova política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="44d8e-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="44d8e-131">Para criar uma nova política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="44d8e-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="44d8e-132">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="44d8e-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="44d8e-133">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="44d8e-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="44d8e-134">Crie uma nova política de roteamento de voz:</span><span class="sxs-lookup"><span data-stu-id="44d8e-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="44d8e-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="44d8e-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="44d8e-136">Este exemplo cria uma nova política de roteamento de voz chamada HybridVoice, que tem dois usos PSTN associados a ela.</span><span class="sxs-lookup"><span data-stu-id="44d8e-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="44d8e-137">Atribuir uma política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="44d8e-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="44d8e-138">Não importa se você usa a política de roteamento de voz global ou as específicas do usuário, use as etapas a seguir para atribuir a política a um usuário.</span><span class="sxs-lookup"><span data-stu-id="44d8e-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="44d8e-139">Para atribuir a política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="44d8e-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="44d8e-140">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="44d8e-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="44d8e-141">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="44d8e-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="44d8e-142">Atribua uma política de voz existente a um usuário:</span><span class="sxs-lookup"><span data-stu-id="44d8e-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="44d8e-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="44d8e-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="44d8e-144">Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído à política de voz criada anteriormente com o nome HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="44d8e-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="44d8e-145">Para obter mais detalhes sobre políticas de roteamento de voz, consulte Create or modify a voice policy and [configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="44d8e-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
