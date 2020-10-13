---
title: Gerenciar políticas de comentários no Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Saiba como usar políticas de comentários para controlar se os usuários de equipes em sua organização podem enviar comentários sobre o Teams para a Microsoft.
ms.openlocfilehash: 0bece4515825a0d7ddf7e547f1607fbd6cf205cc
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433034"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gerenciar políticas de comentários no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Os usuários em sua organização podem enviar comentários sobre as equipes para a Microsoft nos informar como estamos fazendo, diretamente dentro dos clientes da área de trabalho e da Web do teams. Estamos melhorando continuamente a experiência do Teams e usamos esses comentários para melhorar a equipe.

> [!NOTE]
> Políticas de feedback não estão disponíveis em implantações GCC, GCC High ou DOD.

**O recurso fornecer comentários**

Os usuários podem enviar comentários e sugestões sobre equipes para nós indo para **ajudar**a enviar comentários sobre o Microsoft  >  **Give feedback** Teams. Os dados enviados por meio de **comentários** são considerados como "dados de suporte" em seu contrato do Microsoft 365 ou do Office 365, incluindo informações que, de outra forma, seriam consideradas "dados do cliente" ou "dados pessoais".

![Captura de tela da opção fornecer comentários no Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Formulários**

Os usuários também podem classificar sua experiência com o Microsoft Teams e nos enviar detalhes sobre a classificação que elas oferecem. Esta pesquisa instantânea é exibida para os usuários de tempos em tempos no Teams. Quando um usuário clica em **fornecer comentários** na notificação, a pesquisa é exibida para que elas sejam concluídas.

![Captura de tela da notificação de pesquisa e do formulário no Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Definir se os usuários podem enviar comentários sobre o Microsoft Teams para a Microsoft

Como administrador, você pode controlar se os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft por meio de **comentários** e se eles recebem a pesquisa. Por padrão, todos os usuários de sua organização recebem automaticamente a atribuição da política global (padrão da organização), e o recurso **fornecer comentários** e a pesquisa são habilitados na política. A exceção é o Teams for Education, em que os recursos são habilitados para professores e desabilitado para estudantes.

Você pode editar a política global ou criar e atribuir uma política personalizada. Depois de editar a política global ou atribuir uma política personalizada, pode demorar algumas horas para que as alterações entrem em vigor.

Digamos, por exemplo, permitir que todos os usuários em sua organização enviem comentários por meio de **comentários** e recebam pesquisas, exceto para novas contratações no treinamento. Nesse cenário, você cria uma política personalizada para desativar os dois recursos e atribuí-lo a novas contratações. Todos os outros usuários da sua organização obtêm a política global com os recursos ativados.  

Você gerencia políticas de comentários usando o PowerShell. Use o cmdlet **New-CsTeamsFeedbackPolicy** , *que pode ser [encontrado aqui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, para criar uma política personalizada e o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-lo a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição.

Para desativar e ativar os recursos, defina os seguintes parâmetros:

 - **Enviar comentários**: defina o parâmetro **useriniciad** como **Enabled** para permitir que os usuários atribuídos à política forneçam comentários. Definir o parâmetro como **desativado** desativa o recurso e os usuários atribuídos à política não têm a opção de enviar comentários.
 - **Pesquisas**: defina o parâmetro **receiveSurveysMode** como **Enabled** para permitir que os usuários atribuídos à política recebam a pesquisa. Para que os usuários recebam a pesquisa e permitam que eles se recusem, defina o parâmetro como **enabledUserOverride**. No Teams, os usuários podem ir até a privacidade **das configurações**  >  **Privacy** e escolher se desejam participar de pesquisas. Definir o parâmetro como **desativado** desativa o recurso e os usuários atribuídos a política não receberão a pesquisa.

## <a name="create-a-custom-feedback-policy"></a>Criar uma política de comentários personalizada

Neste exemplo, criamos uma política de comentários chamada nova política de feedback de contratar e desativamos a capacidade de enviar comentários por meio de **comentários** e a pesquisa.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Atribuir uma política de comentários personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Neste exemplo, atribuímos uma política personalizada chamada nova política de feedback de contratação a um usuário chamado Usuário1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas a seus usuários no Teams](assign-policies.md)