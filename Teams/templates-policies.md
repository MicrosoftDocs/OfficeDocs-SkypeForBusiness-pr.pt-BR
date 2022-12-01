---
title: Gerenciar modelos de equipe no centro de administração
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar modelos de equipe no centro de administração
ms.openlocfilehash: 5370353b38813230ab4329f8a5ad7368efe6c916
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198303"
---
# <a name="manage-team-templates-in-the-admin-center"></a>Gerenciar modelos de equipe no centro de administração

Gerencie os modelos de equipe que seus usuários finais veem criando políticas de modelos no centro de administração. Em cada política de modelos, você pode designar quais modelos são mostrados ou ocultos.
Atribua usuários diferentes a políticas de modelos diferentes para que os usuários exibam apenas o subconjunto de modelos de equipe especificados.

Assista a este pequeno vídeo para saber como gerenciar políticas de modelos.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-templates-policies-and-assign-available-templates"></a>Criar políticas de modelos e atribuir modelos disponíveis

1. Entre no Centro de administração do Teams.

2. Acesse **políticas de Modelos** do **Teams** > .

3. Escolha **Adicionar**.

    ![As políticas de modelos são selecionadas e Adicionar está realçada.](media/template-policies-1.png)

1. Dê um nome à política e adicione uma breve descrição.

2. Na lista **Modelos exibicionáveis** , selecione os modelos que você deseja ocultar e selecione **Ocultar**.

    ![Os modelos selecionados com ocultar realçados.](media/template-policies-2.png)

    Você pode ver os modelos escolhidos para ocultar na lista **de modelos ocultos** .

1. Para desmarmar determinados modelos, acesse a lista **modelos ocultos** .

2. Selecione os modelos para desativar e selecione **Mostrar**.

   ![Os modelos selecionados que não estão ocultos.](media/template-policies-3.png)

   Os modelos selecionados serão exibidos na lista **de modelos exibicionáveis** .
3. Escolha **Salvar**.

   Sua nova política de modelos é exibida na lista **de políticas de modelos** .

## <a name="assign-templates-policies-to-users"></a>Atribuir políticas de modelos aos usuários

Você pode atribuir uma política de modelos diretamente aos usuários, individualmente ou em escala por meio de uma atribuição em lote. Tenha em mente que pode levar até 24 horas para que sua nova política entre em vigor para seus usuários.

> [!Note]
> Atualmente, não há suporte para atribuir políticas de modelos aos usuários com base na associação de grupo, como para todos os usuários em um grupo de segurança. Essa funcionalidade estará disponível no futuro.

Para obter uma visão geral das maneiras de atribuir políticas no Teams, consulte [Atribuir políticas no Teams](policy-assignment-overview.md).

### <a name="assign-a-templates-policy-to-individual-users"></a>Atribuir uma política de modelos a usuários individuais

Você pode usar o centro de administração do Teams ou o PowerShell para atribuir uma política de modelos a um usuário individual ou a um pequeno número de usuários por vez. Para saber mais, confira [Atribuir uma política a usuários individuais](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users).

### <a name="assign-a-templates-policy-to-a-batch-of-users"></a>Atribuir uma política de modelos a um lote de usuários

Você pode usar o PowerShell para atribuir uma política de modelos a grandes conjuntos de usuários por vez. Para fazer isso, use o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) junto com o TeamsTemplatePermissionPolicy como o ```PolicyType``` para enviar um lote de usuários e a política de modelos que você deseja atribuir. Por exemplo:

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName <Any operation name> -PolicyType TeamsTemplatePermissionPolicy -PolicyName <policy name> -Identity <users identity | list of user identities>
```

As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote. Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para acompanhar o progresso e o status das atribuições em um lote.

Para saber mais, confira [Atribuir uma política a um lote de usuários usando o PowerShell](assign-policies-users-and-groups.md#use-powershell-method).

## <a name="size-limits-for-templates-policies"></a>Limites de tamanho para políticas de modelos

Você pode ocultar um máximo de 100 modelos por política. O botão **Ocultar** será desabilitado se a política fornecida já tiver 100 modelos ocultos.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**P: Se um novo modelo for criado, o modelo será incluído em minhas políticas?**

R: Todos os novos modelos ficarão visíveis por padrão. Você pode optar por ocultar o modelo no centro de administração na seção Políticas de Modelos.

**P: O que acontecerá se um modelo for excluído?**

R: Todos os modelos excluídos não estarão mais presentes em políticas de modelos.

**P: Posso atribuir vários usuários a uma política de modelos no centro de administração do Teams?**

R: Sim.

1. No centro de administração do Teams, acesse **Usuários** > **Gerenciar usuários**.
1. Na lista de usuários, selecione os usuários que você deseja atribuir à política de modelos.
1. Selecione **Editar configurações** e, em seguida, na **política Modelos**, escolha a política que você deseja atribuir.
1. Escolha **Aplicar**.

Para saber mais, confira [Atribuir uma política a usuários individuais](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users).

**P: Como fazer exibir todos os usuários atribuídos a uma política específica?**

R: No centro de administração do Teams:

1. Acesse **Usuários** > **Gerenciar usuários**.
2. Selecione **Filtrar**, defina um filtro para a política de modelos e escolha **Aplicar**.

    ![A política de modelos selecionados e os usuários de exibição.](media/template-policies-5.png)

**P: Posso gerenciar políticas de modelos por meio do PowerShell?**

R: Não, não há suporte para gerenciar políticas de modelos no PowerShell. No entanto, você pode usar o PowerShell para [atribuir políticas de modelos aos usuários](#assign-templates-policies-to-users) .

**P: As políticas de modelos são aplicáveis à EDU?**

R: Não há suporte para políticas de modelos para EDU.

## <a name="related-articles"></a>Artigos relacionados

- [Introdução aos modelos de equipe no centro de administração](./get-started-with-teams-templates-in-the-admin-console.md)

- [Criar um modelo de equipe personalizado](./create-a-team-template.md)

- [Criar um modelo de uma equipe existente](./create-template-from-existing-team.md)

- [Criar um modelo de equipe a partir de um modelo de equipe existente](./create-template-from-existing-template.md)

- [Atribuir políticas aos usuários no Microsoft Teams – Microsoft Docs do Teams \| Microsoft](./policy-assignment-overview.md)

- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
