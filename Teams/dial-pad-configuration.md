---
title: Teams configuração do teclado de discagem
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Saiba mais sobre como configurar o teclado de discagem no cliente Teams para que os usuários possam acessar a funcionalidade PSTN (Rede Telefônica Pública Comuada).
ms.openlocfilehash: 7fc2622ce0fda97ce608e13d67ff786431a30aa5
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2022
ms.locfileid: "65248923"
---
# <a name="dial-pad-configuration"></a>Configuração do teclado de discagem

No cliente Teams, o teclado de discagem permite que os usuários acessem a funcionalidade PSTN (Rede Telefônica Pública Comuada). O teclado de discagem está disponível para usuários com uma Sistema de Telefonia, desde que eles sejam configurados corretamente. Todos os critérios a seguir são necessários para que o teclado de discagem mostre:

- O usuário tem uma licença Sistema de Telefonia ("MCOEV") habilitada
- O usuário tem o Plano de Chamadas da Microsoft, Conexão do operador ou está habilitado para Roteamento Direto
- O usuário Enterprise Voice habilitado
- O usuário está hospedado online e não Skype for Business local
- O usuário Teams política de chamada habilitada

As seções a seguir descrevem como usar o PowerShell para verificar os critérios. Na maioria dos casos, você precisa examinar várias propriedades na saída do Get-CsOnlineUser cmdlet. Os exemplos pressupõem $user seja o endereço UPN ou sip do usuário.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>O usuário tem uma licença Sistema de Telefonia ("MCOEV") habilitada

Verifique se o plano atribuído para o usuário mostra o atributo **CapabilityStatus** definido como Habilitado e o Recurso definido como **MCOEV** (Sistema de Telefonia licença). Você pode ver MCOEV, MCOEV1 e assim por diante. Todos são aceitáveis, desde que o Recurso comece com MCOEV.

Para verificar se os atributos estão definidos corretamente, use o seguinte comando:

```
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

A saída será semelhante à seguinte. Você só precisa verificar os atributos **CapabilityStatus** e **Capability** :

```
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-…
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-…
```


## <a name="user-has-microsoft-calling-plan-operator-connect-or-is-enabled-for-direct-routing"></a>O usuário tem o Plano de Chamadas da Microsoft, Conexão do operador OR está habilitado para Roteamento Direto

**Se o usuário tiver o Plano** de Chamada da Microsoft, verifique se o atributo **CapabilityStatus** está definido como Habilitado e se a Funcionalidade está definida como **MCOPSTN**. Você pode ver MCOPSTN1, MCOPSTN2 e assim por diante. Todos são aceitáveis, desde que o Recurso comece com MCOPSTN.

Para verificar os atributos, use o seguinte comando:

```
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

A saída será semelhante à seguinte. Você só precisa verificar os atributos **CapabilityStatus** e **Capability** :

```  
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-…
07-02-2020 12:28:48 MCOPSTN2        Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 5a10155d-f5c1-411a-a8ec-…
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-…
```
**Se o usuário estiver** habilitado para Conexão do operador, o usuário deverá ter um valor não nulo para TeamsCarrierEmergencyCallRoutingPolicy. Para verificar o atributo, use o seguinte comando:
  
```
Get-CsOnlineUser -Identity $user|Select TeamsCarrierEmergencyCallRoutingPolicy
```

A saída deve ter um valor não nulo, por exemplo:

```
TeamsCarrierEmergencyCallRoutingPolicy
--------------------------------------
Synergy_98d1a5cb-d3e6-4306-885e-69a95f2da5c3
```

**Se o usuário estiver habilitado para Roteamento** Direto, o usuário deverá receber um valor não nulo para OnlineVoiceRoutingPolicy. Para verificar o atributo, use o seguinte comando:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

A saída deve ter um valor não nulo, por exemplo:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>O usuário Enterprise Voice habilitado

Para verificar se o usuário Enterprise Voice habilitado, use o seguinte comando:

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

A saída deve ser semelhante a:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>O usuário está hospedado online e não Skype for Business local

Para garantir que o usuário esteja hospedado online e não no Skype for Business local, o RegistradorPool não deve ser nulo e o HostingProvider deve conter um valor que comece com "sipfed.online".  Para verificar os valores, use o seguinte comando:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

A saída deve ser semelhante a:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>O usuário Teams política de chamada habilitada

O TeamsCallingPolicy efetivo do usuário deve ter AllowPrivateCalling definido como true.  Por padrão, os usuários herdam a política global, que tem AllowPrivateCallingPolicy definido como true por padrão.

Para obter o TeamsCallingPolicy para um usuário e verificar se AllowPrivateCalling está definido como true, use o seguinte comando:

```
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
```

A saída deve ser semelhante a:

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

## <a name="additional-notes"></a>Observações adicionais

-   Talvez seja necessário reiniciar o cliente Teams depois de fazer qualquer uma dessas alterações de configuração.

-   Se você atualizou recentemente qualquer um dos critérios acima, talvez seja necessário aguardar algumas horas para que o cliente receba as novas configurações.

-   Se você ainda não vir o teclado de discagem, verifique se há um erro de provisionamento usando o seguinte comando:

  ```
  Get-CsOnlineUser -Identity $user|Select UserValidationErrors
  ```

-    Se já se foram mais de 24 horas e você ainda está com problemas, entre em contato com o Suporte.


