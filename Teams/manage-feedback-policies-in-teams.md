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
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804691"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gerenciar políticas de comentários no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft para nos dizer como estamos fazendo, diretamente na área de trabalho do Teams e em clientes Web. Estamos melhorando continuamente a experiência do Teams e usamos esse comentário para melhorar o Teams.

> [!NOTE]
> As políticas de comentários não estão disponíveis nas implantações GCC, GCC High ou DOD.

**O recurso Dar comentários**

Os usuários podem enviar comentários e sugestões sobre o Teams para nós, indo para **Ajudar**  >  **a enviar comentários** no Teams. Os dados enviados por meio de Enviar **comentários** são considerados como "Dados de Suporte" sob seu contrato do Microsoft 365 ou do Office 365, incluindo informações que, de outra forma, seriam consideradas "Dados do Cliente" ou "Dados Pessoais".

![Captura de tela da opção Dar comentários no Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Pesquisas**

Os usuários também podem taxar sua experiência com o Teams e nos enviar detalhes sobre a classificação que eles dão. Esta pesquisa pop-up é exibida para os usuários de tempos em tempos no Teams. Quando um usuário clica em **Fornecer comentários** na notificação, a pesquisa é exibida para que ele seja concluído.

![Captura de tela da notificação e formulário da pesquisa no Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Definir se os usuários podem enviar comentários sobre o Teams para a Microsoft

Como administrador, você pode controlar se os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft por meio de Enviar **comentários** e se eles recebem a pesquisa. Por padrão, todos os usuários em sua organização são atribuídos automaticamente à política global (padrão de toda a organização), e o recurso Enviar **comentários** e a pesquisa são habilitados na política. A exceção é o Teams for Education, onde os recursos são habilitados para professores e desabilitados para alunos.

Você pode editar a política global ou criar e atribuir uma política personalizada. Depois de editar a política global ou atribuir uma política personalizada, pode levar algumas horas para que as alterações entre em vigor.

Por exemplo, você deseja permitir que todos os usuários em sua organização enviem comentários por meio de Enviar **comentários** e receber pesquisas, exceto para novos contratados no treinamento. Nesse cenário, você cria uma política personalizada para desativar os dois recursos e atribuí-la a novas contratações. Todos os outros usuários em sua organização ficam com a política global com os recursos ativos.  

Você gerencia políticas de comentários usando o PowerShell. Use o cmdlet **New-CsTeamsFeedbackPolicy,** que pode ser encontrado *aqui, [](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* para criar uma política personalizada e o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-lo a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição.

Para desativar e ativar os recursos, de definir os seguintes parâmetros:

 - **Fazer comentários:** De definir o parâmetro  **userInitiatedMode** para habilitado para permitir que os usuários que têm a política sejam atribuídos a fazer comentários. Definir o parâmetro para **desabilitar** desativa o recurso, e os usuários que têm a política atribuída não têm a opção de fazer comentários.
 - **Pesquisas:** De definir o **parâmetro receiveSurveysMode** para habilitado para permitir que os usuários que receberam a política recebam a pesquisa.  Para que os usuários recebam a pesquisa e permitam que eles optem por não fazer isso, de definir o parâmetro para **habilitar oUserOverride.** No Teams, os usuários podem ir para **Configurações de** Privacidade e escolher se  >   querem participar de pesquisas. Definir o parâmetro para **desabilitar** desativa o recurso, e os usuários que receberam a política não receberão a pesquisa.

## <a name="create-a-custom-feedback-policy"></a>Criar uma política de comentários personalizada

Neste exemplo, criamos uma política de comentários chamada Política de Comentários de Nova Contratação e desligamos a capacidade de fazer comentários por meio de Dar **comentários** e da pesquisa.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Atribuir uma política de comentários personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Neste exemplo, atribuímos uma política personalizada chamada Política de Comentários de Nova Contratação a um usuário chamado usuário1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribua políticas a seus usuários no Teams](assign-policies.md)