---
title: Configurar e gerenciar a moderação do canal
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como configurar canais para moderação em Microsoft Teams, incluindo como adicionar membros da equipe como moderadores de canal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5e1a58f7f09c94ae5178add3897b84e3571eef03
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726130"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Configurar e gerenciar a moderação de canal Microsoft Teams

Em Microsoft Teams, os proprietários de equipe podem ativar a moderação para um canal padrão para controlar quem pode iniciar novas postagens e responder a postagens nesse canal.

Os proprietários da equipe também podem adicionar membros da equipe como moderadores. Um proprietário de equipe pode não ter a experiência do assunto no nível do canal para melhor suportar a moderação do canal. Ao permitir que membros específicos da equipe moderam um canal, a responsabilidade de gerenciar conteúdo e contexto em um canal é compartilhada entre proprietários de equipe e moderadores de canal. Por exemplo, um proprietário de equipe pode adicionar proprietários de negócios ou proprietários de conteúdo como moderadores, o que permite controlar o compartilhamento de informações nesse canal.

> [!NOTE]
> A moderação de canal está disponível para canais padrão. Não está disponível para o canal geral ou para canais privados.

## <a name="what-can-a-channel-moderator-do"></a>O que um moderador de canal pode fazer?

Os moderadores de canal podem:

- Inicie novas postagens no canal. Quando a moderação é ativas para um canal, somente os moderadores podem iniciar novas postagens nesse canal.
- Adicione e remova os membros da equipe como moderadores a um canal. Lembre-se de que, por padrão, os proprietários de equipe são moderadores de canal e não podem ser removidos.
- Controle se os membros da equipe podem responder a mensagens de canal existentes e se bots e conectores podem enviar mensagens de canal.

## <a name="scenarios"></a>Cenários

Aqui estão alguns exemplos de como sua organização pode usar a moderação de canal Teams.

### <a name="use-a-channel-as-an-announcement-channel"></a>Usar um canal como canal de anúncio

A equipe de Marketing usa um canal específico para compartilhar os principais comunicados e entregas do projeto. Às vezes, os membros da equipe postam conteúdo no canal que pertence mais adequadamente a outros canais. O proprietário da equipe deseja restringir o compartilhamento de informações no canal apenas para anúncios para que os membros da equipe possam usar esse canal para se manterem atentos ao que é importante.

Nesse cenário, o proprietário da equipe adiciona leads de Marketing como moderadores para que eles possam postar anúncios no canal e desligar a capacidade de os membros da equipe responderem às mensagens nesse canal.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Usar um canal para discussões de classe em Teams para Educação

Em Teams para Educação, um professor de ciências deseja usar um canal para envolver os alunos em discussões focadas em tópicos específicos da sala de aula.

Nesse cenário, o professor permite que seus assistentes de ensino moderam o canal. Os assistentes de ensino podem criar novas postagens para iniciar e conduzir discussões com os alunos.

## <a name="manage-channel-moderation"></a>Gerenciar moderação de canal

Em Teams, vá para o canal, clique em **Mais opções...**  >  **Gerenciar canal**. A partir daqui, você pode ativar e desativar a moderação, adicionar membros da equipe como moderadores e definir preferências.

Moderação de canal é uma configuração por canal. Não há configuração no nível de locatário para moderação de canal. Se quiser que adicionemos uma configuração de moderação de canal no nível de locatário, solicite-a [Teams UserVoice](https://microsoftteams.uservoice.com/).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![preferências para managing-channel-moderation-in-teams.](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>Ativar ou desativar a moderação de um canal

Por padrão, a moderação está desligada, o que significa que as configurações de canal usuais se aplicam aos proprietários da equipe e aos membros da equipe. Por exemplo, você pode restringir novas postagens apenas para membros da equipe ou permitir que todos, incluindo convidados, iniciem novas postagens.

Para ativar a moderação de um canal, em **Moderação de Canal,** **clique** em . Quando a moderação do canal está em, somente moderadores podem iniciar novas postagens. 

### <a name="add-or-remove-channel-moderators"></a>Adicionar ou remover moderadores de canal

Em **Who os moderadores?**, clique em **Gerenciar** e, em seguida, adicionar ou remover membros da equipe como moderadores. Os proprietários e moderadores de equipe podem adicionar e remover outros moderadores.  

### <a name="set-team-member-permissions"></a>Definir permissões de membro da equipe

Em **Permissões de membro da equipe,** selecione as caixas de seleção ao lado das atividades que você deseja permitir.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral de equipes e canais no Teams](teams-channels-overview.md)
