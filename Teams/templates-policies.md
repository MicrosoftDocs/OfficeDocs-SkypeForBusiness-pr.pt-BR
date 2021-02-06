---
title: Gerenciar modelos de equipe no centro de administração
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar modelos de equipe no centro de administração
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ef765013541ae740211cc5666da3544f1cd5b528
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125858"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a>Criar e gerenciar modelos de equipe no centro de administração

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Gerencie os modelos do teams que são mostrados para seus usuários finais criando políticas de modelos no centro de administração. Em cada política de modelo, você pode designar quais modelos são mostrados ou ocultos.
Atribua diferentes usuários a políticas de modelos diferentes para que seus usuários exibam somente o subconjunto de modelos de equipes especificado.

## <a name="create-template-policies-and-assign-available-templates"></a>Criar políticas de modelo e atribuir modelos disponíveis

1. Entre no centro de administração do Microsoft Teams.

2. Expanda políticas de modelos do **Teams**  >  .

3. Selecione **Adicionar**.

    ![As políticas de modelo são selecionadas e a adição é realçada](media/template-policies-1.png)

1. Na seção **configurações de políticas de modelos** , preencha os seguintes campos:

    - Nome da política de modelos

    - Descrição resumida da política modelos

2. Na tabela **modelos exibíveis** , selecione os modelos que você deseja ocultar e selecione **ocultar**.

    ![Os modelos selecionados com ocultar realçado](media/template-policies-2.png)

    Você pode ver os modelos que selecionou para ocultar na tabela **modelos ocultos** .

1. Para reexibir determinados modelos, role até a tabela **modelos ocultos** .

1. Selecione os modelos para reexibir e selecione **Mostrar**.

   ![Os modelos selecionados com ocultar realçado](media/template-policies-3.png)

   Os modelos selecionados aparecerão na tabela **modelos exibíveis** .
3. Selecione **Salvar**.

   Sua nova política de modelo é exibida na lista **políticas de modelos** .

## <a name="assign-users-to-the-template-policies"></a>Atribuir usuários às políticas de modelo

Os usuários atribuídos a uma política só poderão ver os modelos visíveis dentro dessa política.

1. Em **políticas de modelos**, selecione uma política e, em seguida, selecione **gerenciar usuários**.

2. Digite os usuários que deseja atribuir a essa política.

   ![Os modelos selecionados com ocultar realçado](media/template-policies-4.png)

3. Selecione **aplicar**.

> [!Note]
> Pode levar até 24 horas para que sua nova política entre em vigor para os usuários finais.

## <a name="size-limits-for-template-policies"></a>Limites de tamanho para políticas de modelo

Você pode ocultar um máximo de modelos do 100 por política. O botão **ocultar** estará desabilitado se a política fornecida já tiver modelos do 100 ocultos.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**P: posso atribuir usuários a políticas de modelos de equipe a um lote?**
  
R: Sim, oferecemos suporte à atribuição em lote para a política de modelo no PowerShell. O tipo de política para esta ação é TeamsTemplatePermissionPolicy. [Saiba Mais](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

**P: os grupos podem ser atribuídos a políticas de modelos de equipe?**

R: no momento. Esta funcionalidade estará disponível no futuro.

**P: se um novo modelo for criado, o modelo será incluído em minhas políticas?**

R: os modelos novos ficarão visíveis por padrão. Você pode optar por ocultar o modelo no centro de administração na seção políticas de modelos.

**P: o que acontece se um modelo é excluído?**

R: todos os modelos excluídos não estarão mais presentes em políticas de modelos.

**P: posso atribuir vários usuários a uma política de modelo no centro de administração do teams?**

R: Sim.

1. No centro de administração, vá para **usuários**.
1. Na tabela lista de usuários, selecione os usuários que você deseja atribuir a determinada política de modelos.
1. Selecione Editar configurações e altere o campo políticas de modelos.
1. Selecione aplicar.
   Saiba mais [atribuir políticas a seus usuários no Microsoft Teams-Microsoft Teams \| Microsoft docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).

**P: como exibir todos os usuários atribuídos a uma política específica?**

R: no centro de administração:

1. Vá para a seção **usuários** .
2. Selecione o filtro na tabela da lista usuários e o filtro para a política de modelo do teams.
3. Selecione **aplicar**.

![Os modelos selecionados com ocultar realçado](media/template-policies-5.png)

**P: é possível gerenciar políticas de modelos pelo PowerShell?**

R: não, isso não tem suporte.

**P: as políticas de modelos se aplicam ao EDU?**

R: não, isso não tem suporte.

## <a name="related-topics"></a>Tópicos relacionados

- [Introdução aos modelos de equipe no centro de administração](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [Criar um modelo de equipe personalizado](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [Criar um modelo a partir de uma equipe existente](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [Criar um modelo de equipe a partir de um modelo de equipe existente](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [Atribuir políticas a seus usuários no Microsoft Teams-Microsoft Teams \| Microsoft docs](https://docs.microsoft.com/microsoftteams/assign-policies)

- [TeamsTemplatePermissionPolicy](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)