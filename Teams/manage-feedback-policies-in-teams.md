---
title: Gerenciar políticas de comentários no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar políticas de comentários para controlar se os usuários do Teams em sua organização podem enviar comentários sobre o Teams para a Microsoft.
ms.openlocfilehash: bc925320959c55b2fa06c8480f1011aab81aae9c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094261"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gerenciar políticas de comentários no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft para nos dizer como estamos fazendo, diretamente de dentro da área de trabalho do Teams e clientes Web. Estamos melhorando continuamente a experiência do Teams e usamos esse feedback para melhorar o Teams.

> [!NOTE]
> As políticas de feedback não estão disponíveis em implantações GCC, GCC High ou DOD.

**O recurso Dar comentários**

Os usuários podem enviar comentários e sugestões sobre o Teams para nós, indo para **Ajudar**  >  **a dar comentários** no Teams. Os dados  enviados por meio de Feedback são considerados como "Dados de Suporte" em seu contrato do Microsoft 365 ou office 365, incluindo informações que, de outra forma, seriam consideradas "Dados do Cliente" ou "Dados Pessoais".

![Captura de tela da opção Dar comentários no Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Pesquisas**

Os usuários também podem taxar sua experiência com o Teams e nos enviar detalhes sobre a classificação que eles dão. Essa pesquisa pop-up é exibida para os usuários de tempos em tempos no Teams. Quando um usuário clica em **Fornecer comentários** na notificação, a pesquisa é exibida para que ele seja concluído.

![Captura de tela da notificação e do formulário de pesquisa no Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Definir se os usuários podem enviar comentários sobre o Teams para a Microsoft

Como administrador, você pode controlar se os usuários em sua  organização podem enviar comentários sobre o Teams para a Microsoft por meio de Comentários e se eles receberão a pesquisa. Por padrão, todos os usuários em sua organização são atribuídos automaticamente à política global (padrão em toda a organização) e o recurso Dar **comentários** e a pesquisa são habilitados na política. A exceção é o Teams for Education, onde os recursos são habilitados para professores e desabilitados para alunos.

Você pode editar a política global ou criar e atribuir uma política personalizada. Depois de editar a política global ou atribuir uma política personalizada, pode levar algumas horas para que as alterações entre em vigor.

Digamos, por exemplo, que você deseja permitir que  todos os usuários em sua organização enviem comentários por meio de Comentários e recebam pesquisas, exceto para novos contratados em treinamento. Nesse cenário, você cria uma política personalizada para desativar ambos os recursos e atribuí-la a novos contratados. Todos os outros usuários em sua organização obterão a política global com os recursos ativos.  

Você gerencia políticas de comentários usando o PowerShell. Use o cmdlet **New-CsTeamsFeedbackPolicy,** que pode ser encontrado aqui *, [](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* para criar uma política personalizada e o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-la a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição.

Para desativar e ativar os recursos, de definir os seguintes parâmetros:

 - **Comentários**: de definir o parâmetro  **userInitiatedMode** como habilitado para permitir que os usuários atribuídos à política deem feedback. A configuração do parâmetro como **desabilitado** desativa o recurso e os usuários que são atribuídos à política não têm a opção de dar comentários.
 - Pesquisas : de definir o parâmetro  **receiveSurveysMode** como habilitado para permitir que os usuários **atribuídos** à política recebam a pesquisa. Para que os usuários recebam a pesquisa e permitam que eles optem por não fazer isso, de definir o parâmetro **como enabledUserOverride**. No Teams, os usuários podem, em seguida, ir para **Configurações** Privacidade e escolher se  >   eles querem participar de pesquisas. A configuração do parâmetro como **desabilitado** desativa o recurso e os usuários atribuídos à política não receberão a pesquisa.

## <a name="create-a-custom-feedback-policy"></a>Criar uma política de comentários personalizada

Neste exemplo, criamos uma política de comentários chamada New Hire Feedback Policy e desativaremos a capacidade de dar comentários por meio de Comentários **e** da pesquisa.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Atribuir uma política de feedback personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Neste exemplo, atribuímos uma política personalizada chamada New Hire Feedback Policy a um usuário chamado user1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribua políticas a seus usuários no Teams](assign-policies.md)