---
title: Atribuir proprietários de equipe e membros no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Saiba como atribuir funções e permissões de proprietários membros de equipe no Microsoft Teams, inclusive permissões para criar equipes.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c7343f294f18d5aaacf01059459524cdd2700a2
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569953"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Atribuir proprietários de equipe e membros no Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Em Microsoft Teams, existem duas funções de usuário: **proprietário** e do **membro**. Por padrão, um usuário que cria uma nova equipe recebe o status de proprietário. Se uma equipe for criada a partir de um Grupo existente do Office 365, as permissões são herdadas.

A tabela abaixo mostra a diferença em permissões entre um proprietário e um membro.


|                                   | Proprietário da equipe | Membro da equipe |
|-----------------------------------|------------|-------------|
|          **Criar equipe**          |    Sim<sup>1</sup>     |     Não      |
|          **Sair da equipe**           |    Sim     |     Sim     |
|  **Editar nome/descrição da equipe**   |    Sim     |     Não      |
|          **Excluir equipe**          |    Sim     |     Não      |
|          **Adicionar canal**          |    Sim     |    Sim<sup>2</sup>|
| **Editar nome/descrição do canal** |    Sim     |    Sim<sup>2</sup>|
|        **Excluir canal**         |    Sim     |    Sim<sup>2</sup>|
|          **Adicionar membros**          |  Sim<sup>3</sup>   |     Nenhum<sup>4</sup>    |
|          **Solicitação para adicionar membros**          |  N/D   |     Sim<sup>5</sup>     |
|           **Adicionar guias**            |    Sim     |    Sim<sup>2</sup>|
|        **Adicionar conectores**         |    Sim     |    Sim<sup>2</sup>|
|           **Adicionar bots**            |    Sim     |    Sim<sup>2</sup>|

<sup>1</sup> proprietários de equipe possam criar equipes, a menos que eles tenham sido impedidos de fazer isso. Consulte "Permissões para criar equipes" abaixo.
>
<sup>2</sup> desses itens podem ser desativados por um proprietário em um nível de equipe, caso em que os membros não terá acesso a eles.

<sup>3</sup> depois de adicionar um membro para uma equipe, um proprietário também pode promover um membro ao status de proprietário. Também é possível para um proprietário a serem rebaixados suas próprias status do membro.

<sup>4</sup> membros da equipe podem adicionar outros membros para uma equipe pública.

<sup>5</sup> enquanto um membro da equipe não pode adicionar membros diretamente para uma equipe privada, eles podem solicitar uma pessoa a ser adicionado a uma equipe que elas já membro do. Quando um membro solicita uma pessoa a ser adicionado a uma equipe, os proprietários de equipe recebem um alerta que têm uma solicitação pendente que eles podem aceitar ou recusar.



> [!NOTE]
> Os Proprietários também podem fazer com que outros membros se tornem proprietários na opção Visualizar equipes. Uma equipe pode ter até 100 proprietários. É recomendável ter pelo menos alguns proprietários para gerenciar o Teams, isso também evitará grupos órfãos, caso o único proprietário saia da organização. Para obter mais informações sobre grupos órfãos, consulte [Atribuir novo proprietário a um grupo órfão](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Permissões para criar equipes
---------------------------

Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Office 365 e, portanto, um time no Microsoft Teams. Você pode ter um controle mais rígido e restringir a criação de novas equipes e, assim, a criação de novos grupos do Office 365 ao delegar direitos de criação e gerenciamento de grupos a um conjunto de usuários. Para obter instruções, consulte [Manage quem pode criar grupos do Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Ícone de ponto de decisão.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Ponto de decisão         |Todos os usuários do Microsoft Teams terão permissão para criar equipes (recomendado)?         |
| ![Ícone de próximos passos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Próximos passos         |Modifique as permissões padrão para quem pode criar grupos do Office 365, caso precise limitar as pessoas que podem criar equipes         |
