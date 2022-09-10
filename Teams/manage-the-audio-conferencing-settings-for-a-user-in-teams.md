---
title: Gerenciar configurações de Audioconferência para usuários
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Um administrador do Microsoft 365 ou Office 365 pode editar as configurações de Audioconferência do Teams, incluindo provedor, número de chamada tarifada ou gratuita padrão, ID de conferência ou PIN para um usuário.
ms.openlocfilehash: 9b68ea4452928ce739ec8429ed9b71bfaca91cf4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641902"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>Gerenciar as configurações de Audioconferência de um usuário no Microsoft Teams

Como administrador do Microsoft 365 ou Office 365, você pode editar as configurações de Audioconferência, como o provedor, número de chamada tarifada ou gratuita padrão, ID de conferência ou PIN, para um usuário individual em sua organização. Se você quiser editar as configurações da sua organização, consulte [Gerenciar as configurações de Audioconferência para sua organização](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, clique **em Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Clique **em Editar**.

3. Em **Audioconferência**, modifique qualquer um dos seguintes itens:

|**Configuração**|**Descrição**|
|:-----|:-----|
|**Audioconferência**|Para ativar ou desativar a audioconferência para o usuário,  clique em Editar ao lado de **Audioconferência** e, no painel Audioconferência,  ative ou desative a Audioconferência.|
|**Enviar informações de conferência por email**  |Clique neste link apenas se você quiser enviar imediatamente um e-mail para o usuário com sua ID de conferência e número de telefone. (Este e-mail não inclui o PIN.) Consulte [Enviar um e-mail para um usuário com informações de audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).  |
|**ID de conferência**  |Clique **em Redefinir ID de** conferência se precisar redefinir a ID de conferência para o usuário. Para obter mais informações, consulte [Redefinir uma ID de conferência para um usuário](reset-a-conference-id-for-a-user-in-teams.md).  |
|**Pino** |Clique **em Redefinir PIN** se precisar redefinir o PIN do usuário. Para obter mais informações, consulte [Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md). |
|**Número de telefone de chamada tarifada de conferência padrão** (obrigatório) |Os números definidos na ponte de audioconferência. Formate os números como você deseja que eles apareçam nas solicitações de reunião do Teams. Para alterar o número de chamada tarifada  padrão, clique em Editar ao lado de **Audioconferência** e, no painel **Audioconferência**, selecione um número em **Número de chamada tarifada**. Você também pode definir números de telefone adicionando-os ao TeamsAudioConferencingPolicy e atribuindo a política aos usuários. Os números de telefone adicionados à política têm precedência sobre os números de telefone definidos usando o número de telefone de **chamada tarifada de conferência padrão**. Se nenhum número de telefone for adicionado ao TeamsAudioConferencingPolicy, o número de telefone definido  usando o número de telefone de chamada tarifada de conferência padrão será exibido nas solicitações de reunião do Microsoft Teams. |
|**Convites desse usuário podem incluir número de chamada gratuita**|Essa configuração só pode ser alterada usando o TeamsAudioconferecningPolicy. |
|**Usuários não autenticados podem ser a primeira pessoa na reunião**|Para alterar essa configuração, ativar ou desativar usuários não autenticados pode ser a primeira **pessoa** na reunião.
|**Permissões de discagem**|Para alterar essa configuração, clique em **Editar** ao lado de **Audioconferência** e, no painel **Audioconferência** , escolha uma opção em **Discagem das reuniões**.|

![Mostra as configurações de Audioconferência para um usuário.](media/teams-manage-audio-conferencing-settings-for-a-user-image1.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência para minha organização](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[Perguntas comuns sobre a Audioconferência](audio-conferencing-common-questions.md)
