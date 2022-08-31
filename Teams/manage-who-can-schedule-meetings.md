---
title: Gerenciar quem pode iniciar reuniões instantâneas e agendar reuniões
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Saiba como usar as configurações de política de reunião do Teams para controlar quem pode iniciar reuniões instantâneas e agendar reuniões.
ms.openlocfilehash: 6736ecd20ef4b0e9eb082e83bd8212597da5f7ab
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466282"
---
# <a name="manage-who-can-start-instant-meetings-and-schedule-meetings"></a>Gerenciar quem pode iniciar reuniões instantâneas e agendar reuniões

Como administrador, você pode restringir quais usuários podem iniciar reuniões instantâneas e agendar reuniões no Teams. Isso pode ser especialmente útil por motivos de privacidade e segurança, em que talvez você não queira que usuários específicos configurem reuniões.

As configurações de política de reunião são ativadas por padrão. Essas configurações podem ser encontradas no centro de administração do Teams em **Políticas de Reunião** > **.**

- **Reunir-se agora em canais**: controla se um usuário pode iniciar uma reunião instantânea em um canal.
- **Agendamento de reunião de canal**: controla se um usuário pode agendar uma reunião em um canal.
- **Agendamento de reunião privada**: controla se um usuário pode agendar uma reunião privada no Teams. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- **Suplemento do Outlook**: controla se um usuário pode agendar uma reunião privada do Outlook. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- **Reunir-se agora em reuniões privadas**: controla se um usuário pode iniciar uma reunião privada instantânea.

> [!NOTE]
> Se a reunião foi enviada por um representante, que recebeu permissões para enviar convites de reunião em nome de outra pessoa, como um gerente, a configuração da política de reunião será aplicada à pessoa que concedeu permissão (o gerente).

## <a name="channel-meetings"></a>Reuniões de canal

Se você tiver requisitos de conformidade que exigem que somente pessoas específicas iniciem reuniões instantâneas de canal e agendem reuniões de canal, você pode criar ou atualizar sua política de reunião para restringir essas configurações. Em seguida, você pode criar uma política separada atribuída aos usuários que você deseja iniciar reuniões instantâneas de canal e agendar reuniões de canal.

1. No centro de administração do Teams, acesse **as políticas de** > **Reunião de** Reuniões e escolha a política que você deseja atualizar. Para criar uma nova política, clique em **Adicionar**.
1. Em **Geral**, alterne o seguinte:
    1. Se você quiser restringir quem pode iniciar reuniões instantâneas em um canal, alterne **Reunir agora em canais** para **Desativado**.
    1. Se você quiser restringir quem pode agendar reuniões em um canal, alterne o agendamento de **reunião do Channel** para **Desativado**.
1. Pressione **Salvar** na parte inferior da página.

## <a name="private-meetings"></a>Reuniões particulares

Se você tiver requisitos de conformidade que exigem que apenas pessoas específicas iniciem reuniões privadas instantâneas e agendem reuniões privadas, você pode criar ou atualizar suas políticas de reunião para restringir essas configurações. Em seguida, você pode criar uma política separada atribuída aos usuários que deseja iniciar reuniões instantâneas e agendar reuniões privadas.

1. No centro de administração do Teams, acesse **as políticas de** > **Reunião de** Reuniões e escolha a política que você deseja atualizar. Para criar uma nova política, clique em **Adicionar**.
1. Em **Geral**, alterne o seguinte:
    1. Se você quiser restringir quem pode iniciar reuniões privadas instantâneas, alterne **Reunir agora em reuniões privadas** para **Desativado**.
    1. Se você quiser restringir quem pode agendar reuniões privadas em um canal, alterne  o agendamento de reuniões privadas e o **suplemento do Outlook** para **Desativado**.
1. Pressione **Salvar** na parte inferior da página.

## <a name="turning-off-meeting-policy-settings"></a>Desativando as configurações de política de reunião

Depois que qualquer uma dessas configurações de política de reunião for desativada, qualquer usuário atribuído à política não poderá iniciar ou agendar reuniões desse tipo. Os links de ingresso na reunião e as IDs de conferência de todas as reuniões existentes desse tipo que o usuário tinha iniciado ou agendado anteriormente não funcionarão. (As conversas, arquivos, quadros de comunicações, gravações, transcrições e outros conteúdos relacionados à reunião são mantidos e os usuários ainda podem accessá-los.)

Se uma configuração de política de reunião estiver desativada e ativada novamente para um usuário, todas as reuniões agendadas anteriormente organizadas pelo usuário se tornarão ativas e as pessoas poderão ingressá-las usando o link de ingresso na reunião ou por telefone.

## <a name="related-topics"></a>Tópicos relacionados

[Alterar a data de expiração da reunião – controles do usuário final](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Gerenciar políticas de reunião no Teams](meeting-policies-overview.md)

[Atribua políticas a seus usuários no Teams](policy-assignment-overview.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Limites e especificações do Microsoft Teams](/microsoftteams/limits-specifications-teams)
