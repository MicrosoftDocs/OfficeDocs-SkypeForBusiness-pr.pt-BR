---
title: Configurar e gerenciar a moderação de canal
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Saiba como configurar canais para moderação no Microsoft Teams, incluindo como adicionar membros da equipe como moderadores de canal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52fb88d6371c033713c5b14d96ecf2a9211420b0
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562360"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Configurar e gerenciar a moderação de canal no Microsoft Teams

No Microsoft Teams, os proprietários da equipe podem ativar a moderação de um canal padrão para controlar quem pode iniciar novas postagens e responder a postagens nesse canal.

Os proprietários da equipe também podem adicionar membros da equipe como moderadores. Um proprietário de equipe pode não ter a experiência no assunto no nível do canal para dar melhor suporte à moderação do canal. Ao permitir que membros específicos da equipe moderam um canal, a responsabilidade de gerenciar conteúdo e contexto em um canal é compartilhada entre proprietários de equipe e moderadores de canal. Por exemplo, um proprietário de equipe pode adicionar proprietários de negócios ou proprietários de conteúdo como moderadores, o que permite controlar o compartilhamento de informações nesse canal.

> [!NOTE]
> A moderação de canal está disponível para canais padrão. Ele não está disponível para o canal Geral ou para canais privados ou compartilhados.

## <a name="what-can-a-channel-moderator-do"></a>O que um moderador de canal pode fazer?

Os moderadores de canal podem:

- Inicie novas postagens no canal. Quando a moderação é ativada para um canal, somente moderadores podem iniciar novas postagens nesse canal.
- Adicionar e remover membros da equipe como moderadores a um canal. Tenha em mente que, por padrão, os proprietários da equipe são moderadores de canal e não podem ser removidos.
- Controle se os membros da equipe podem responder a mensagens de canal existentes e se bots e conectores podem enviar mensagens de canal.

## <a name="scenarios"></a>Cenários

Aqui estão alguns exemplos de como sua organização pode usar a moderação de canal no Teams.

### <a name="use-a-channel-as-an-announcement-channel"></a>Usar um canal como um canal de anúncio

A equipe de Marketing usa um canal específico para compartilhar os principais comunicados e entregas do projeto. Às vezes, os membros da equipe postam conteúdo no canal que pertence mais adequadamente a outros canais. O proprietário da equipe deseja restringir o compartilhamento de informações no canal a apenas comunicados para que os membros da equipe possam usar esse canal para se manter por dentro do que é importante.

Nesse cenário, o proprietário da equipe adiciona clientes potenciais de Marketing como moderadores para que eles possam postar comunicados no canal e desativa a capacidade de os membros da equipe responderem às mensagens nesse canal.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Usar um canal para discussões de classe no Teams para Educação

No Teams para Educação, um professor de ciências deseja usar um canal para envolver os alunos em discussões focadas em tópicos específicos da sala de aula.

Nesse cenário, o professor permite que seus assistentes de ensino moderam o canal. Os assistentes de ensino podem criar novas postagens para iniciar e conduzir discussões com os alunos.

## <a name="manage-channel-moderation"></a>Gerenciar moderação de canal

No Teams, acesse o canal, clique em **Mais opções...** >  **Gerenciar canal**. A partir daqui, você pode ativar e desativar a moderação, adicionar membros da equipe como moderadores e definir preferências.

Moderação de canal é uma configuração por canal. Não há nenhuma configuração no nível do locatário para moderação de canal. Se você quiser que adicionemos uma configuração de moderação de canal no nível do locatário, solicite-a no [portal de Comentários do Teams](https://feedbackportal.microsoft.com/feedback/forum/ad198462-1c1c-ec11-b6e7-0022481f8472).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![preferências para gerenciar-channel-moderation-in-teams.](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>Ativar ou desativar a moderação de um canal

Por padrão, a moderação está desativada, o que significa que as configurações de canal usuais se aplicam aos proprietários da equipe e aos membros da equipe. Por exemplo, você pode restringir novas postagens somente aos membros da equipe ou permitir que todos, incluindo convidados, iniciem novas postagens.

Para ativar a moderação de um canal, em **Moderação de canal**, clique **em Ativado**. Quando a moderação do canal está ativada, somente moderadores podem iniciar novas postagens. 

### <a name="add-or-remove-channel-moderators"></a>Adicionar ou remover moderadores de canal

Em **Quem são os moderadores?**, clique em **Gerenciar** e adicione ou remova membros da equipe como moderadores. Os proprietários e moderadores de equipe podem adicionar e remover outros moderadores.  

### <a name="set-team-member-permissions"></a>Definir permissões de membro da equipe

Em **Permissões de membro da equipe**, marque as caixas de seleção ao lado das atividades que você deseja permitir.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral de equipes e canais no Teams](teams-channels-overview.md)
