---
title: Configuração do teclado de discagem do teams
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
description: Saiba como configurar o teclado de discagem no cliente do teams para que os usuários possam acessar a funcionalidade PSTN (rede telefônica pública comutada).
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012409"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="524fc-103">Configuração do teclado de discagem</span><span class="sxs-lookup"><span data-stu-id="524fc-103">Dial pad configuration</span></span>

<span data-ttu-id="524fc-104">No cliente do Teams, o teclado de discagem permite que os usuários acessem a funcionalidade PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="524fc-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="524fc-105">O teclado de discagem está disponível para usuários com uma licença de sistema telefônico, contanto que estejam configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="524fc-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="524fc-106">Os seguintes critérios são necessários para o teclado de discagem mostrar:</span><span class="sxs-lookup"><span data-stu-id="524fc-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="524fc-107">O usuário tem uma licença de sistema telefônico habilitada ("MCOEV")</span><span class="sxs-lookup"><span data-stu-id="524fc-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="524fc-108">O usuário tem um plano de chamadas da Microsoft ou está habilitado para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="524fc-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="524fc-109">O usuário tem o Enterprise Voice habilitado</span><span class="sxs-lookup"><span data-stu-id="524fc-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="524fc-110">O usuário está em casa online e não no Skype for Business no local</span><span class="sxs-lookup"><span data-stu-id="524fc-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="524fc-111">O usuário tem a política de chamada de equipe habilitada</span><span class="sxs-lookup"><span data-stu-id="524fc-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="524fc-112">As seções a seguir descrevem como usar o PowerShell para verificar os critérios.</span><span class="sxs-lookup"><span data-stu-id="524fc-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="524fc-113">Na maioria dos casos, você precisa examinar várias propriedades na saída do cmdlet Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="524fc-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="524fc-114">Os exemplos pressupõem que $user seja o endereço UPN ou SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="524fc-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="524fc-115">O usuário tem uma licença de sistema telefônico habilitada ("MCOEV")</span><span class="sxs-lookup"><span data-stu-id="524fc-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="524fc-116">Você deve garantir que o plano atribuído para o usuário mostre o **atributo CapabilityStatus definido como Enabled** e o **plano de funcionalidades definido como MCOEV** (licença do sistema de telefonia).</span><span class="sxs-lookup"><span data-stu-id="524fc-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="524fc-117">Você pode ver MCOEV, MCOEV1 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="524fc-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="524fc-118">Todos são aceitáveis--desde que o plano de recursos comece com o MCOEV.</span><span class="sxs-lookup"><span data-stu-id="524fc-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="524fc-119">Para verificar se os atributos estão definidos corretamente, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="524fc-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="524fc-120">O resultado será semelhante ao seguinte.</span><span class="sxs-lookup"><span data-stu-id="524fc-120">The output will look like the following.</span></span> <span data-ttu-id="524fc-121">Você só precisa verificar os atributos **CapabilityStatus** e **plano de recursos** :</span><span class="sxs-lookup"><span data-stu-id="524fc-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="524fc-122">O usuário tem um plano de chamadas da Microsoft ou está habilitado para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="524fc-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="524fc-123">**Se o usuário tiver um plano de chamadas da Microsoft**, você deve garantir que o **atributo CapabilityStatus esteja definido como habilitado**e que o **plano de funcionalidade esteja definido como MCOPSTN**.</span><span class="sxs-lookup"><span data-stu-id="524fc-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="524fc-124">Você pode ver MCOPSTN1, MCOPSTN2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="524fc-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="524fc-125">Todos são aceitáveis--desde que o plano de recursos comece com o MCOPSTN.</span><span class="sxs-lookup"><span data-stu-id="524fc-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="524fc-126">Para verificar os atributos, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="524fc-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="524fc-127">O resultado será semelhante ao seguinte.</span><span class="sxs-lookup"><span data-stu-id="524fc-127">The output will look like the following.</span></span> <span data-ttu-id="524fc-128">Você só precisa verificar os atributos **CapabilityStatus** e **plano de recursos** :</span><span class="sxs-lookup"><span data-stu-id="524fc-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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

<span data-ttu-id="524fc-129">**Se o usuário estiver habilitado para roteamento direto**, o usuário deverá receber um valor não nulo para OnlineVoiceRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="524fc-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="524fc-130">Para verificar o atributo, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="524fc-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="524fc-131">A saída deve ter um valor não nulo, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="524fc-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="524fc-132">O usuário tem o Enterprise Voice habilitado</span><span class="sxs-lookup"><span data-stu-id="524fc-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="524fc-133">Para verificar se o usuário tem o Enterprise Voice habilitado, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="524fc-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="524fc-134">A saída deve ser como:</span><span class="sxs-lookup"><span data-stu-id="524fc-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="524fc-135">O usuário está em casa online e não no Skype for Business no local</span><span class="sxs-lookup"><span data-stu-id="524fc-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="524fc-136">Para garantir que o usuário seja hospedado online e não no Skype for Business no local, o RegistrarPool não deve ser nulo e o Hostingprovider deve conter um valor que comece com "sipfed. online".</span><span class="sxs-lookup"><span data-stu-id="524fc-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="524fc-137">Para verificar os valores, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="524fc-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="524fc-138">A saída deve ser semelhante a:</span><span class="sxs-lookup"><span data-stu-id="524fc-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="524fc-139">O usuário tem a política de chamada de equipe habilitada</span><span class="sxs-lookup"><span data-stu-id="524fc-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="524fc-140">O TeamsCallingPolicy efetivo do usuário deve ter AllowPrivateCalling definido como true.</span><span class="sxs-lookup"><span data-stu-id="524fc-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="524fc-141">Por padrão, os usuários herdam a política global, que tem AllowPrivateCallingPolicy definido como true por padrão.</span><span class="sxs-lookup"><span data-stu-id="524fc-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="524fc-142">Para obter o TeamsCallingPolicy para um usuário e verificar se AllowPrivateCalling está definido como true, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="524fc-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="524fc-143">A saída deve ser como:</span><span class="sxs-lookup"><span data-stu-id="524fc-143">The output should look like:</span></span>

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

## <a name="additional-notes"></a><span data-ttu-id="524fc-144">Anotações adicionais</span><span class="sxs-lookup"><span data-stu-id="524fc-144">Additional notes</span></span>

-   <span data-ttu-id="524fc-145">Talvez seja necessário reiniciar o cliente de equipes após fazer qualquer alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="524fc-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="524fc-146">Se você atualizou recentemente qualquer um dos critérios acima, talvez seja necessário esperar algumas horas para que o cliente receba as novas configurações.</span><span class="sxs-lookup"><span data-stu-id="524fc-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="524fc-147">Se você ainda não vir o teclado de discagem, verifique se há um erro de provisionamento usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="524fc-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="524fc-148">Se houver mais de 24 horas e você ainda estiver vendo problemas, entre em contato com o suporte.</span><span class="sxs-lookup"><span data-stu-id="524fc-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


