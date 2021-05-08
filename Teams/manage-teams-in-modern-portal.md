---
title: Gerenciar equipes no Microsoft Teams de administração
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Saiba como exibir ou atualizar as equipes que sua organização definiu para colaboração no Microsoft Teams de administração.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea81ad854224e08142f9c87725d25176dcc60d44
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237537"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gerenciar equipes no Microsoft Teams de administração
==========================================

## <a name="overview"></a>Visão Geral

Este artigo fornece uma visão geral das ferramentas de gerenciamento para Teams no Microsoft Teams de administração.

Como administrador, talvez seja necessário exibir ou atualizar as equipes que sua organização definiu para colaboração, ou talvez seja necessário executar ações de correção, como a atribuição de proprietários para equipes sem proprietário. Você pode gerenciar as equipes usadas em sua organização por meio do módulo Microsoft Teams PowerShell e do Microsoft Teams de administração. Você pode acessar o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> . Para recursos de administração completa usando esses dois toolsets, você deve garantir que você tenha uma das seguintes funções:

- Administrador Global
- Teams Administrador

Você pode saber mais sobre funções de administrador no Teams em Usar funções de administrador do Microsoft Teams para gerenciar o Teams e ler mais sobre [como](using-admin-roles.md)usar os cmdlets do PowerShell para gerenciar equipes na referência do [cmdlet Microsoft Teams](/powershell/teams/?view=teams-ps).



## <a name="teams-overview-grid"></a>Teams de visão geral

As ferramentas de gerenciamento para equipes **estão sob o nó Teams** no centro de Microsoft Teams de administração. (No centro de administração, selecione **Teams**  >  **Gerenciar equipes**.) Cada equipe tem o Microsoft 365 Grupo, e esse nó fornece uma exibição de grupos que foram Microsoft Teams habilitados em sua organização.

![Captura de tela da grade Teams visão geral](media/manage-teams-in-modern-portal-grid.png)  

A grade exibe as seguintes propriedades:

- **Nome da equipe**
- **Canais** - uma contagem de todos os canais da equipe, incluindo o canal geral padrão.
- **Membros da** equipe - uma contagem do total de usuários, incluindo proprietários, convidados e membros de seu locatário.
- **Proprietários** - uma contagem de proprietários para essa equipe.
- **Convidados** - uma contagem de Azure Active Directory usuários convidados B2B que são membros dessa equipe.
- **Privacidade** - a Visibilidade/AccessType do grupo de Microsoft 365 de apoio.
- **Status** - o status Arquivado ou Ativo para essa equipe. Saiba mais sobre as equipes de arquivamento em [Arquivo morto ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **Descrição** - a descrição do grupo de Microsoft 365 de apoio.
- **Classificação** - a classificação (se usada em sua organização) atribuída ao grupo de Microsoft 365 de apoio. Saiba mais sobre classificações em [Criar classificações para Office grupos em sua organização.](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- **GroupID** - o GroupID exclusivo do grupo de Microsoft 365 de apoio.

> [!NOTE]
> Se você não vir todas essas propriedades na grade, clique no **ícone Editar colunas.** No painel **Editar colunas,** você pode usar as alternâncias para ativar ou desativar colunas na grade. Quando terminar, clique em **Aplicar**.

### <a name="add"></a>Adicionar

Para adicionar uma nova equipe, clique em **Adicionar**. No painel **Adicionar um novo time,** dê um nome e uma descrição à equipe, de definir se você deseja torná-la uma equipe pública ou privada e definir a classificação.

> [!NOTE]
> As equipes recém-criadas podem ser gerenciadas imediatamente no Centro de Administração Teams, diferentemente da experiência em outros clientes, como, Outlook.

### <a name="edit"></a>Editar

Para editar configurações específicas do grupo e da equipe, selecione a equipe clicando à esquerda do nome da equipe e selecione **Editar**.

### <a name="archive"></a>Arquivamento

Você pode arquivar uma equipe. O arquivamento de uma equipe coloca a equipe no modo somente leitura dentro Teams. Como administrador, você pode arquivar e des arquivar equipes em nome da sua organização no centro de administração. 

### <a name="delete"></a>Excluir

Excluir uma equipe é uma exclusão suave da equipe e o grupo Microsoft 365 correspondente. Para restaurar uma equipe excluída por engano, siga as instruções em [Restaurar um Grupo excluído.](/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="search"></a>Pesquisa

A pesquisa atualmente dá suporte à cadeia de caracteres "Begins with" e pesquisa o **campo Nome da** equipe.

## <a name="team-profile"></a>Perfil de equipe

Você pode navegar até a página de perfil de equipe de qualquer equipe na grade de visão geral das equipes principais clicando no nome da equipe. A página de perfil de equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu grupo de Microsoft 365 de apoio), bem como os canais e configurações da equipe. Na página perfil de equipe, você pode:

- Adicionar ou remover membros e proprietários.
- Adicione ou remova canais (observe que você não pode remover o canal Geral).
- Alterar configurações de equipe e grupo.
 
![Captura de tela de um perfil de equipe de exemplo](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Fazendo alterações nas equipes

Na página de perfil da equipe, você pode alterar os seguintes elementos de uma equipe:

- **Membros** - adicionar ou remover membros e promover ou rebaixar proprietários.
- **Canais** - adicione novos canais e edite ou remova canais existentes. Lembre-se de que você não pode excluir o canal geral padrão.
- **Nome da equipe**
- **Descrição**
- **Privacidade** - definir se a equipe é pública ou privada.
- **Classificação** - isso é respaldado pelas classificações Microsoft 365 grupo. Escolha **Confidencial,** **Altamente Confidencial** ou **Geral.**
- **Configurações de conversas** - definir se os membros podem editar e excluir mensagens enviadas.
- **Configurações de canais** - definir se os membros podem criar novos canais e editar os existentes e adicionar, editar e remover guias, conectores e aplicativos.

As alterações feitas em uma equipe são registradas. Se você estiver modificando as configurações de grupo (alterando o nome, a descrição, a foto, a privacidade, a classificação ou os membros da equipe), as alterações serão atribuídas a você por meio do pipeline de auditoria. Se você estiver executando ações Teams configurações específicas, suas alterações serão controladas e atribuídas a você no canal Geral da equipe.

## <a name="troubleshooting"></a>Solução de problemas

**Problema: Teams ausente da grade visão geral da equipe**

Algumas de suas equipes estão ausentes na lista de equipes na grade Teams visão geral.

**Causa**: Esse problema ocorre quando a equipe foi perfilada incorretamente (ou ainda não) pelo sistema, o que pode levar a uma propriedade ausente para que ela seja reconhecida.

**Resolução: de definir manualmente a propriedade como o valor correto por meio do MS Graph**

Substitua **{groupid}** na Consulta para o GroupId real em questão, que você pode obter por meio do powershell Exchange Online, pelo cmdlet **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)",** como o atributo "**ExternalDirectoryObjectId**".

1. Acessar [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).

2. Entre no Graph Explorer no menu esquerdo.

3. Altere a linha de consulta para: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} .

4. Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["Team"]}.

5. Execute a consulta na parte superior direita.

6. Confirme se a equipe aparece corretamente no Microsoft Teams de administração - Visão geral da equipe.

## <a name="learn-more"></a>Saiba mais

- [Teams de cmdlet](/powershell/teams/?view=teams-ps)  
- [Usar Teams funções de administrador para gerenciar Teams](using-admin-roles.md)
- [Planejar o gerenciamento do ciclo de vida no Teams](plan-teams-lifecycle.md)