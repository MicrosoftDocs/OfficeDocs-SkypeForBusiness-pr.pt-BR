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
localization_priority: Normal
search.appverid: MET150
description: Saiba como configurar canais para moderação no Microsoft Teams, incluindo como adicionar membros da equipe como moderadores de canal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9598723d1a88826d1efa5fb487d02fc93aa5d4e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822891"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Configurar e gerenciar a moderação de canal no Microsoft Teams

No Microsoft Teams, os proprietários da equipe podem ativar a moderação para um canal padrão para controlar quem pode iniciar novas postagens e responder a postagens nesse canal.

Os proprietários da equipe também podem adicionar membros da equipe como moderadores. Um proprietário de equipe pode não ter a especialização no assunto no nível do canal para melhor moderação do canal de suporte. Ao permitir que membros específicos da equipe moderam um canal, a responsabilidade de gerenciar conteúdo e contexto em um canal é compartilhada entre proprietários de equipe e moderadores de canal. Por exemplo, um proprietário de equipe pode adicionar proprietários de negócios ou proprietários de conteúdo como moderadores, o que permite controlar o compartilhamento de informações nesse canal.

> [!NOTE]
> A moderação de canal está disponível para canais padrão. Ele não está disponível para o canal Geral ou canais privados.

## <a name="what-can-a-channel-moderator-do"></a>O que um moderador de canal pode fazer?

Os moderadores de canal podem:

- Inicie novas postagens no canal. Quando a moderação está 2010 para um canal, somente os moderadores podem iniciar novas postagens nesse canal.
- Adicione e remova membros da equipe como moderadores a um canal. Lembre-se de que, por padrão, os proprietários da equipe são moderadores de canal e não podem ser removidos.
- Controle se os membros da equipe podem responder a mensagens de canal existentes e se bots e conectores podem enviar mensagens de canal.

## <a name="scenarios"></a>Cenários

Aqui estão alguns exemplos de como sua organização pode usar a moderação de canal no Teams.

### <a name="use-a-channel-as-an-announcement-channel"></a>Usar um canal como um canal de anúncio

A equipe de Marketing usa um canal específico para compartilhar os principais comunicados e entregas do projeto. Às vezes, os membros da equipe postam conteúdo no canal que pertence mais adequadamente a outros canais. O proprietário da equipe deseja restringir o compartilhamento de informações no canal apenas para comunicados para que os membros da equipe possam usar esse canal para se manter por dentro do que é importante.

Nesse cenário, o proprietário da equipe adiciona as lideranças de Marketing como moderadores para que eles possam postar anúncios no canal e desligar a capacidade de os membros da equipe responderem às mensagens nesse canal.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Usar um canal para discussões de classe no Teams for Education

No Teams for Education, um professor de ciências deseja usar um canal para envolver os alunos em discussões focadas em tópicos específicos da sala de aula.

Nesse cenário, o professor permite que seus assistentes de ensino moderam o canal. Os assistentes de ensino podem criar novas postagens para iniciar e conduzir discussões com os alunos.

## <a name="manage-channel-moderation"></a>Gerenciar moderação de canal

No Teams, vá para o canal, clique **em Mais opções...**  >  **Gerenciar canal**. A partir daqui, você pode ativar e desativar a moderação, adicionar membros da equipe como moderadores e definir preferências.

A moderação de canal é uma configuração por canal. Não há configuração no nível do locatário para moderação de canal. Se você quiser que adicionemos uma configuração de moderação de canal no nível do locatário, solicite-a no [Teams UserVoice](https://microsoftteams.uservoice.com/).

![manage-channel-moderation-in-teams-preferences.png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>Ativar ou desativar a moderação para um canal

Por padrão, a moderação está desligada, o que significa que as configurações de canal usuais se aplicam aos proprietários e membros da equipe. Por exemplo, você pode restringir novas postagens apenas para membros da equipe ou permitir que todos, incluindo convidados, iniciem novas postagens.

Para ativar a moderação para um canal, em **Moderação de Canal,** clique **em .** Quando a moderação do canal está 1, somente os moderadores podem iniciar novas postagens. 

### <a name="add-or-remove-channel-moderators"></a>Adicionar ou remover moderadores de canal

Em **Quem são os moderadores?**, clique em **Gerenciar** e, em seguida, adicionar ou remover membros da equipe como moderadores. Os proprietários e moderadores de equipe podem adicionar e remover outros moderadores.  

### <a name="set-team-member-permissions"></a>Definir permissões de membro da equipe

Em **Permissões de membro da equipe,** marque as caixas de seleção ao lado das atividades que você deseja permitir.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral de equipes e canais no Teams](teams-channels-overview.md)
