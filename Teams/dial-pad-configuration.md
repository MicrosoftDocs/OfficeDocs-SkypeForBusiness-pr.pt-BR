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
# <a name="dial-pad-configuration"></a>Configuração do teclado de discagem

No cliente do Teams, o teclado de discagem permite que os usuários acessem a funcionalidade PSTN (Rede Telefônica Pública Comutado). O teclado de discagem está disponível para usuários com uma licença do Sistema de Telefonia, desde que eles sejam configurados corretamente. Todos os critérios a seguir são necessários para que o teclado de discagem mostre:

- O usuário tem uma licença do Sistema Telefônico habilitado ("MCOEV")
- O usuário tem o Plano de Chamada da Microsoft ou está habilitado para Roteamento Direto
- O usuário tem o Enterprise Voice habilitado
- O usuário está online e não no Skype for Business local
- O usuário tem a Política de Chamada do Teams habilitada

As seções a seguir descrevem como usar o PowerShell para verificar os critérios. Na maioria dos casos, você precisa ver várias propriedades na saída do cmdlet Get-CsOnlineUser. Os exemplos pressuem $user seja o endereço UPN ou sip do usuário.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>O usuário tem uma licença do Sistema Telefônico habilitado ("MCOEV")

Você deve garantir que o plano atribuído para o usuário mostre o atributo **CapabilityStatus** definido como Habilitado e o Plano de Capacidade definido como **MCOEV** (licença do Sistema de Telefonia). Você pode ver MCOEV, MCOEV1 e assim por diante. Todos são aceitáveis, desde que o Plano de Capacidade comece com MCOEV.

Para verificar se os atributos estão definidos corretamente, use o seguinte comando:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

A saída terá a seguinte aparência. Você só precisa verificar os atributos **CapabilityStatus** e **Plano de Capacidade:**

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>O usuário tem o Plano de Chamada da Microsoft OU está habilitado para Roteamento Direto

**Se o usuário** tiver o Plano de Chamada da Microsoft, você deve garantir que o atributo **CapabilityStatus** está definido como Habilitado e que o Plano de Capacidade está definido como **MCOPSTN.** Você pode ver MCOPSTN1, MCOPSTN2 e assim por diante. Todos são aceitáveis, desde que o Plano de Capacidade comece com o MCOPSTN.

Para verificar os atributos, use o seguinte comando:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

A saída terá a seguinte aparência. Você só precisa verificar os atributos **CapabilityStatus** e **Plano de Capacidade:**

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

**Se o usuário estiver habilitado** para Roteamento Direto, o usuário deverá ter um valor não nulo para o OnlineVoiceRoutingPolicy. Para verificar o atributo, use o seguinte comando:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

A saída deve ter um valor não nulo, por exemplo:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>O usuário tem o Enterprise Voice habilitado

Para verificar se o usuário tem o Enterprise Voice habilitado, use o seguinte comando:

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

A saída deve ter a aparência:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>O usuário está online e não no Skype for Business local

Para garantir que o usuário está online e não no Skype for Business no local, o RegistradorPool não deve ser nulo e o HostingProvider deve conter um valor que começa com "sipfed.online".  Para verificar os valores, use o seguinte comando:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

A saída deve ser semelhante a:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>O usuário tem a Política de Chamada do Teams habilitada

O TeamsCallingPolicy eficaz do usuário deve ter AllowPrivateCalling definido como true.  Por padrão, os usuários herdam a política global, que tem AllowPrivateCallingPolicy definido como true por padrão.

Para obter o TeamsCallingPolicy para um usuário e verificar se AllowPrivateCalling está definido como true, use o seguinte comando:

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

A saída deve ter a aparência:

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

## <a name="additional-notes"></a>Anotações adicionais

-   Talvez seja necessário reiniciar o cliente do Teams depois de fazer qualquer uma dessas alterações de configuração.

-   Se você atualizou recentemente qualquer um dos critérios acima, talvez seja necessário aguardar algumas horas para que o cliente receba as novas configurações.

-   Se você ainda não vir o teclado de discagem, verifique se há um erro de provisionamento usando o seguinte comando:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Se tiver mais de 24 horas e você ainda estiver vendo problemas, entre em contato com o Suporte.


