---
title: Gerenciar equipes no centro de administração do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Saiba como exibir ou atualizar suas equipes no Centro de administração do Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf4d312f8fcb7f9ba509359eaaeed415be3e9662
ms.sourcegitcommit: d3c459dc1304db5f5ba78b5e093b5a4fd797c8ec
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "30178673"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gerenciar equipes no centro de administração do Microsoft Teams
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a>Visão geral

Como um administrador de TI, você pode precisar exibir ou atualizar as equipes que sua organização tiver configurado para colaboração, ou você podem precisar efetuar as ações de remediação como atribuir proprietários para equipes sem proprietários. Você pode gerenciar as equipes usadas na sua organização por meio do módulo de PowerShell de equipes da Microsoft e o Centro de administração do Microsoft Teams. Para os recursos de administração completos usando esses dois conjuntos de ferramentas, verifique se você recebem uma das seguintes funções:

- Administrador global
- Administrador de Serviço de Equipes

Você também deve garantir que sua conta tenha sido atribuída uma licença de equipes não seja de avaliação para o gerenciamento. Como parte de um problema conhecido, você deve garantir que sua conta tem apenas **uma** função de administrador atribuída.  Você pode aprender mais sobre as funções de administrador no Microsoft Teams em [equipes da Microsoft usar funções de administrador para gerenciar equipes](using-admin-roles.md)e você pode ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet equipes da Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).  

Este artigo fornece uma visão geral das ferramentas de gerenciamento para equipes no Centro de administração do Microsoft Teams.

## <a name="teams-overview-grid"></a>Grade de visão geral de equipes

Ferramentas de gerenciamento para equipes estão sob o nó de **equipes** no Centro de administração do Microsoft Teams. (No Centro de administração, selecione **equipes** > **gerenciar equipes**.) Cada equipe é feito por um grupo do Office 365 e este nó fornece um modo de exibição dos grupos que foram habilitados para equipes em sua organização do Microsoft.

> [!NOTE]
> Estamos no processo backfilling criado anteriormente equipes para garantir que eles serão exibidas nesse modo de exibição.

![Grade de visão geral de equipes](media/manage-teams-in-modern-portal-image1.png)  

A grade exibe as seguintes propriedades:

- **Nome da equipe**
- **Canais** - uma contagem de todos os canais da equipe, incluindo o canal gerais do padrão.
- **Os usuários** - uma contagem do total de usuários, incluindo proprietários, convidados e membros de seu locatário.
- **Proprietários** - uma contagem de proprietários para essa equipe.
- **Convidados** - uma contagem de usuários de convidado B2B do Azure Active Directory que são membros dessa equipe.
- **Privacidade** - o AccessType do grupo apoio Office 365.

### <a name="search"></a>Pesquisa

Pesquisa atualmente suporta a cadeia de caracteres "Começa com" e pesquisa o campo **nome da equipe** .

### <a name="edit"></a>Editar

Você pode editar o grupo e as configurações específicas do team selecionando uma equipe da grade e, em seguida, selecionando o botão **Editar** .

![Editar a equipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>Perfil de equipe

Você pode navegar para a página de perfil de equipe de qualquer equipe da grade de visão geral de equipes principal clicando no nome da equipe. A página de perfil de equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu fazendo O365 grupo), bem como os canais e configurações da equipe. Na página de perfil da equipe, você pode:

- Adicionar ou remover membros e proprietários.
- Adicionar ou remover canais (Observe que não é possível remover o canal geral).
- Atualize a equipe e configurações de grupo.
 
![Perfil de equipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>Fazendo alterações em equipes

Você pode alterar os seguintes elementos de uma equipe:
- **Os usuários na equipe de** - você pode adicionar ou remover membros e promover ou rebaixar proprietários
- **Canais** - você pode adicionar novos canais ou remover canais existentes.  Você não pode excluir o canal de "General" padrão e uma vez criada você só pode editar o nome de canal, não a descrição.
- **Nome da equipe**
- **Descrição da equipe**
- **Privacidade de equipe** - pública ou privada
- **Classificação de equipe** - feito pelo seus classificações de grupo do Office 365
- **Configurações de membro de equipe** - configurações de membro da equipe select


As alterações feitas em uma equipe são registradas. Se você estiver modificando configurações de grupo (alterando o nome, descrição, foto, privacidade, classificação ou membros da equipe), essas alterações serão atribuídas a você através do pipeline de auditoria. Se você estiver realizando ações contra as configurações específicas de equipes, suas alterações serão rastreadas e atribuídas a você no canal geral da equipe.

## <a name="troubleshooting"></a>Solução de problemas

**Problema: As equipes ausentes da grade de visão geral da equipe**

Quando você insere o Centro de administração do Microsoft Teams, sob a opção de **equipes** algumas das suas equipes estão ausentes da listagem na grade de visão geral de equipes.

**Causa**: esse problema ocorre quando a equipe foi atribuída incorretamente (ou ainda não) pelo sistema que pode resultar em uma propriedade ausente para que ele seja reconhecida.

**Resolução: Definir a propriedade manualmente o valor correto via MS Graph**

Substitua **{groupid}** na consulta referente a GroupId real em questão, que você pode obter via o powershell do Exchange Online, o cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como o atributo "**ExternalDirectoryObjectId**".

1. Acesso do [Explorer do gráfico](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. Entrar no Explorer do gráfico no menu à esquerda

3. Altere a linha de consulta para: gt _ do PATCH gt _ v 1.0https://graph.microsoft.com/v1.0/groups/{groupid}

4. Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["equipe"]}

5. Execute a consulta na parte superior direita.

6. Confirmar que a equipe seja exibido corretamente no Centro de administração do Microsoft Teams - visão geral da equipe


## <a name="learn-more"></a>Saiba mais

[Referência do cmdlet Teams da Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Funções de administrador no Microsoft Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

