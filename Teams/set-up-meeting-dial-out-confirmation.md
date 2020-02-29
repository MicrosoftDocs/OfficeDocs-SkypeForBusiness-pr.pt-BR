---
title: Configurar discagem externa da reunião-confirmação para seus usuários no Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o Microsoft Teams para solicitar uma confirmação de discagem para impedir que sistemas de correio de voz se conectem a reuniões quando a pessoa chamada não conseguir atender a chamada.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339466"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurar a confirmação de discagem de reunião para seus usuários no Microsoft Teams

As chamadas discadas na reunião e chamadas para mim são muito úteis para convidar participantes a participarem de uma reunião e para que os participantes existentes ingressem em uma reunião usando um telefone tradicional ou celular. No entanto, quando a pessoa chamada não consegue atender a chamada e a chamada é atendida por um sistema de correio de voz, o sistema de correio de voz está conectado à reunião e os participantes poderão ouvi-la até ser removida da reunião.

Para impedir que sistemas de correio de voz se conectem a reuniões quando uma reunião discada for enviada para um número de telefone e a pessoa chamada não conseguir atender a chamada, você poderá configurar o Microsoft Teams para solicitar uma confirmação da pessoa chamada para ela ingressar na reunião. Se a pessoa chamada não conseguir atender a chamada e a chamada for respondida por um sistema de correio de voz, o sistema de correio de voz não será conectado à reunião porque não fornecerá uma confirmação para ingressar nela.

Quando essa funcionalidade estiver habilitada, as pessoas que receberem chamadas discadas ou chamadas para mim deverão confirmar que desejam ingressar na reunião pressionando 1 no seu telefone tradicional ou celular.

Para habilitar esse recurso para todas as reuniões em sua organização, defina ```EnableDialOutJoinConfirmation``` o parâmetro do cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) como ```true```. Para isso, execute o seguinte comando:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Tópicos relacionados

- [Configurar o recurso Telefonar para Mim para os usuários](set-up-the-call-me-feature-for-your-users.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)