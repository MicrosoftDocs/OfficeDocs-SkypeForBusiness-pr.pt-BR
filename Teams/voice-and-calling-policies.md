---
title: Gerenciar políticas de voz e chamada no Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Saiba mais sobre as políticas de voz e chamada do Teams.
audience: admin
ms.localizationpriority: medium
ms.collection:
- M365-voice
ms.openlocfilehash: d53c05053e2719a88b698497fd4a872c4cb91dab
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706928"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Gerenciar políticas de voz e chamada no Microsoft Teams

As políticas de voz e chamada são usadas para controlar a voz e a chamada no Microsoft Teams.

## <a name="emergency-calling-policies"></a>Políticas de chamada de emergência

Você usa [políticas de chamada de emergência](manage-emergency-calling-policies.md) para configurar o que acontece quando um usuário em sua organização faz uma chamada de emergência. Essas políticas são gerenciadas no centro de administração do Teams ou usando Windows PowerShell.

![Captura de tela da política de chamada de emergência.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Políticas de roteamento de chamadas de emergência

Se sua organização implantou o Roteamento Direto do Sistema de [](manage-emergency-call-routing-policies.md) Telefonia **, você** pode usar políticas de roteamento de chamadas de emergência para determinar para onde as chamadas de emergência são roteados, se os serviços de emergência aprimorados estão habilitados e quais números são usados para serviços de emergência. Essas políticas são gerenciadas usando o PowerShell ou no centro de administração do Microsoft Teams.

![Captura de tela da política de roteamento de chamadas de emergência.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Políticas de ID do chamador

[As políticas de ID do chamador](caller-id-policies.md) são usadas para alterar ou bloquear a ID do chamador.

![Captura de tela da política de ID do chamador.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Políticas de roteamento de voz

Uma [política de roteamento de](manage-voice-routing-policies.md) voz é um contêiner para registros de uso de PSTN (Rede Telefônica Pública Comunada). Você poderá usar essas políticas se sua organização tiver implantado o **Roteamento Direto do Sistema de Telefonia**. As políticas de roteamento de voz podem ser gerenciadas com o PowerShell ou no Centro de administração do Teams.

![Captura de tela da política de roteamento de voz.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Políticas de chamadas

[As políticas de](teams-calling-policy.md) chamada controlam quais recursos de encaminhamento de chamadas e chamadas estão disponíveis para os usuários, incluindo se um usuário pode fazer chamadas privadas, enviar chamadas para grupos de chamadas e encaminhar chamadas para a caixa postal.

![Captura de tela da política de chamada.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Estacionamento de chamadas e recuperação de políticas

[O estacionamento de chamadas e](call-park-and-retrieve.md) a recuperação permitem que os usuários coloquem outros usuários em espera e habilitem o mesmo usuário ou outra pessoa a continuar a chamada.

![Captura de tela do estacionamento de chamadas e da política de recuperação.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Criar e gerenciar planos de discagem

[Os planos de discagem](create-and-manage-dial-plans.md) convertem números de telefone discados para autorização e roteamento de chamadas. Você pode criar e gerenciar planos de discagem por meio do PowerShell ou no Centro de administração do Microsoft Teams.

![Captura de tela do plano de discagem.](media/dial-plans.png)

## <a name="related-topics"></a>Tópicos relacionados

* [Gerenciar políticas de chamadas de emergência no Microsoft Teams](manage-emergency-calling-policies.md)
* [Gerenciar políticas de roteamento de chamada](manage-emergency-call-routing-policies.md)
* [Gerenciar políticas de identificação de chamadas no Microsoft Teams](caller-id-policies.md)
* [Gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md)
* [Políticas de chamada no Microsoft Teams](teams-calling-policy.md)
* [Estacionamento e recuperação de chamadas no Microsoft Teams](call-park-and-retrieve.md)
* [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)
* [Gerenciar o Teams com políticas](manage-teams-with-policies.md)
