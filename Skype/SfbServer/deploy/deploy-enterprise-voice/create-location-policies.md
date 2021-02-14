---
title: Criar políticas de local no Skype for Business Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Leia este tópico para saber como configurar as políticas de local do serviço de emergência aprimorado (E9-1-1) no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 4230d6ac1a820cb9612d58b21a2e5b6ae36d8f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822541"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="745ac-103">Criar políticas de local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="745ac-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="745ac-104">Leia este tópico para saber como configurar as políticas de local do serviço de emergência aprimorado (E9-1-1) no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="745ac-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="745ac-105">O Skype for Business Server usa uma política de local para habilitar clientes do Skype for Business para E9-1-1 durante o registro do cliente.</span><span class="sxs-lookup"><span data-stu-id="745ac-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="745ac-106">Uma política de localização contém as configurações que definem como o E9-1-1 será implementado.</span><span class="sxs-lookup"><span data-stu-id="745ac-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="745ac-107">Para obter mais informações, [consulte Planejar políticas de local para o Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="745ac-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="745ac-108">Defina as políticas de local usando o Painel de Controle do Skype for Business ou o cmdlet [New-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="745ac-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="745ac-109">O Skype for Business Server agora dá suporte à configuração de vários números de emergência para um cliente.</span><span class="sxs-lookup"><span data-stu-id="745ac-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="745ac-110">Se você quiser configurar vários números de emergência, siga as informações no Plano para vários números de emergência no [Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) e configure vários números de emergência no Skype for [Business.](configure-multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="745ac-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="745ac-p103">É possível editar a política de localização global e criar novas políticas de localização sinalizadas. Um cliente obtém uma política global quando não está localizado dentro de uma subrede com uma política de localização associada ou quando o cliente não foi atribuído diretamente com uma política de localização. As políticas sinalizadas são atribuídas à subredes ou usuários.</span><span class="sxs-lookup"><span data-stu-id="745ac-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="745ac-114">Para criar uma política de localização, você deve usar uma conta membro do grupo RTCUniversalServerAdmins, membro da função administrativa CsVoiceAdministrator ou com direitos e permissões de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="745ac-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="745ac-115">Para obter mais informações, [consulte Planejar políticas de local para o Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="745ac-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="745ac-116">Os cmdlets neste procedimento usam uma política de local definida usando os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="745ac-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="745ac-117">Para uma descrição completa dos parâmetros e valores do cmdlet, consulte [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="745ac-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="745ac-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="745ac-118">**Element**</span></span>                               | <span data-ttu-id="745ac-119">**Valor**</span><span class="sxs-lookup"><span data-stu-id="745ac-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="745ac-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="745ac-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="745ac-121">**Verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="745ac-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="745ac-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="745ac-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="745ac-123">**Aviso de isenção**</span><span class="sxs-lookup"><span data-stu-id="745ac-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="745ac-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="745ac-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="745ac-p105">Sua empresa exige a definição de uma localização. Se você não a definir, os serviços de emergência não poderão localizá-lo em caso de emergência. Defina uma localização.</span><span class="sxs-lookup"><span data-stu-id="745ac-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
| <span data-ttu-id="745ac-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="745ac-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="745ac-129">**Falso**</span><span class="sxs-lookup"><span data-stu-id="745ac-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="745ac-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="745ac-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="745ac-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="745ac-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="745ac-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="745ac-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="745ac-133">**911**</span><span class="sxs-lookup"><span data-stu-id="745ac-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="745ac-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="745ac-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="745ac-135">**112**</span><span class="sxs-lookup"><span data-stu-id="745ac-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="745ac-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="745ac-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="745ac-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="745ac-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="745ac-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="745ac-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="745ac-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="745ac-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="745ac-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="745ac-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="745ac-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="745ac-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="745ac-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="745ac-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="745ac-143">**2**</span><span class="sxs-lookup"><span data-stu-id="745ac-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="745ac-144">Para criar políticas de localização</span><span class="sxs-lookup"><span data-stu-id="745ac-144">To create location policies</span></span>

1. <span data-ttu-id="745ac-145">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="745ac-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="745ac-146">O CsLocationPolicy irá falhar se a configuração do **PstnUsage** ainda não estiver na lista Global de PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="745ac-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="745ac-147">Opcionalmente, execute o seguinte cmdlet para editar a política de localização global:</span><span class="sxs-lookup"><span data-stu-id="745ac-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="745ac-148">Execute o seguinte para criar uma política de localização sinalizada.</span><span class="sxs-lookup"><span data-stu-id="745ac-148">Run the following to create a tagged Location Policy.</span></span>

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="745ac-149">Execute o seguinte cmdlet para aplicar a política de localização sinalizada criada na etapa 3 em uma política de usuário.</span><span class="sxs-lookup"><span data-stu-id="745ac-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
