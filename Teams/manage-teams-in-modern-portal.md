---
title: Gerenciar equipes no centro de administração do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Saiba como exibir ou atualizar suas equipes no centro de administração do Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fea7081ee66cbd7b103f4292f577aaf5d841e11
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37571929"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gerenciar equipes no centro de administração do Microsoft Teams
==========================================

## <a name="overview"></a>Visão geral

Como administrador, talvez você precise exibir ou atualizar as equipes configuradas para colaboração ou pode precisar executar ações de correção, como a atribuição de proprietários para equipes sem proprietário. Você pode gerenciar as equipes usadas em sua organização por meio do módulo do Microsoft Teams PowerShell e do centro de administração do Microsoft Teams. Para obter recursos de administração plena usando esses dois conjuntos de ferramentas, você deve certificar-se de que recebeu uma das funções a seguir:

- Administrador global
- Administrador de Serviço de Equipes

Você pode saber mais sobre as funções de administrador no Teams em [usar funções de administração do Microsoft Teams para gerenciar o Teams](using-admin-roles.md)e ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).

Este artigo fornece uma visão geral das ferramentas de gerenciamento para Teams no centro de administração do Microsoft Teams.

## <a name="teams-overview-grid"></a>Grade de visão geral do teams

As ferramentas de gerenciamento do teams estão sob o nó **Teams** no centro de administração do Microsoft Teams. (No centro de administração, selecione **Teams** > **Manage Teams**.) Cada equipe tem o suporte de um grupo do Office 365, e esse nó fornece um modo de exibição de grupos que foram habilitados para o Microsoft Teams na sua organização.

![Captura de tela da grade de visão geral do teams](media/manage-teams-in-modern-portal-grid.png)  

A grade exibe as seguintes propriedades:

- **Nome da equipe**
- **Canais** – uma contagem de todos os canais da equipe, incluindo o canal geral padrão.
- **Membros da equipe** -uma contagem total de usuários, incluindo proprietários, convidados e membros do seu locatário.
- **Proprietários** -uma contagem de proprietários para esta equipe.
- **Convidados** -uma contagem de usuários convidados do Azure Active Directory que são membros da equipe.
- **Privacidade** -a visibilidade/acessotype do grupo de backup do Office 365.
- **Status** -o status arquivado ou ativo para esta equipe. Saiba mais sobre o arquivamento de equipes em [arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **Descrição** -a descrição do grupo de backup do Office 365.
- **Classificação** – a classificação (se usada em sua organização) atribuída ao grupo de backup do Office 365. Saiba mais sobre classificações em [criar classificações para grupos do Office em sua organização](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).
- **GroupId** -o GroupId exclusivo do grupo de backup do Office 365.

> [!NOTE]
> Se você não vir todas essas propriedades na grade, clique no ícone **Editar colunas** . No painel **Editar colunas** , você pode usar as alternâncias para ativar ou desativar colunas na grade. Quando tiver terminado, clique em **aplicar**.

### <a name="add"></a>Suplementa

Para adicionar uma nova equipe, clique em **Adicionar**. No painel **Adicionar uma nova equipe** , dê um nome e uma descrição para a equipe, defina se deseja torná-la uma equipe privada ou pública e definir a classificação.

### <a name="edit"></a>Editar

Para editar configurações específicas do grupo e da equipe, selecione a equipe clicando à esquerda do nome da equipe e, em seguida, selecione **Editar**.

### <a name="archive"></a>Arquivamento

Você pode arquivar uma equipe. Arquivar uma equipe coloca a equipe em modo somente leitura no Microsoft Teams. Como administrador, você pode arquivar e Desarquivar equipes em nome de sua organização no centro de administração. 

### <a name="delete"></a>Excluir

A exclusão de uma equipe é uma exclusão suave da equipe e do grupo correspondente do Office 365. Para restaurar uma equipe excluída incorretamente, siga as instruções em [restaurar um grupo excluído do Office 365](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).

### <a name="search"></a>Pesquisa

A pesquisa atualmente oferece suporte à cadeia de caracteres "começa com" e pesquisa o campo **nome da equipe** .

## <a name="team-profile"></a>Perfil de equipe

Você pode navegar até a página perfil da equipe de qualquer equipe na grade principal do teams Overview clicando no nome da equipe. A página perfil da equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu grupo de suporte do Office 365), bem como os canais e as configurações da equipe. Na página perfil da equipe, você pode:

- Adicionar ou remover membros e proprietários.
- Adicionar ou remover canais (Observe que você não pode remover o canal geral).
- Alterar configurações de equipe e grupo.
 
![Captura de tela de um exemplo de perfil de equipe](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Como fazer alterações em equipes

Na página de perfil da equipe, você pode alterar os seguintes elementos de uma equipe:

- **Membros** : Adicionar ou remover membros e promover ou rebaixar proprietários.
- **Canais** – adicionar novos canais e editar ou remover canais existentes. Lembre-se de que não é possível excluir o canal geral padrão.
- **Nome da equipe**
- **Descrição**
- **Privacidade** -defina se a equipe é pública ou privada.
- **Classificação** : apoiado por suas classificações de grupo do Office 365. Escolha **confidencial**, **altamente confidencial**ou **geral**.
- **Configurações de conversas** -defina se os membros podem editar e excluir mensagens enviadas.
- **Configurações de canais** -defina se os membros poderão criar novos canais e editar os existentes e adicionar, editar e remover guias, conectores e aplicativos.

As alterações feitas em uma equipe são registradas. Se você estiver modificando as configurações do grupo (alterando o nome, a descrição, a foto, a classificação, a classificação ou os membros da equipe), as alterações serão atribuídas a você pelo pipeline de auditoria. Se você estiver executando ações em configurações específicas de equipes, suas alterações serão controladas e atribuídas a você no canal geral da equipe.

## <a name="troubleshooting"></a>Solução de problemas

**Problema: equipes ausentes da grade de visão geral da equipe**

Algumas de suas equipes estão ausentes da lista de equipes na grade de visão geral do teams.

**Causa**: esse problema ocorre quando a equipe era incorretamente (ou ainda não) Profile pelo sistema, que pode levar a uma propriedade ausente para ser reconhecida.

**Resolução: definir manualmente a propriedade como o valor correto via MS Graph**

Substitua **{GroupId}** na consulta para o GroupId em questão real, que você pode obter por meio do PowerShell do Exchange Online, com o cmdlet **"[Get-unificado](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como o atributo "**ExternalDirectoryObjectId**".

1. [Gerenciador de gráficos](https://developer.microsoft.com/en-us/graph/graph-explorer)do Access.

2. Conecte-se ao Graph Explorer no menu à esquerda.

3. Altere a linha de consulta para: PATCH > v 1.0 https://graph.microsoft.com/v1.0/groups/{groupid}>.

4. Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["equipe"]}.

5. Execute a consulta no canto superior direito.

6. Confirme que a equipe é exibida corretamente no centro de administração do Microsoft Teams-visão geral da equipe.

## <a name="learn-more"></a>Saiba mais

- [Referência do cmdlet do teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [Usar funções de administrador do teams para gerenciar equipes](using-admin-roles.md)
- [Planejar o gerenciamento do ciclo de vida no Teams](plan-teams-lifecycle.md)
