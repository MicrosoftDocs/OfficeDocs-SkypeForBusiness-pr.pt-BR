---
title: Configuração do teclado de discagem do Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Saiba mais sobre como configurar o teclado de discagem no cliente do Teams para que os usuários possam acessar a funcionalidade PSTN (Rede Telefônica Pública Comutado).
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012409"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="e5bbb-103">Configuração do teclado de discagem</span><span class="sxs-lookup"><span data-stu-id="e5bbb-103">Dial pad configuration</span></span>

<span data-ttu-id="e5bbb-104">No cliente do Teams, o teclado de discagem permite que os usuários acessem a funcionalidade PSTN (Rede Telefônica Pública Comutado).</span><span class="sxs-lookup"><span data-stu-id="e5bbb-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="e5bbb-105">O teclado de discagem está disponível para usuários com uma licença do Sistema de Telefonia, desde que eles sejam configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="e5bbb-106">Todos os critérios a seguir são necessários para que o teclado de discagem mostre:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="e5bbb-107">O usuário tem uma licença do Sistema Telefônico habilitado ("MCOEV")</span><span class="sxs-lookup"><span data-stu-id="e5bbb-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="e5bbb-108">O usuário tem o Plano de Chamada da Microsoft ou está habilitado para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="e5bbb-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="e5bbb-109">O usuário tem o Enterprise Voice habilitado</span><span class="sxs-lookup"><span data-stu-id="e5bbb-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="e5bbb-110">O usuário está online e não no Skype for Business local</span><span class="sxs-lookup"><span data-stu-id="e5bbb-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="e5bbb-111">O usuário tem a Política de Chamada do Teams habilitada</span><span class="sxs-lookup"><span data-stu-id="e5bbb-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="e5bbb-112">As seções a seguir descrevem como usar o PowerShell para verificar os critérios.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="e5bbb-113">Na maioria dos casos, você precisa ver várias propriedades na saída do cmdlet Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="e5bbb-114">Os exemplos pressuem $user seja o endereço UPN ou sip do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="e5bbb-115">O usuário tem uma licença do Sistema Telefônico habilitado ("MCOEV")</span><span class="sxs-lookup"><span data-stu-id="e5bbb-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="e5bbb-116">Você deve garantir que o plano atribuído para o usuário mostre o atributo **CapabilityStatus** definido como Habilitado e o Plano de Capacidade definido como **MCOEV** (licença do Sistema de Telefonia).</span><span class="sxs-lookup"><span data-stu-id="e5bbb-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="e5bbb-117">Você pode ver MCOEV, MCOEV1 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="e5bbb-118">Todos são aceitáveis, desde que o Plano de Capacidade comece com MCOEV.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="e5bbb-119">Para verificar se os atributos estão definidos corretamente, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="e5bbb-120">A saída terá a seguinte aparência.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-120">The output will look like the following.</span></span> <span data-ttu-id="e5bbb-121">Você só precisa verificar os atributos **CapabilityStatus** e **Plano de Capacidade:**</span><span class="sxs-lookup"><span data-stu-id="e5bbb-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="e5bbb-122">O usuário tem o Plano de Chamada da Microsoft OU está habilitado para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="e5bbb-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="e5bbb-123">**Se o usuário** tiver o Plano de Chamada da Microsoft, você deve garantir que o atributo **CapabilityStatus** está definido como Habilitado e que o Plano de Capacidade está definido como **MCOPSTN.**</span><span class="sxs-lookup"><span data-stu-id="e5bbb-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="e5bbb-124">Você pode ver MCOPSTN1, MCOPSTN2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="e5bbb-125">Todos são aceitáveis, desde que o Plano de Capacidade comece com o MCOPSTN.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="e5bbb-126">Para verificar os atributos, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="e5bbb-127">A saída terá a seguinte aparência.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-127">The output will look like the following.</span></span> <span data-ttu-id="e5bbb-128">Você só precisa verificar os atributos **CapabilityStatus** e **Plano de Capacidade:**</span><span class="sxs-lookup"><span data-stu-id="e5bbb-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

<span data-ttu-id="e5bbb-129">**Se o usuário estiver habilitado** para Roteamento Direto, o usuário deverá ter um valor não nulo para o OnlineVoiceRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="e5bbb-130">Para verificar o atributo, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="e5bbb-131">A saída deve ter um valor não nulo, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="e5bbb-132">O usuário tem o Enterprise Voice habilitado</span><span class="sxs-lookup"><span data-stu-id="e5bbb-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="e5bbb-133">Para verificar se o usuário tem o Enterprise Voice habilitado, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="e5bbb-134">A saída deve ter a aparência:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="e5bbb-135">O usuário está online e não no Skype for Business local</span><span class="sxs-lookup"><span data-stu-id="e5bbb-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="e5bbb-136">Para garantir que o usuário está online e não no Skype for Business no local, o RegistradorPool não deve ser nulo e o HostingProvider deve conter um valor que começa com "sipfed.online".</span><span class="sxs-lookup"><span data-stu-id="e5bbb-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="e5bbb-137">Para verificar os valores, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="e5bbb-138">A saída deve ser semelhante a:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="e5bbb-139">O usuário tem a Política de Chamada do Teams habilitada</span><span class="sxs-lookup"><span data-stu-id="e5bbb-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="e5bbb-140">O TeamsCallingPolicy eficaz do usuário deve ter AllowPrivateCalling definido como true.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="e5bbb-141">Por padrão, os usuários herdam a política global, que tem AllowPrivateCallingPolicy definido como true por padrão.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="e5bbb-142">Para obter o TeamsCallingPolicy para um usuário e verificar se AllowPrivateCalling está definido como true, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="e5bbb-143">A saída deve ter a aparência:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-143">The output should look like:</span></span>

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a><span data-ttu-id="e5bbb-144">Anotações adicionais</span><span class="sxs-lookup"><span data-stu-id="e5bbb-144">Additional notes</span></span>

-   <span data-ttu-id="e5bbb-145">Talvez seja necessário reiniciar o cliente do Teams depois de fazer qualquer uma dessas alterações de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="e5bbb-146">Se você atualizou recentemente qualquer um dos critérios acima, talvez seja necessário aguardar algumas horas para que o cliente receba as novas configurações.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="e5bbb-147">Se você ainda não vir o teclado de discagem, verifique se há um erro de provisionamento usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="e5bbb-148">Se tiver mais de 24 horas e você ainda estiver vendo problemas, entre em contato com o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


