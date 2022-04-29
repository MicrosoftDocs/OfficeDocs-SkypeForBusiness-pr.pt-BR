---
title: Atribuir proprietários de equipe e membros no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Saiba como atribuir funções e permissões de proprietários membros de equipe no Microsoft Teams, inclusive permissões para criar equipes.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76ca4a5dfd6d120b71e23d899ec9c7749db99827
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125486"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams"></a>Atribuir proprietários de equipe e membros no Microsoft Teams

No Microsoft Teams, existem duas funções: **proprietário** e **membro**. Por padrão, um usuário que cria uma nova equipe recebe o status de proprietário. Além disso, os proprietários e membros podem ter recursos moderadores para um canal (desde que a moderação tenha sido configurada). Se uma equipe for criada de um grupo de Microsoft 365 existente, as permissões serão herdadas.

A tabela abaixo mostra as diferenças de permissão entre um proprietário e um membro:


|    Tarefas                               | Proprietário da equipe | Membro da equipe |
|-----------------------------------|------------|-------------|
|          **Criar equipe**          |    Sim<sup>1</sup>     |     Não      |
|          **Sair da equipe**           |    Sim     |     Sim     |
|  **Editar nome/descrição da equipe**   |    Sim     |     Não      |
|          **Excluir equipe**          |    Sim     |     Não      |
|          **Adicionar canal padrão**          |    Sim     |    Sim<sup>2</sup>|
| **Editar nome/descrição do canal padrão** |    Sim     |    Sim<sup>2</sup>|
|        **Excluir o canal padrão**         |    Sim     |    Sim<sup>2</sup>|
|          ***Adicionar canal privadol**          |    Sim     |    Sim<sup>2</sup>|
| ***Editar nome/descrição do canal privado** |    Não     |    Não disponível|
|        ***Excluir canal privado**         |    Sim     |    Não|
|          **Adicionar canal compartilhado**          |    Sim     |    Não|
| **Editar nome/descrição do canal compartilhado** |    Não     |    <sup>No6</sup>|
|        **Excluir canal compartilhado**         |    Sim     |    <sup>No6</sup>|
|          **Adicionar membros**          |  Sim<sup>3</sup>   |     Não<sup>4</sup>    |
|          **Solicitação para adicionar membros**          |  N/A   |     Sim<sup>5</sup>     |
|           **Adicionar aplicativos**            |    Sim     |    Sim<sup>2</sup>|

<sup>1</sup> Os proprietários da equipe podem criar equipes, a menos que eles tenham sido restritos. [Permissões para criar equipes](#permissions-to-create-teams) a seguir.<br>
<sup>2</sup> Um proprietário pode desabilitar esses itens no nível da equipe, caso os membros não tenham acesso a eles.<br>
<sup>3</sup> Após adicionar um membro a uma equipe, um proprietário também pode promover um membro para o status de proprietário. Também é possível para um proprietário rebaixar seu próprio status para o status de membro.<br>
<sup>4</sup> Os membros da equipe podem adicionar outros membros a uma equipe pública.<br>
<sup>5</sup> Apesar de um membro da equipe não poder adicionar membros diretamente a uma equipe privada, eles podem solicitar que alguém seja adicionado a uma equipe que já seja membro. Quando um membro solicitar alguém para ser adicionado a uma equipe, os proprietários da equipe recebem um alerta de que eles têm uma solicitação pendente que eles podem aceitar ou recusar.<br>
<sup>6</sup> Se o membro da equipe for um proprietário de canal compartilhado, ele poderá executar essa ação.

*Para saber mais sobre as permissões para canais privados, consulte [Canais privados no Teams](private-channels.md).

> [!NOTE]
> Os proprietários podem fazer com que outros membros se tornem proprietários na opção **Exibir equipes**. Uma equipe pode ter até 100 proprietários. É recomendável ter pelo menos alguns proprietários para gerenciar a equipe, isso também evitará grupos órfãos, caso o único proprietário saia da organização. Para obter mais informações sobre grupos órfãos, consulte [Atribuir novo proprietário a um grupo órfão](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

## <a name="moderator-capabilities"></a>Recursos do moderador

Além de outros recursos, os proprietários e membros da equipe podem ter recursos do moderador para um canal (desde que a moderação esteja habilitada para uma equipe). Os moderadores podem iniciar novas postagens em um canal e controlar se os membros da equipe podem responder às mensagens existentes do canal. Os moderadores também podem controlar se aplicativos com recursos de bots e conectores podem enviar mensagens de canal.

A função de moderador é atribuída no nível do canal. Os proprietários da equipe têm recursos de moderador por padrão. Também por padrão, os membros da equipe não têm a função de moderação ativada, mas o proprietário pode conceder essa função em um canal para um membro. Dentro de um canal, os moderadores podem adicionar e remover outros moderadores.

Para obter mais informações sobre os recursos do moderador, consulte [Configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md).

## <a name="assign-a-user-role"></a>Atribuir uma função de usuário

Para atribuir uma função de usuário, Teams, selecione o nome da equipe e, em seguida, selecione Mais **opções (****...**) > **Gerenciar equipe**. Na guia **Membros**, você pode adicionar membros e escolher proprietários e moderadores (se tiver permissões suficientes). Para obter mais informações, consulte [Alterar as configurações da equipe Teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).

> [!NOTE]
> A **opção Gerenciar equipe** não aparecerá para canais fixados. Selecione o nome da equipe *em Suas equipes* mais abaixo e, em seguida, selecione **Mais** opções (**...**) à direita do nome.

## <a name="permissions-to-create-teams"></a>Permissões para criar equipes

Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Microsoft 365 e, portanto, uma equipe no Microsoft Teams. Você pode ter um controle mais rígido e restringir a criação de novas equipes e, assim, a criação de novos grupos do Microsoft 365 ao delegar direitos de criação e gerenciamento de grupos a um conjunto de usuários. Para obter instruções, consulte [Gerenciar quem pode criar Grupos do Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).
