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
# <a name="dial-pad-configuration"></a>Configuração do teclado de discagem

No cliente do Teams, o teclado de discagem permite que os usuários acessem a funcionalidade PSTN (rede telefônica pública comutada). O teclado de discagem está disponível para usuários com uma licença de sistema telefônico, contanto que estejam configurados corretamente. Os seguintes critérios são necessários para o teclado de discagem mostrar:

- O usuário tem uma licença de sistema telefônico habilitada ("MCOEV")
- O usuário tem um plano de chamadas da Microsoft ou está habilitado para roteamento direto
- O usuário tem o Enterprise Voice habilitado
- O usuário está em casa online e não no Skype for Business no local
- O usuário tem a política de chamada de equipe habilitada

As seções a seguir descrevem como usar o PowerShell para verificar os critérios. Na maioria dos casos, você precisa examinar várias propriedades na saída do cmdlet Get-CsOnlineUser. Os exemplos pressupõem que $user seja o endereço UPN ou SIP do usuário.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>O usuário tem uma licença de sistema telefônico habilitada ("MCOEV")

Você deve garantir que o plano atribuído para o usuário mostre o **atributo CapabilityStatus definido como Enabled** e o **plano de funcionalidades definido como MCOEV** (licença do sistema de telefonia). Você pode ver MCOEV, MCOEV1 e assim por diante. Todos são aceitáveis--desde que o plano de recursos comece com o MCOEV.

Para verificar se os atributos estão definidos corretamente, use o seguinte comando:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

O resultado será semelhante ao seguinte. Você só precisa verificar os atributos **CapabilityStatus** e **plano de recursos** :

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>O usuário tem um plano de chamadas da Microsoft ou está habilitado para roteamento direto

**Se o usuário tiver um plano de chamadas da Microsoft**, você deve garantir que o **atributo CapabilityStatus esteja definido como habilitado**e que o **plano de funcionalidade esteja definido como MCOPSTN**. Você pode ver MCOPSTN1, MCOPSTN2 e assim por diante. Todos são aceitáveis--desde que o plano de recursos comece com o MCOPSTN.

Para verificar os atributos, use o seguinte comando:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

O resultado será semelhante ao seguinte. Você só precisa verificar os atributos **CapabilityStatus** e **plano de recursos** :

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

**Se o usuário estiver habilitado para roteamento direto**, o usuário deverá receber um valor não nulo para OnlineVoiceRoutingPolicy. Para verificar o atributo, use o seguinte comando:
  
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

A saída deve ser como:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>O usuário está em casa online e não no Skype for Business no local

Para garantir que o usuário seja hospedado online e não no Skype for Business no local, o RegistrarPool não deve ser nulo e o Hostingprovider deve conter um valor que comece com "sipfed. online".  Para verificar os valores, use o seguinte comando:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

A saída deve ser semelhante a:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>O usuário tem a política de chamada de equipe habilitada

O TeamsCallingPolicy efetivo do usuário deve ter AllowPrivateCalling definido como true.  Por padrão, os usuários herdam a política global, que tem AllowPrivateCallingPolicy definido como true por padrão.

Para obter o TeamsCallingPolicy para um usuário e verificar se AllowPrivateCalling está definido como true, use o seguinte comando:

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

A saída deve ser como:

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

-   Talvez seja necessário reiniciar o cliente de equipes após fazer qualquer alteração de configuração.

-   Se você atualizou recentemente qualquer um dos critérios acima, talvez seja necessário esperar algumas horas para que o cliente receba as novas configurações.

-   Se você ainda não vir o teclado de discagem, verifique se há um erro de provisionamento usando o seguinte comando:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Se houver mais de 24 horas e você ainda estiver vendo problemas, entre em contato com o suporte.


