---
title: Atribuir proprietários de equipe e membros no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Saiba como atribuir funções e permissões de proprietários membros de equipe no Microsoft Teams, inclusive permissões para criar equipes.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6757f7200535dc8fb687915ec033712b2654723b
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37516441"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Atribuir proprietários de equipe e membros no Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

No Microsoft Teams há duas funções de usuário: **proprietário** e **membro**. Por padrão, um usuário que cria uma nova equipe recebe o status de proprietário. Além disso, os proprietários e membros podem ter recursos moderadores para um canal (desde que a moderação tenha sido configurada). Se uma equipe for criada a partir de um Grupo existente do Office 365, as permissões são herdadas.

A tabela a seguir mostra a diferença nas permissões entre um proprietário e um membro.


|                                   | Proprietário da equipe | Membro da equipe |
|-----------------------------------|------------|-------------|
|          **Criar equipe**          |    Sim<sup>1</sup>     |     Não      |
|          **Sair da equipe**           |    Sim     |     Sim     |
|  **Editar nome/descrição da equipe**   |    Sim     |     Não      |
|          **Excluir equipe**          |    Sim     |     Não      |
|          **Adicionar canal**          |    Sim     |    Sim<sup>2</sup>|
| **Editar nome/descrição do canal** |    Sim     |    Sim<sup>2</sup>|
|        **Excluir canal**         |    Sim     |    Sim<sup>2</sup>|
|          **Adicionar membros**          |  Sim<sup>3</sup>   |     Sem<sup>4</sup>    |
|          **Solicitação para adicionar membros**          |  N/D   |     Sim<sup>5</sup>     |
|           **Adicionar guias**            |    Sim     |    Sim<sup>2</sup>|
|        **Adicionar conectores**         |    Sim     |    Sim<sup>2</sup>|
|           **Adicionar bots**            |    Sim     |    Sim<sup>2</sup>|

<sup>1</sup> os proprietários da equipe podem criar equipes, a menos que elas tenham sido limitadas de fazê-lo. [Permissões para criar equipes](#permissions-to-create-teams) abaixo.<br>
><sup>2</sup> um proprietário pode desativar esses itens no nível da equipe, caso em que os membros não tenham acesso a eles.<br>
<sup>3</sup> após adicionar um membro a uma equipe, um proprietário também pode promover um membro ao status de proprietário. Também é possível que um proprietário rebaixe seu próprio status para um membro.<br>
<sup>4</sup> os membros da equipe podem adicionar outros membros a uma equipe pública.<br>
<sup>5</sup> embora um membro da equipe não possa adicionar membros diretamente a uma equipe privada, ele pode solicitar que alguém seja adicionado a uma equipe da qual eles já são membros. Quando um membro solicita que alguém seja adicionado a uma equipe, os proprietários da equipe recebem um alerta de que eles têm uma solicitação pendente que eles podem aceitar ou recusar.

> [!NOTE]
> Os proprietários podem fazer outros proprietários de membros na opção **Exibir equipes** . Uma equipe pode ter até 100 proprietários. Recomendamos que você tenha pelo menos alguns proprietários para ajudar a gerenciar a equipe; Isso também impedirá grupos órfãos se um único proprietário deixar sua organização. Para obter mais informações sobre grupos órfãos, consulte [Atribuir novo proprietário a um grupo órfão](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

## <a name="moderator-capabilities"></a>Recursos do moderador

Além de outros recursos, os proprietários e membros da equipe podem ter recursos moderadores para um canal (desde que a moderação esteja ativada para uma equipe). Os moderadores podem iniciar novas postagens em um canal e controlar se os membros da equipe podem responder às mensagens de canal existentes. Eles também podem controlar se os bots e conectores podem enviar mensagens de canal.

Os recursos do moderador são atribuídos no nível de canal. Os proprietários da equipe têm recursos moderadores por padrão. Os membros da equipe têm recursos moderadores desativados por padrão, mas um proprietário da equipe pode oferecer recursos moderadores para um canal para um membro da equipe. Os moderadores dentro de um canal podem adicionar e remover outros moderadores nesse canal.

Para obter mais informações sobre os recursos do moderador, consulte [configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md).

## <a name="assign-a-user-role"></a>Atribuir uma função de usuário

Para atribuir uma função de usuário, no Teams, selecione o nome da equipe e clique em **mais opções** > **Gerenciar equipe**. Na guia **Membros** , você pode adicionar membros e escolher proprietários e moderadores (se tiver permissões suficientes). Para obter mais informações, consulte [alterar as configurações da equipe no](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)Microsoft Teams.

## <a name="permissions-to-create-teams"></a>Permissões para criar equipes

Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Office 365 e, portanto, um time no Microsoft Teams. Você pode ter um controle mais rígido e restringir a criação de novas equipes e, assim, a criação de novos grupos do Office 365 ao delegar direitos de criação e gerenciamento de grupos a um conjunto de usuários. Para obter instruções, consulte [gerenciar quem pode criar grupos do Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Um ícone representando um ponto de decisão](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Ponto de decisão         |Todos os usuários do Microsoft Teams terão permissão para criar equipes (recomendado)?         |
| ![Um ícone que representa as próximas etapas](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Próximos passos         |Modifique as permissões padrão para quem pode criar grupos do Office 365, caso precise limitar as pessoas que podem criar equipes         |
