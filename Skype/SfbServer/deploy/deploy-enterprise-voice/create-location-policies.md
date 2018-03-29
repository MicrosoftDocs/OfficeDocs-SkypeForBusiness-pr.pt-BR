---
title: Criar políticas de localização no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Leia este tópico para saber como configurar aprimorada políticas de local de serviço de emergência (E9-1-1) em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 7635199810e21f33bdbe30d5bf6f229987fa8c77
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="create-location-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="bb0b8-103">Criar políticas de localização no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bb0b8-103">Create location policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bb0b8-104">Leia este tópico para saber como configurar aprimorada políticas de local de serviço de emergência (E9-1-1) em Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="bb0b8-105">Skype para Business Server usa uma política de local para habilitar o Skype para clientes corporativos para E9-1-1 durante o registro de cliente.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="bb0b8-106">Uma política de local contém as configurações que definem como o serviço E9-1-1 será implementado.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="bb0b8-107">Para obter mais informações, consulte [planejar políticas de local para Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bb0b8-107">For more information, see [Plan location policies for Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>
  
<span data-ttu-id="bb0b8-108">Defina as políticas de local usando o Skype para painel de controle corporativos ou usando o cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="bb0b8-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb0b8-109">Skype para Business Server agora oferece suporte a configuração de vários números de emergências para um cliente.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="bb0b8-110">Se você deseja configurar vários números de emergências, você deve seguir as informações em [vários números de emergências Skype para Business Server 2015 planejar](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) e [Configurar vários números de emergências Skype para negócios 2015](configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="bb0b8-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business 2015](configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="bb0b8-p103">É possível editar a política de localização global e criar novas políticas de localização sinalizadas. Um cliente obtém uma política global quando não está localizado dentro de uma sub-rede com uma política de localização associada ou quando o cliente não foi atribuído diretamente com uma política de localização. As políticas sinalizadas são atribuídas à sub-redes ou usuários.  </span><span class="sxs-lookup"><span data-stu-id="bb0b8-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 
  
<span data-ttu-id="bb0b8-114">Para criar uma política de localização, você deve usar uma conta membro do grupo RTCUniversalServerAdmins, membro da função administrativa CsVoiceAdministrator ou com direitos e permissões de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>
  
<span data-ttu-id="bb0b8-115">Para obter mais informações, consulte [planejar políticas de local para Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bb0b8-115">For more information, see [Plan location policies for Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="bb0b8-116">Os cmdlets contidos neste procedimento usam uma política de local definida com os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="bb0b8-117">Para obter uma descrição completa dos valores e de parâmetros do cmdlet, consulte [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bb0b8-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>
  
|<span data-ttu-id="bb0b8-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-118">**Element**</span></span>|<span data-ttu-id="bb0b8-119">**Valor**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-119">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bb0b8-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="bb0b8-120">EnhancedEmergencyServicesEnabled</span></span>  <br/> |<span data-ttu-id="bb0b8-121">**True**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-121">**True**</span></span> <br/> |
|<span data-ttu-id="bb0b8-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="bb0b8-122">LocationRequired</span></span>  <br/> |<span data-ttu-id="bb0b8-123">**Disclaimer**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-123">**Disclaimer**</span></span> <br/> |
|<span data-ttu-id="bb0b8-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="bb0b8-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> |<span data-ttu-id="bb0b8-p105">Sua empresa exige a definição de uma localização. Se você não a definir, os serviços de emergência não poderão localizá-lo em caso de emergência. Defina uma localização.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
|<span data-ttu-id="bb0b8-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="bb0b8-128">UseLocationForE911Only</span></span>  <br/> |<span data-ttu-id="bb0b8-129">**False**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-129">**False**</span></span> <br/> |
|<span data-ttu-id="bb0b8-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="bb0b8-130">PstnUsage</span></span>  <br/> |<span data-ttu-id="bb0b8-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-131">**EmergencyUsage**</span></span> <br/> |
|<span data-ttu-id="bb0b8-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="bb0b8-132">EmergencyDialString</span></span>  <br/> |<span data-ttu-id="bb0b8-133">**911**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-133">**911**</span></span> <br/> |
|<span data-ttu-id="bb0b8-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="bb0b8-134">EmergencyDialMask</span></span>  <br/> |<span data-ttu-id="bb0b8-135">**112**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-135">**112**</span></span> <br/> |
|<span data-ttu-id="bb0b8-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="bb0b8-136">NotificationUri</span></span>  <br/> |<span data-ttu-id="bb0b8-137">**SIP:Security@litwareinc.com**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-137">**sip:security@litwareinc.com**</span></span> <br/> |
|<span data-ttu-id="bb0b8-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="bb0b8-138">ConferenceUri</span></span>  <br/> |<span data-ttu-id="bb0b8-139">**SIP:+14255550123@litwareinc.com**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-139">**sip:+14255550123@litwareinc.com**</span></span> <br/> |
|<span data-ttu-id="bb0b8-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="bb0b8-140">ConferenceMode</span></span>  <br/> |<span data-ttu-id="bb0b8-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-141">**twoway**</span></span> <br/> |
|<span data-ttu-id="bb0b8-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="bb0b8-142">LocationRefreshInterval</span></span>  <br/> |<span data-ttu-id="bb0b8-143">**2**</span><span class="sxs-lookup"><span data-stu-id="bb0b8-143">**2**</span></span> <br/> |
   
### <a name="to-create-location-policies"></a><span data-ttu-id="bb0b8-144">Para criar políticas de localização</span><span class="sxs-lookup"><span data-stu-id="bb0b8-144">To create location policies</span></span>

1. <span data-ttu-id="bb0b8-145">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb0b8-146">O CsLocationPolicy irá falhar se a configuração do **PstnUsage** ainda não estiver na lista Global de PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>
  
2. <span data-ttu-id="bb0b8-147">Opcionalmente, execute o seguinte cmdlet para editar a política de localização global:</span><span class="sxs-lookup"><span data-stu-id="bb0b8-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

   ```

3. <span data-ttu-id="bb0b8-148">Execute o seguinte para criar uma política de localização sinalizada.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-148">Run the following to create a tagged Location Policy.</span></span>
    
   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

   ```

4. <span data-ttu-id="bb0b8-149">Execute o seguinte cmdlet para aplicar a política de localização sinalizada criada na etapa 3 em uma política de usuário.</span><span class="sxs-lookup"><span data-stu-id="bb0b8-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```


