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
ms.openlocfilehash: ab48796f877f6af33b8a3c1b2bc5a3cc56e7bd1e
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530978"
---
# <a name="microsoft-teams-public-preview"></a>Visualização Pública do Microsoft Teams

> [!NOTE]
> Talvez os recursos incluídos na pré-visualização possam estar incompletos e possam sofrer alterações antes de ficarem disponíveis no lançamento público. Eles são fornecidoas apenas para fins de avaliação e exploração.

A Pré-visualização Pública do Microsoft Teams oferece acesso antecipado aos recursos inéditos no Teams. As pré-visualizações permitem que você explore e teste os recursos que estão por vir. Também agradecemos comentários sobre qualquer recurso nas pré-visualizações públicas. A pré-visualização pública está habilitada para cada usuário do Teams, portanto, você não precisa se preocupar em afetar a sua organização.

## <a name="set-the-update-policy"></a>Definir a política de Atualização

 A visualização pública é habilitada para cada usuário e a opção de ativar a visualização pública é controlada em uma política administrativa. As políticas de atualização são usadas para gerenciar o Microsoft Teams e os usuários de visualização do Office que verão recursos de pré-lançamento ou pré-visualização no aplicativo Microsoft Teams. Você pode usar a política Global (Padrão em toda a organização) e personalizá-la ou criar uma ou mais políticas personalizadas para os usuários. A política precisa ser atribuída a usuários específicos porque não sobrescreve a política global.

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
