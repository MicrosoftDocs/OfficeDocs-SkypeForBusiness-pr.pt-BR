---
title: Gerenciar equipes no centro de administração do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Saiba como exibir ou atualizar suas equipes no centro de administração do Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c205c8d3b4f57935c1882530815643a90357d1aa
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548266"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gerenciar equipes no centro de administração do Microsoft Teams
==========================================


## <a name="overview"></a>Visão geral

Como um administrador de ti, talvez seja necessário exibir ou atualizar as equipes que a sua organização configurou para colaboração, ou talvez seja necessário executar ações de correção, como a atribuição de proprietários para equipes sem proprietário. Você pode gerenciar as equipes usadas em sua organização por meio do módulo do Microsoft Teams PowerShell e do centro de administração do Microsoft Teams. Para obter recursos de administração plena usando esses dois conjuntos de ferramentas, você deve certificar-se de que recebeu uma das funções a seguir:

- Administrador global
- Administrador de Serviço de Equipes

Você pode saber mais sobre as funções de administrador no Teams em [usar funções de administração do Microsoft Teams para gerenciar o Teams](using-admin-roles.md)e ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).  

Este artigo fornece uma visão geral das ferramentas de gerenciamento para Teams no centro de administração do Microsoft Teams.

## <a name="teams-overview-grid"></a>Grade de visão geral do teams

As ferramentas de gerenciamento do teams **** estão sob o nó Teams no centro de administração do Microsoft Teams. (No centro de administração, selecione **Teams** > **Manage Teams**.) Cada equipe tem o suporte de um grupo do Office 365, e esse nó fornece um modo de exibição de grupos que foram habilitados para o Microsoft Teams na sua organização.

![Captura de tela da grade de visão geral do teams](media/manage-teams-in-modern-portal-image1.png)  

A grade exibe as seguintes propriedades:

- **Nome da equipe**
- **Canais** – uma contagem de todos os canais da equipe, incluindo o canal geral padrão.
- **Usuários** – uma contagem do total de usuários, incluindo proprietários, convidados e membros do seu locatário.
- **Proprietários** -uma contagem de proprietários para esta equipe.
- **Convidados** -uma contagem de usuários convidados do Azure Active Directory que são membros da equipe.
- **Privacidade** -a visibilidade/acessotype do grupo de backup do Office 365.
- **Status** -o status arquivado ou ativo para esta equipe.  Saiba mais sobre o arquivamento de equipes no [arquivamento ou restauração de uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **GroupId** -o GroupId exclusivo do grupo de backup do Office 365
- **Classificação** – a classificação (se usada em sua organização) atribuída ao grupo de backup do Office 365.  Saiba mais sobre classificações em [criar classificações para grupos do Office em sua organização](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).
- **Descrição** -a descrição definida para o grupo de backup do Office 365

### <a name="search"></a>Pesquisa

A pesquisa atualmente oferece suporte à cadeia de caracteres "começa com" e pesquisa o campo **nome da equipe** .

### <a name="edit"></a>Editar

Você pode editar as configurações específicas do grupo e da equipe selecionando uma equipe na grade e, em seguida, selecionando o botão **Editar** .

![Captura de tela das opções de editar equipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>Perfil de equipe

Você pode navegar até a página perfil da equipe de qualquer equipe na grade principal do teams Overview clicando no nome da equipe. A página perfil da equipe mostra os membros, os proprietários e os convidados que pertencem à equipe (e seu grupo de O365 de apoio), bem como os canais e as configurações da equipe. Na página perfil da equipe, você pode:

- Adicionar ou remover membros e proprietários.
- Adicionar ou remover canais (Observe que não é possível remover o canal geral).
- Atualizar configurações de equipe e grupo.
 
![Captura de tela de um exemplo de perfil de equipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>Como fazer alterações em equipes

Você pode alterar os seguintes elementos de uma equipe:
- **Usuários na equipe** -você pode adicionar ou remover membros e promover ou rebaixar proprietários
- **Canais** – você pode adicionar novos canais ou remover canais existentes.  Não é possível excluir o canal "geral" padrão e, depois de criado, você só pode editar o nome do canal e não a descrição.
- **Nome da equipe**
- **Descrição da equipe**
- **Privacidade da equipe** -público ou privado
- **Classificação da equipe** -apoiada pelas suas classificações de grupo do Office 365
- **Configurações de membro da equipe** – selecionar configurações de membro da equipe

## <a name="other-supported-changes-to-teams"></a>Outras alterações com suporte no Teams

- **Excluir** – excluir uma equipe é uma exclusão suave da equipe e do grupo correspondente do Office 365.  Para restaurar uma equipe excluída incorretamente, siga as instruções em [restaurar um grupo do Office 365 excluído](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).
- **Arquivo morto** : o arquivamento de uma equipe coloca a equipe em modo somente leitura no Microsoft Teams.  Como administrador, você pode arquivar e Desarquivar equipes em nome de sua organização por meio do portal de administração.


As alterações feitas em uma equipe são registradas. Se você estiver modificando as configurações de grupo (alterando o nome, a descrição, a foto, a classificação, a classificação ou os membros da equipe), essas alterações serão atribuídas a você pelo pipeline de auditoria. Se você estiver executando ações em configurações específicas de equipes, suas alterações serão rastreadas e atribuídas a você no canal geral da equipe.

## <a name="troubleshooting"></a>Solução de problemas

**Problema: equipes ausentes da grade de visão geral da equipe**

Quando você insere o centro de administração do Microsoft Teams, na opção **equipes** algumas de suas equipes estão ausentes da listagem na grade de visão geral do teams.

**Causa**: esse problema ocorre quando a equipe era incorretamente (ou ainda não) Profile pelo sistema, que pode levar a uma propriedade ausente para ser reconhecida.

**Resolução: definir manualmente a propriedade como o valor correto via MS Graph**

Substitua **{GroupId}** na consulta para o GroupId em questão real, que você pode obter por meio do PowerShell do Exchange Online, com o cmdlet **"[Get-](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)unificado"** , como o atributo "**ExternalDirectoryObjectId**".

1. [Gerenciador de gráficos](https://developer.microsoft.com/en-us/graph/graph-explorer) do Access

2. Entrar no explorador de gráficos no menu à esquerda

3. Alterar a linha da consulta para: PATCH > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["equipe"]}

5. Execute a consulta no canto superior direito.

6. Confirmar que a equipe é exibida corretamente no centro de administração do Microsoft Teams-visão geral da equipe


## <a name="learn-more"></a>Saiba mais

[Referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Funções de administrador no Microsoft Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

