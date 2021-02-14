---
title: Gerenciar equipes no Centro de administração do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Saiba como exibir ou atualizar as equipes que sua organização definiu para colaboração no Centro de administração do Microsoft Teams.
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
ms.openlocfilehash: c736cf17d263f097e97b32f856bc83cf2fe42a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814550"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gerenciar equipes no Centro de administração do Microsoft Teams
==========================================

## <a name="overview"></a>Visão Geral

Este artigo fornece uma visão geral das ferramentas de gerenciamento do Teams no Centro de administração do Microsoft Teams.

Como administrador, talvez seja necessário exibir ou atualizar as equipes que sua organização definiu para colaboração, ou talvez seja necessário executar ações de correção, como a atribuição de proprietários para equipes sem proprietário. Você pode gerenciar as equipes usadas em sua organização por meio do módulo do Microsoft Teams PowerShell e do Centro de administração do Microsoft Teams. Você pode acessar o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> . Para recursos completos de administração usando essas duas ferramentas, certifique-se de que você tenha atribuído uma das seguintes funções:

- Administrador Global
- Administrador de Serviço do Teams

Você pode saber mais sobre as funções de administrador do Teams em Usar funções de administrador do [Microsoft Teams](using-admin-roles.md)para gerenciar o Teams e ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na referência [de cmdlet](https://docs.microsoft.com/powershell/teams/?view=teams-ps)do Microsoft Teams.



## <a name="teams-overview-grid"></a>Grade de visão geral do Teams

As ferramentas de gerenciamento para equipes estão sob o nó **do Teams** no Centro de administração do Microsoft Teams. (No centro de administração, selecione **Teams**  >  **Gerenciar equipes**.) Cada equipe tem o suporte de um Grupo do Microsoft 365, e esse nó fornece uma exibição dos grupos que foram habilitados para o Microsoft Teams em sua organização.

![Captura de tela da grade de visão geral do Teams](media/manage-teams-in-modern-portal-grid.png)  

A grade exibe as seguintes propriedades:

- **Nome da equipe**
- **Canais** - uma contagem de todos os canais da equipe, incluindo o canal Geral padrão.
- **Membros da** equipe – uma contagem total de usuários, incluindo proprietários, convidados e membros de seu locatário.
- **Proprietários** – uma contagem de proprietários para esta equipe.
- **Convidados** – uma contagem de usuários convidados do Azure Active Directory B2B que são membros dessa equipe.
- **Privacidade** – a Visibilidade/AccessType do grupo de backing do Microsoft 365.
- **Status** – o status Arquivado ou Ativo desta equipe. Saiba mais sobre como arquivar equipes no [Arquivo Morto ou restaurar uma equipe.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)
- **Descrição** : a descrição do grupo de backing do Microsoft 365.
- **Classificação** : a classificação (se usada em sua organização) atribuída ao grupo de backing do Microsoft 365. Saiba mais sobre classificações em [Criar classificações para grupos do Office em sua organização.](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- **GroupID** - o GroupID exclusivo do grupo de apoio do Microsoft 365.

> [!NOTE]
> Se você não vir todas essas propriedades na grade, clique no **ícone Editar colunas.** No painel **Editar colunas,** você pode usar os botões para ativar ou desativar colunas na grade. Quando terminar, clique em **Aplicar.**

### <a name="add"></a>Adicionar

Para adicionar uma nova equipe, clique em **Adicionar.** No painel **Adicionar uma** nova equipe, dê um nome e uma descrição à equipe, desmarque se deseja torná-la uma equipe pública ou privada e desmarque a classificação.

> [!NOTE]
> As equipes recém-criadas podem ser gerenciadas imediatamente no Centro de administração do Teams, diferentemente da experiência em outros clientes, como o Outlook.

### <a name="edit"></a>Editar

Para editar configurações específicas do grupo e da equipe, selecione a equipe clicando à esquerda do nome da equipe e, em seguida, selecione **Editar.**

### <a name="archive"></a>Arquivamento

Você pode arquivar uma equipe. O arquivamento de uma equipe coloca a equipe no modo somente leitura no Teams. Como administrador, você pode arquivar e des arquivar equipes em nome de sua organização no centro de administração. 

### <a name="delete"></a>Excluir

Excluir uma equipe é uma exclusão suave da equipe e o grupo correspondente do Microsoft 365. Para restaurar uma equipe excluída por engano, siga as instruções em [Restaurar um Grupo excluído.](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="search"></a>Pesquisa

A pesquisa atualmente dá suporte à cadeia de caracteres "Começa com" e pesquisa o **campo nome da** equipe.

## <a name="team-profile"></a>Perfil da equipe

Você pode navegar até a página de perfil da equipe de qualquer equipe na grade de visão geral das equipes principais clicando no nome da equipe. A página de perfil da equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu grupo de apoio do Microsoft 365), bem como os canais e configurações da equipe. Na página de perfil da equipe, você pode:

- Adicionar ou remover membros e proprietários.
- Adicionar ou remover canais (observe que não é possível remover o canal Geral).
- Altere as configurações de equipe e grupo.
 
![Captura de tela de um exemplo de perfil de equipe](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Fazer alterações nas equipes

Na página de perfil da equipe, você pode alterar os seguintes elementos de uma equipe:

- **Membros** - adicionar ou remover membros e promover ou rebaixar proprietários.
- **Canais** – adicione novos canais e edite ou remova canais existentes. Lembre-se de que não é possível excluir o canal Geral padrão.
- **Nome da equipe**
- **Descrição**
- **Privacidade** : definir se a equipe é pública ou privada.
- **Classificação** : isso é respaldado pelas classificações de grupo do Microsoft 365. Escolha **Confidencial,** **Altamente Confidencial** ou **Geral.**
- **Configurações de conversas** - de definir se os membros podem editar e excluir mensagens enviadas.
- **Configurações de canais** : de definir se os membros podem criar novos canais e editar os existentes e adicionar, editar e remover guias, conectores e aplicativos.

As alterações feitas em uma equipe são registradas. Se você estiver modificando as configurações de grupo (alterando o nome, a descrição, a foto, a privacidade, a classificação ou os membros da equipe), as alterações serão atribuídas a você por meio do pipeline de auditoria. Se você estiver executando ações em relação às configurações específicas do Teams, suas alterações serão controladas e atribuídas a você no canal Geral da equipe.

## <a name="troubleshooting"></a>Solução de problemas

**Problema: Equipes ausentes da grade de visão geral da equipe**

Algumas de suas equipes estão ausentes na lista de equipes na grade de visão geral do Teams.

**Causa:** esse problema ocorre quando a equipe foi perfilada incorretamente (ou ainda não) pelo sistema, o que pode levar a uma propriedade ausente para que ela seja reconhecida.

**Resolução: definir manualmente a propriedade como o valor correto por meio do MS Graph**

Substitua **{groupid}** na Consulta para o GroupId real em questão, que você pode obter por meio do powershell do Exchange Online, pelo cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)",** como o atributo "**ExternalDirectoryObjectId**".

1. Access [Graph Explorer.](https://developer.microsoft.com/graph/graph-explorer)

2. Entre no Graph Explorer no menu à esquerda.

3. Altere a linha da consulta para: PATCH > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >.

4. Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["Equipe"]}.

5. Execute a consulta no canto superior direito.

6. Confirme se a equipe aparece corretamente no Centro de administração do Microsoft Teams – Visão geral da equipe.

## <a name="learn-more"></a>Saiba mais

- [Referência de cmdlet do Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [Usar funções de administrador do Teams para gerenciar o Teams](using-admin-roles.md)
- [Planejar o gerenciamento do ciclo de vida no Teams](plan-teams-lifecycle.md)
