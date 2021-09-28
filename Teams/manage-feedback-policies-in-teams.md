---
title: Gerenciar políticas de comentários em Microsoft Teams
author: serdarsoysal
ms.author: serdars
manager: serdars
ms.reviewer: heprecel
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como usar políticas de comentários para controlar se Teams usuários em sua organização podem enviar comentários sobre Teams para a Microsoft.
ms.openlocfilehash: 582c5e39fca8dc37cefe8b480b2ff886779f6fa0
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59942096"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gerenciar políticas de comentários em Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Os usuários em sua organização podem enviar comentários sobre Microsoft Teams para nos dizer como estamos fazendo diretamente de dentro da área de trabalho Teams, clientes Web e dispositivos móveis. Estamos melhorando continuamente a experiência Teams e usamos esse feedback para melhorar Teams.

> [!NOTE]
> As políticas de feedback não estão disponíveis em implantações GCC, GCC High ou DOD.

**O **recurso Dar comentários****

Os usuários podem enviar comentários e sugestões sobre Teams para nós, indo para **Ajudar** a dar comentários Teams área de  >   trabalho e web.


![Dê uma opção de feedback Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

Acessar comentários em dispositivos móveis usando **Configurações**  >  **Ajuda & comentários** Enviar  >  **comentários**.

![Dê a opção de comentários em Teams no celular](media/feedback3.jpg)

 Os dados  enviados  por meio de Comentários de Envio e Envio são considerados como "Dados de Suporte" em seu contrato de Microsoft 365 ou Office 365, incluindo informações que, de outra forma, seriam consideradas "Dados do Cliente" ou "Dados Pessoais".


**Pesquisas**

Os usuários também podem taxar sua experiência com Teams e nos enviar detalhes sobre a classificação que eles dão. Essa pesquisa pop-up é exibida para os usuários de tempos em tempos Teams. Quando um usuário seleciona **Fornecer comentários** na notificação, a pesquisa é exibida para que ele seja concluído.

![a notificação e o formulário de pesquisa Teams.](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Definir se os usuários podem enviar comentários sobre Teams para a Microsoft

Como administrador, você pode controlar se os usuários em sua organização podem enviar comentários sobre Teams para a Microsoft e se eles receberão a pesquisa. Por padrão, todos os usuários em sua organização são atribuídos automaticamente à política global (padrão em toda a organização), e o recurso de comentários e a pesquisa são habilitados na política. A exceção é Teams para Educação, onde os recursos são habilitados para professores e desabilitados para alunos.

Você pode editar a política global ou criar e atribuir uma política personalizada. Depois de editar a política global ou atribuir uma política personalizada, pode levar algumas horas para que as alterações entre em vigor.

Digamos, por exemplo, que você deseja permitir que todos os usuários em sua organização enviem comentários e recebam pesquisas, exceto para novos contratados no treinamento. Nesse cenário, você cria uma política personalizada para desativar ambos os recursos e atribuí-la a novos contratados. Todos os outros usuários em sua organização obterão a política global com os recursos ativos.  

Você gerencia políticas de comentários usando o PowerShell. Use o [cmdlet **New-CsTeamsFeedbackPolicy**](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) para criar uma política personalizada. Use o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-lo a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição. Use **Set-CsTeamsFeedbackPolicy** para definir sinalizadores específicos.

Para desativar e ativar os recursos, de definir os seguintes parâmetros:

 - **Comentários**: de definir o parâmetro  **userInitiatedMode** como habilitado para permitir que os usuários atribuídos à política deem feedback. A configuração do parâmetro como **desabilitado** desativa o recurso e os usuários que são atribuídos à política não têm a opção de dar comentários.
 - Pesquisas : de definir o parâmetro  **receiveSurveysMode** como habilitado para permitir que os usuários **atribuídos** à política recebam a pesquisa. Para que os usuários recebam a pesquisa e permitam que eles optem por não fazer isso, de definir o parâmetro **como enabledUserOverride**. Em Teams, os usuários podem, em seguida, ir **Configurações** Privacidade e escolher se eles  >   querem participar de pesquisas. A configuração do parâmetro como **desabilitado** desativa o recurso e os usuários atribuídos à política não receberão a pesquisa.
 - **Email**: Use o **sinalizador AllowEmailCollection** para adicionar um campo de email.
 - **Conjunto de** log : Use o **sinalizador AllowLogCollection** para adicionar a aceitação do conjunto de log para usuários. No momento, o conjunto de log está habilitado apenas em dispositivos móveis. Para obter mais detalhes sobre quais dados são compartilhados por meio de logs, [saiba mais](https://go.microsoft.com/fwlink/?linkid=2168178).

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
