---
title: Gerenciar equipes no centro de administração do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Saiba como exibir ou atualizar as equipes que sua organização definiu para colaboração no centro de administração do Microsoft Teams.
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
ms.openlocfilehash: 6bf864fefd3ac60c7531bd339a5587c8f2f0dd72
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094231"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gerenciar equipes no centro de administração do Microsoft Teams
==========================================

## <a name="overview"></a>Visão Geral

Este artigo fornece uma visão geral das ferramentas de gerenciamento do Teams no centro de administração do Microsoft Teams.

Como administrador, talvez seja necessário exibir ou atualizar as equipes que sua organização definiu para colaboração, ou talvez seja necessário executar ações de correção, como a atribuição de proprietários para equipes sem proprietário. Você pode gerenciar as equipes usadas em sua organização por meio do módulo do Microsoft Teams PowerShell e do centro de administração do Microsoft Teams. Você pode acessar o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> . Para recursos de administração completa usando esses dois toolsets, você deve garantir que você tenha uma das seguintes funções:

- Administrador Global
- Administrador de Serviço do Teams

Você pode saber mais sobre funções de administrador no Teams em Usar funções de administrador do [Microsoft Teams](using-admin-roles.md)para gerenciar o Teams e ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na referência [de cmdlet](/powershell/teams/?view=teams-ps)do Microsoft Teams.



## <a name="teams-overview-grid"></a>Grade de visão geral do Teams

As ferramentas de gerenciamento para equipes estão sob o nó **Do Teams** no centro de administração do Microsoft Teams. (No centro de administração, selecione **Teams**  >  **Gerenciar equipes**.) Cada equipe tem o suporte de um Grupo do Microsoft 365, e esse nó fornece uma exibição de grupos que foram habilitados para o Microsoft Teams em sua organização.

![Captura de tela da grade de visão geral do Teams](media/manage-teams-in-modern-portal-grid.png)  

A grade exibe as seguintes propriedades:

- **Nome da equipe**
- **Canais** - uma contagem de todos os canais da equipe, incluindo o canal geral padrão.
- **Membros da** equipe - uma contagem do total de usuários, incluindo proprietários, convidados e membros de seu locatário.
- **Proprietários** - uma contagem de proprietários para essa equipe.
- **Convidados** - uma contagem de usuários convidados do Azure Active Directory B2B que são membros dessa equipe.
- **Privacidade** - a Visibilidade/AccessType do grupo de suporte do Microsoft 365.
- **Status** - o status Arquivado ou Ativo para essa equipe. Saiba mais sobre as equipes de arquivamento em [Arquivo morto ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **Descrição** - a descrição do grupo de suporte do Microsoft 365.
- **Classificação** - a classificação (se usada em sua organização) atribuída ao grupo de suporte do Microsoft 365. Saiba mais sobre classificações em [Criar classificações para grupos do Office em sua organização.](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- **GroupID** - o GroupID exclusivo do grupo de suporte do Microsoft 365.

> [!NOTE]
> Se você não vir todas essas propriedades na grade, clique no **ícone Editar colunas.** No painel **Editar colunas,** você pode usar as alternâncias para ativar ou desativar colunas na grade. Quando terminar, clique em **Aplicar**.

### <a name="add"></a>Adicionar

Para adicionar uma nova equipe, clique em **Adicionar**. No painel **Adicionar um novo time,** dê um nome e uma descrição à equipe, de definir se você deseja torná-la uma equipe pública ou privada e definir a classificação.

> [!NOTE]
> As equipes recém-criadas podem ser gerenciadas imediatamente no Centro de Administração do Teams, ao contrário da experiência em outros clientes, como o Outlook.

### <a name="edit"></a>Editar

Para editar configurações específicas do grupo e da equipe, selecione a equipe clicando à esquerda do nome da equipe e selecione **Editar**.

### <a name="archive"></a>Arquivamento

Você pode arquivar uma equipe. O arquivamento de uma equipe coloca a equipe no modo somente leitura no Teams. Como administrador, você pode arquivar e des arquivar equipes em nome da sua organização no centro de administração. 

### <a name="delete"></a>Excluir

Excluir uma equipe é uma exclusão suave da equipe e do grupo correspondente do Microsoft 365. Para restaurar uma equipe excluída por engano, siga as instruções em [Restaurar um Grupo excluído.](/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="search"></a>Pesquisa

A pesquisa atualmente dá suporte à cadeia de caracteres "Begins with" e pesquisa o **campo Nome da** equipe.

## <a name="team-profile"></a>Perfil de equipe

Você pode navegar até a página de perfil de equipe de qualquer equipe na grade de visão geral das equipes principais clicando no nome da equipe. A página de perfil de equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu grupo de suporte do Microsoft 365), bem como os canais e configurações da equipe. Na página perfil de equipe, você pode:

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
- **Classificação** - isso é apoiado pelas classificações de grupo do Microsoft 365. Escolha **Confidencial,** **Altamente Confidencial** ou **Geral.**
- **Configurações de conversas** - definir se os membros podem editar e excluir mensagens enviadas.
- **Configurações de canais** - definir se os membros podem criar novos canais e editar os existentes e adicionar, editar e remover guias, conectores e aplicativos.

As alterações feitas em uma equipe são registradas. Se você estiver modificando as configurações de grupo (alterando o nome, a descrição, a foto, a privacidade, a classificação ou os membros da equipe), as alterações serão atribuídas a você por meio do pipeline de auditoria. Se você estiver executando ações em relação a configurações específicas do Teams, suas alterações serão controladas e atribuídas a você no canal Geral da equipe.

## <a name="troubleshooting"></a>Solução de problemas

**Problema: Equipes ausentes da grade visão geral da equipe**

Algumas de suas equipes estão ausentes na lista de equipes na grade de visão geral do Teams.

**Causa**: Esse problema ocorre quando a equipe foi perfilada incorretamente (ou ainda não) pelo sistema, o que pode levar a uma propriedade ausente para que ela seja reconhecida.

**Resolução: de definir manualmente a propriedade como o valor correto por meio do MS Graph**

Substitua **{groupid}** na Consulta para o GroupId real em questão, que você pode obter por meio do powershell do Exchange Online, pelo cmdlet **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)",** como o atributo "**ExternalDirectoryObjectId**".

1. Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).

2. Entre no Explorador do Graph no menu esquerdo.

3. Altere a linha de consulta para: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} .

4. Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["Team"]}.

5. Execute a consulta na parte superior direita.

6. Confirme se a equipe aparece corretamente no centro de administração do Microsoft Teams - Visão geral da equipe.

## <a name="learn-more"></a>Saiba mais

- [Referência de cmdlet do Teams](/powershell/teams/?view=teams-ps)  
- [Usar funções de administrador do Teams para gerenciar o Teams](using-admin-roles.md)
- [Planejar o gerenciamento do ciclo de vida no Teams](plan-teams-lifecycle.md)