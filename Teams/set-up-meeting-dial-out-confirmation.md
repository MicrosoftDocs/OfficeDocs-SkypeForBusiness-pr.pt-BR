---
title: Configurar a confirmação de discagem de reunião para seus usuários no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o Teams para solicitar uma confirmação de discagem para impedir que os sistemas de caixa postal se conectem a reuniões quando a pessoa chamada não puder atender à chamada.
ms.localizationpriority: medium
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74a02b8d6c0a11202676144ce2dba91618118c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271556"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurar a confirmação de discagem de reunião para seus usuários no Microsoft Teams

Discagem de reunião e chamadas de chamada são maneiras úteis de convidar participantes para ingressar em uma reunião e para que os participantes existentes ingressem em uma reunião usando um telefone celular ou tradicional. No entanto, quando a pessoa chamada não consegue atender a chamada e a chamada é atendida por um sistema de caixa postal, o sistema de caixa postal é conectado à reunião. Os participantes poderão ouvi-lo até que ele seja removido da reunião.

Para impedir que os sistemas de caixa postal se conectem a reuniões quando uma discagem de reunião é enviada para um número de telefone e a pessoa chamada não consegue atender à chamada, você pode configurar o Teams para solicitar uma confirmação da pessoa chamada para que ela ingresse na reunião. Se a pessoa chamada não puder atender a chamada e a chamada for atendida por um sistema de caixa postal, o sistema de caixa postal não será conectado à reunião porque não fornecerá uma confirmação para ingressá-la.

Quando essa funcionalidade estiver habilitada, as pessoas que receberem uma chamada discada ou Ligar para mim deverão confirmar que querem ingressar na reunião pressionando 1 em seu telefone celular ou tradicional ou dizendo "Ok". A confirmação impedirá que a mensagem de voz do usuário ingresse na reunião.

Para habilitar esse recurso para todas as reuniões em sua organização, ```EnableDialOutJoinConfirmation``` defina o parâmetro do cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) como ```true```. Para definir esse parâmetro, execute o seguinte comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Tópicos relacionados

- [Configurar o recurso Telefonar para Mim para os usuários](set-up-the-call-me-feature-for-your-users.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
