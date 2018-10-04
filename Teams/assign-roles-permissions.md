---
title: Atribuir membros em Microsoft Teams e proprietários de equipe
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Saiba como atribuir funções e permissões de proprietários membros de equipe no Microsoft Teams, inclusive permissões para criar equipes.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 523530647834fa2c54d18d983f25733bbe25d1be
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372645"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Atribuir membros em Microsoft Teams e proprietários de equipe
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Em Microsoft Teams, existem duas funções de usuário: **proprietário** e do **membro**. Por padrão, um usuário que cria uma nova equipe recebe o status de proprietário. Se uma equipe for criada a partir de um Grupo existente do Office 365, as permissões são herdadas.

A tabela abaixo mostra as diferenças de permissão entre um proprietário e um membro:


|                                   | Proprietário da equipe | Membro da equipe |
|-----------------------------------|------------|-------------|
|          **Criar equipe**          |    Sim     |     Não      |
|          **Sair da equipe**           |    Sim     |     Sim     |
|  **Editar nome/descrição da equipe**   |    Sim     |     Não      |
|          **Excluir equipe**          |    Sim     |     Não      |
|          **Adicionar canal**          |    Sim     |    Sim\*    |
| **Editar nome/descrição do canal** |    Sim     |    Sim\*    |
|        **Excluir canal**         |    Sim     |    Sim\*    |
|          **Adicionar membros**          |  Sim\*\*   |     Não      |
|           **Adicionar guias**            |    Sim     |    Sim\*    |
|        **Adicionar conectores**         |    Sim     |    Sim\*    |
|           **Adicionar bots**            |    Sim     |    Sim\*    |

\*Esses itens podem ser desativados por um proprietário em um nível de equipe, caso em que os membros não terá acesso a eles.

\*\*Após adicionar um membro a uma equipe, o Proprietário também pode promover um Membro para o status de Proprietário. Também é possível para um Proprietário rebaixar seu próprio status para o status de Membro.



> [!NOTE]
> Os Proprietários também podem fazer com que outros membros se tornem proprietários na opção Visualizar equipes. Uma equipe pode ter até 100 proprietários. É recomendável ter pelo menos alguns proprietários para gerenciar o Teams, isso também evitará grupos órfãos, caso o único proprietário saia da organização. Para obter mais informações sobre grupos órfãos, consulte [Atribuir novo proprietário a um grupo órfão](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Permissões para criar equipes
---------------------------

Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Office 365 e, portanto, um time no Microsoft Teams. Você pode ter um controle mais rígido e restringir a criação de novas equipes e, assim, a criação de novos grupos do Office 365 ao delegar direitos de criação e gerenciamento de grupos a um conjunto de usuários. Para obter instruções, consulte [Manage quem pode criar grupos do Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Ícone de ponto de decisão.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Ponto de decisão         |Todos os usuários do Microsoft Teams terão permissão para criar equipes (recomendado)?         |
| ![Ícone de próximos passos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Próximos passos         |Modifique as permissões padrão para quem pode criar grupos do Office 365, caso precise limitar as pessoas que podem criar equipes         |
