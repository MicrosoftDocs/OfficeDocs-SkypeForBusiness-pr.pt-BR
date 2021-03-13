---
title: Gerenciar modelos do Teams no centro de administração
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
description: Saiba como gerenciar modelos do Teams no centro de administração
ms.openlocfilehash: b32be22dc7a57e65c6ec8d901ae6e7b004ce4b6c
ms.sourcegitcommit: 3db994f3d26b05071d84b2004892a2ca2ff26d25
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2021
ms.locfileid: "50765824"
---
# <a name="manage-teams-templates-in-the-admin-center"></a>Gerenciar modelos do Teams no centro de administração

Gerencie os modelos do Teams que os usuários finais veem criando políticas de modelos no centro de administração. Em cada política de modelo, você pode designar quais modelos são mostrados ou ocultos.
Atribua usuários diferentes a políticas de modelo diferentes para que seus usuários visualizam apenas o subconjunto de modelos do Teams especificados.

Assista a este breve vídeo para saber como gerenciar políticas de modelo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a>Criar políticas de modelo e atribuir modelos disponíveis

1. Entre no Centro de administração do Teams.

2. Expanda **políticas**  >  **de Modelos do** Teams.

3. Selecione **Adicionar**.

    ![As políticas de modelo são selecionadas e Add é realçada](media/template-policies-1.png)

1. Na seção **Configurações de Políticas de Modelos,** conclua os seguintes campos:

    - Nome da Política de Modelos

    - Descrição curta da Política de Modelos

2. Na tabela **Modelos Exibiveis,** selecione os modelos que você deseja ocultar e selecione **Ocultar**.

    ![Os modelos selecionados com ocultação realçada](media/template-policies-2.png)

    Você pode ver os modelos selecionados para ocultar na tabela **Modelos Ocultos.**

1. Para desaconsule determinados modelos, role até **a tabela Modelos ocultos.**

1. Selecione os modelos a ser desaconsudidados e selecione **Mostrar**.

   ![Os modelos selecionados que não estão ocultos](media/template-policies-3.png)

   Os modelos selecionados serão exibidos na tabela **Modelos Exibiveis.**
3. Selecione **Salvar**.

   Sua nova política de modelo é exibida na lista **Políticas de** Modelos.

## <a name="assign-users-to-the-template-policies"></a>Atribuir usuários às políticas de modelo

Os usuários atribuídos a uma política só poderão exibir os modelos que podem ser visualizados nessa política.

1. Em **Políticas de Modelos,** selecione uma política e selecione **Gerenciar usuários**.

2. Digite os usuários a atribuir a essa política.

   ![atribuir usuários a uma política de modelo](media/template-policies-4.png)

3. Selecione **Aplicar**.

> [!Note]
> Pode levar até 24 horas para que sua nova política entre em vigor para os usuários finais.

## <a name="size-limits-for-template-policies"></a>Limites de tamanho para políticas de modelo

Você pode ocultar um máximo de 100 modelos por política. O **botão Ocultar** será desabilitado se a política determinada já tiver 100 modelos ocultos.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**P: Posso atribuir usuários em lote a políticas de modelos de equipe?**
  
R: Sim, suportamos a atribuição em lote para a política de modelo no PowerShell. O tipo de política dessa ação é TeamsTemplatePermissionPolicy. [Saiba Mais](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)

**P: Os grupos podem ser atribuídos às políticas de modelos de equipe?**

R: Atualmente não. Essa funcionalidade estará disponível no futuro.

**P: Se um novo modelo for criado, o modelo será incluído em minhas políticas?**

R: Todos os novos modelos estarão visíveis por padrão. Você pode optar por ocultar o modelo no centro de administração na seção Políticas de Modelos.

**P: O que acontece se um modelo for excluído?**

R: Quaisquer modelos excluídos não estarão mais presentes em nenhuma política de modelos.

**P: Posso atribuir vários usuários a uma política de modelo no Centro de Administração do Teams?**

R: Sim.

1. No Centro de administração, vá para **Usuários**.
1. Na tabela de lista Usuários, selecione os usuários que você deseja atribuir a uma determinada política de modelos.
1. Selecione Editar configurações e altere o campo Políticas de modelos.
1. Selecione aplicar.
   Saiba mais [Atribuir políticas aos seus usuários no Microsoft Teams - Microsoft Teams Microsoft \| Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).

**P: Como vejo todos os usuários atribuídos a uma política específica?**

R: No Centro de administração:

1. Vá para a **seção Usuários.**
2. Selecione o filtro na tabela de lista Usuários e filtre a política de modelo de equipes.
3. Selecione **Aplicar**.

![A política de modelo selecionada e exibir usuários](media/template-policies-5.png)

**P: Posso gerenciar políticas de modelos por meio do PowerShell?**

R: Não há suporte para gerenciar modelos no PowerShell.

**P: As políticas de modelos são aplicáveis ao EDU?**

R: Não, não há suporte para políticas de modelo para EDU.

## <a name="related-topics"></a>Tópicos relacionados

- [Começar a usar modelos de equipe no centro de administração](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [Criar um modelo de equipe personalizado](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [Criar um modelo de uma equipe existente](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [Criar um modelo de equipe a partir de um modelo de equipe existente](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [Atribuir políticas aos seus usuários no Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies)

- [Atribuir em lotes usuários a uma política](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
