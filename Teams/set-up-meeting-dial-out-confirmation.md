---
title: Configurar a confirmação de discagem de reunião para seus usuários em Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o Teams para solicitar uma confirmação de discagem para impedir que os sistemas de caixa postal se conectem às reuniões quando a pessoa chamada não puder atender à chamada.
ms.localizationpriority: medium
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32cdc63f2b129e7d925fed46a8b89ac90944926e
ms.sourcegitcommit: bb302109886a4b853a8e493fb0ffafad4bc4f86b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2022
ms.locfileid: "62085230"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurar a confirmação de discagem de reunião para seus usuários em Microsoft Teams

Discagem de reunião e chamadas de Chamada são maneiras úteis de convidar os participantes a ingressarem em uma reunião e que os participantes existentes participem de uma reunião usando um telefone celular ou tradicional. No entanto, quando a pessoa chamada não consegue atender à chamada e a chamada é atendida por um sistema de caixa postal, o sistema de caixa postal é conectado à reunião. Os participantes poderão ouvi-lo até que seja removido da reunião.

Para impedir que os sistemas de caixa postal se conectem às reuniões quando uma discagem de reunião é enviada para um número de telefone e a pessoa chamada não consegue atender à chamada, você pode configurar o Teams para solicitar uma confirmação da pessoa chamada para que ela participe da reunião. Se a pessoa chamada não puder atender à chamada e a chamada for atendida por um sistema de caixa postal, o sistema de caixa postal não será conectado à reunião porque não fornecerá uma confirmação para ingressar nele.

Quando essa funcionalidade estiver habilitada, as pessoas que receberem uma chamada discada ou Chamada de chamada devem confirmar se querem ingressar na reunião pressionando 1 em seu telefone tradicional ou celular ou dizendo "Ok". A confirmação impedirá que a mensagem de caixa postal do usuário entre na reunião.

Para habilitar esse recurso para todas as reuniões em sua organização, defina o parâmetro do ```EnableDialOutJoinConfirmation``` cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) como ```true``` . Para definir esse parâmetro, execute o seguinte comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Tópicos relacionados

- [Configurar o recurso Telefonar para Mim para os usuários](set-up-the-call-me-feature-for-your-users.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
