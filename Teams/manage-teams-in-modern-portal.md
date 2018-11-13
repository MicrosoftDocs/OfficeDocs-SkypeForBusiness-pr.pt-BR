---
title: Gerenciar equipes na Microsoft Teams & Skype para Business Admin Center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Saiba como exibir ou atualizar suas equipes na Microsoft Teams & Skype para Business Admin Center.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8d517ce7f2fb614a22c45fcf63d59a7d46b606f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295019"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a>Gerenciar equipes na Microsoft Teams & Skype para Business Admin Center
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a>Visão geral

Como um administrador de TI, você pode precisar exibir ou atualizar as equipes que sua organização tiver configurado para colaboração, ou você podem precisar efetuar as ações de remediação como atribuir proprietários para equipes sem proprietários. Você pode gerenciar as equipes usadas na sua organização por meio de tanto o módulo de PowerShell de equipes da Microsoft e o Microsoft Teams & Skype para Business Admin Center. Para os recursos de administração completos usando esses dois conjuntos de ferramentas, verifique se você recebem uma das seguintes funções:

- Administrador global
- Administrador de Serviço de Equipes

Você pode aprender mais sobre as funções de administrador no Microsoft Teams [aqui](using-admin-roles.md), e você pode ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet equipes da Microsoft](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).  

Este artigo fornece uma visão geral das ferramentas de gerenciamento para equipes na Microsoft Teams & Skype para Business Admin Center.

## <a name="teams-overview-grid"></a>Grade de visão geral de equipes

Ferramentas de gerenciamento para equipes estão sob o nó de **equipes** na Microsoft Teams & Skype para Business Admin Center. (No Centro de administração, selecione **equipes** > **gerenciar equipes**.) Cada equipe é feito por um grupo do Office 365 e este nó fornece um modo de exibição de todos os grupos que foram habilitados para equipes em sua organização do Microsoft.

![Grade de visão geral de equipes](media/manage-teams-in-modern-portal-image1.png)  

A grade exibe as seguintes propriedades:

- **Nome da equipe**
- **Canais** - uma contagem de todos os canais da equipe, incluindo o canal gerais do padrão.
- **Os usuários** - uma contagem do total de usuários, incluindo proprietários, convidados e membros de seu locatário.
- **Proprietários** - uma contagem de proprietários para essa equipe.
- **Convidados** - uma contagem de usuários de convidado B2B do Azure Active Directory que são membros dessa equipe.
- **Privacidade** - o AccessType do grupo apoio Office 365.

### <a name="search"></a>Pesquisar

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
- **Foto de equipe**
- **Privacidade de equipe** - pública ou privada
- **Classificação de equipe** - feito pelo seus classificações de grupo do Office 365
- **Configurações de membro de equipe** - configurações de membro da equipe select


As alterações feitas em uma equipe são registradas. Se você estiver modificando configurações de grupo (alterando o nome, descrição, foto, privacidade, classificação ou membros da equipe), essas alterações serão atribuídas a você através do pipeline de auditoria. Se você estiver realizando ações contra as configurações específicas de equipes, suas alterações serão rastreadas e atribuídas a você no canal geral da equipe.


## <a name="learn-more"></a>Saiba mais

[Referência do cmdlet Teams da Microsoft](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)  
[Funções de administrador no Microsoft Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

