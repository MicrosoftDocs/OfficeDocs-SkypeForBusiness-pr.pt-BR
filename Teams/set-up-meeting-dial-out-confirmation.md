---
title: Configurar a confirmação de discagem de reunião para seus usuários no Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o Teams para solicitar uma confirmação de discagem para impedir que os sistemas de caixa postal se conectem a reuniões quando a pessoa chamada não puder atender a chamada.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806141"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurar a confirmação de discagem de reunião para seus usuários no Microsoft Teams

As discações de reunião e as chamadas de Telefonar para mim são maneiras muito úteis de convidar participantes para ingressar em uma reunião e para que os participantes existentes in join a meeting using a traditional or mobile phone. No entanto, quando a pessoa chamada não consegue atender a chamada e a chamada é atendida por um sistema de caixa postal, o sistema de caixa postal é conectado à reunião e os participantes poderão ouvi-la até que ela seja removida da reunião.

Para impedir que os sistemas de caixa postal se conectem a reuniões quando uma discagem de reunião é enviada para um número de telefone e a pessoa chamada não consegue atender a chamada, você pode configurar o Teams para solicitar uma confirmação da pessoa chamada para que ela entre na reunião. Se a pessoa chamada não puder atender a chamada e a chamada for atendida por um sistema de caixa postal, o sistema de caixa postal não será conectado à reunião porque ele não fornecerá uma confirmação para ingressar nele.

Quando esse recurso estiver habilitado, as pessoas que receberem uma chamada de discagem ou Telefonar para mim deverão confirmar que querem ingressar na reunião pressionando 1 em seu telefone tradicional ou celular.

Para habilitar esse recurso para todas as reuniões em sua organização, defina o parâmetro do ```EnableDialOutJoinConfirmation``` cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) como ```true``` . Para isso, execute o seguinte comando:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Tópicos relacionados

- [Configurar o recurso Telefonar para Mim para os usuários](set-up-the-call-me-feature-for-your-users.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)