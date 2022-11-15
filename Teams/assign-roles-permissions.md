---
title: Atribuir proprietários e membros da equipe no centro de administração do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: e0f259a7a24552988d4eca503deeb9151dde144d
ms.sourcegitcommit: 0760416ee0bead3ada93f4d37f8aebc74222bd3c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2022
ms.locfileid: "69019407"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams-admin-center"></a>Atribuir proprietários e membros da equipe no centro de administração do Microsoft Teams

**Proprietário** e **membro** são as duas funções de usuário no Microsoft Teams. O usuário que cria uma nova equipe recebe o status de proprietário por padrão. Proprietários e membros têm diferentes tipos de permissões e recursos ao interagir com uma equipe e seus canais. Confira [Visão geral de equipes e canais no Microsoft Teams](teams-channels-overview.md) para saber mais sobre funções no Teams.

> [!NOTE]
> Se uma equipe for criada a partir de um grupo existente do Microsoft 365, as permissões serão herdadas.

## <a name="assign-a-user-role-in-teams-admin-center"></a>Atribuir uma função de usuário no centro de administração do Teams

1. No centro de administração do Teams, expanda **o Teams** e **selecione Gerenciar equipes**.
2. Selecione o nome da equipe na coluna nome da exibição.
3. Na guia Membros, você pode adicionar ou remover membros e atribuir funções de proprietário e moderador aos membros.

## <a name="restrict-permission-to-create-teams"></a>Restringir permissão para criar equipes

Todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Microsoft 365 e uma equipe no Microsoft Teams. Restrinja os usuários de criar novas equipes e grupos do Microsoft 365 delegando direitos de criação e gerenciamento de grupo a um conjunto de usuários. Se essa restrição estiver ativa, nenhum dos proprietários ou membros da equipe poderá criar novas equipes. Para obter mais informações, confira [Gerenciar quem pode criar Grupos do Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="user-permissions-based-on-assigned-roles"></a>Permissões de usuário com base em funções atribuídas

A tabela abaixo mostra as diferenças de permissão entre um proprietário e um membro:

### <a name="teams"></a>Teams

|Tarefas do Teams| Proprietário da equipe | Membro da equipe |
|---------|---------|---------|
|Equipe Criar/Excluir  |    Sim     |     Não    |
|Editar nome/descrição da equipe   |     Sim    |     Não     |
|Adicionar membros à equipe privada    |     Sim    |  Não |
|Adicionar membros à equipe pública    |     Sim    |     Sim   |
|Solicitar para adicionar novo membro   |     Não disponível    |    Sim   |
|Promover/Demote status do usuário | Sim | Não |
|Sair da equipe  |    Sim     |     Sim    |
|Adicionar/Remover aplicativos   |     Sim    |     Sim, se habilitado pelo proprietário da equipe     |

### <a name="channels"></a>Canais

|***Tarefas de canal padrão** _ | _ *Proprietário da equipe** | **Membro da Equipe**|
|----|----|----|
|Canal Criar/Excluir  |     Sim    |    Sim, se habilitado pelo proprietário da equipe      |
|Editar nome/descrição do canal    |    Sim     |     Sim, se habilitado pelo proprietário da equipe    |
|***Tarefas de canal privado***|
|Criar um canal    |    Sim     |    Sim, se habilitado pelo proprietário da equipe      |
|Excluir canal    |    Sim     |    Não     |
|Editar nome/descrição do canal |     Não    |    Não disponível     |
|***Tarefas de canal compartilhado***
|Criar um canal    |    Sim     |     Não    |
|Excluir canal | Sim | Não |
|Editar nome/descrição do canal    |    Não     |     Não    |
