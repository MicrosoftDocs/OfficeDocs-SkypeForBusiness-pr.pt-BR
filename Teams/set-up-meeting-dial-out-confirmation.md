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
description: Saiba como configurar o Teams para solicitar uma confirmação de discagem para impedir que os sistemas de caixa postal se conectem às reuniões quando a pessoa chamada não puder atender à chamada.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfa15bdb0e58066d085aa852f671c6d89ff1b90
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117089"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurar a confirmação de discagem de reunião para seus usuários no Microsoft Teams

Discagem de reunião e chamadas de Chamada são maneiras muito úteis de convidar os participantes a ingressarem em uma reunião e que os participantes existentes participem de uma reunião usando um telefone celular ou tradicional. No entanto, quando a pessoa chamada não consegue atender à chamada e a chamada é atendida por um sistema de caixa postal, o sistema de caixa postal é conectado à reunião e os participantes poderão ouvi-la até que ela seja removida da reunião.

Para impedir que os sistemas de caixa postal se conectem a reuniões quando uma discagem de reunião é enviada para um número de telefone e a pessoa chamada não consegue atender à chamada, você pode configurar o Teams para solicitar uma confirmação da pessoa chamada para que ela participe da reunião. Se a pessoa chamada não puder atender à chamada e a chamada for atendida por um sistema de caixa postal, o sistema de caixa postal não será conectado à reunião porque não fornecerá uma confirmação para ingressar nele.

Quando essa funcionalidade estiver habilitada, as pessoas que receberem uma chamada discada ou Chamada devem confirmar se querem ingressar na reunião pressionando 1 em seu telefone celular ou tradicional.

Para habilitar esse recurso para todas as reuniões em sua organização, defina o parâmetro do ```EnableDialOutJoinConfirmation``` cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) como ```true``` . Para isso, execute o seguinte comando:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Tópicos relacionados

- [Configurar o recurso Telefonar para Mim para os usuários](set-up-the-call-me-feature-for-your-users.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)