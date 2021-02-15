---
title: Visualização pública no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenha mais informações sobre a prévia pública no Microsoft Teams. Experimente novos recursos e forneça comentários.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 60ed1c821389fb56d6e6bfb4ab4a37e562be726a
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196215"
---
# <a name="microsoft-teams-public-preview"></a>Visualização Pública do Microsoft Teams

> [!NOTE]
> Os recursos incluídos na versão prévia podem não estar completos e podem sofrer alterações antes de se tornarem disponíveis no lançamento público. Eles são fornecidos apenas para fins de avaliação e exploração. Sem suporte na Nuvem da comunidade Office 365 Government.

A Visualização Pública para Microsoft Teams fornece acesso antecipado a recursos não lançados no Teams. As visualizações permitem que você explore e teste os próximos recursos. Também agradecemos comentários sobre qualquer recurso em visualizações públicas. A visualização pública é habilitada por usuário da equipe, então você não precisa se preocupar em afetar toda a sua organização.

Para obter uma lista do que está disponível na visualização pública do Teams, visite as [Notas de Versão do Canal Atual (Pré-visualização)](https://docs.microsoft.com/officeupdates/current-channel-preview).

## <a name="set-the-update-policy"></a>Definir a política de atualização

A visualização pública é habilitada por usuário, e a opção de ativar a visualização pública é controlada por uma política administrativa. As políticas de atualização são usadas para gerenciar o Microsoft Teams e os usuários de visualização do Office que verão recursos de pré-lançamento ou pré-visualização no aplicativo Microsoft Teams. Você pode usar a política Global (Padrão em toda a organização) e personalizá-la ou criar uma ou mais políticas personalizadas para os usuários. A política precisa ser atribuída a usuários específicos porque não sobrescreve a política global.

1. Entre no Centro de administração.
2. Selecione **Teams**>**Atualizar políticas**.

   ![Selecionar a opção Atualizar políticas](media/updatePolicies.png)

3. Selecione **Adicionar**.
4. Nomeie a política de atualização, adicione uma descrição e ative **Mostrar recursos de pré-visualização**.

Também é possível definir a política usando o Windows PowerShell usando o cmdlet`CsTeamsUpdateManagementPolicy`.

## <a name="enable-public-preview"></a>Habilitar visualização pública

Para habilitar a visualização pública em uma área de trabalho ou cliente da web, você precisa realizar as seguintes tarefas:

1. Selecione o perfil para exibir o menu Teams.
2. Selecione **Sobre** → **Visualização pública**.
3. Selecione **Alternar para Visualização pública**.

## <a name="related-topics"></a>Tópicos relacionados

[Pré-visualização do desenvolvedor público](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)

