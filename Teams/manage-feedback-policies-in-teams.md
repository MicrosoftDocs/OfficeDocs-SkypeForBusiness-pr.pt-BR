---
title: Gerenciar políticas de comentários no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Saiba como usar políticas de comentários para controlar se os usuários do Teams em sua organização podem enviar comentários sobre o Teams para a Microsoft.
ms.openlocfilehash: 7fcfa1738f7dbbc0f7c70afec86e9e2f181d6d21
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713339"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gerenciar políticas de comentários no Microsoft Teams

Os usuários em sua organização podem enviar comentários sobre o Microsoft Teams para nos informar como estamos fazendo diretamente de dentro da área de trabalho do Teams, clientes Web e dispositivos móveis. Estamos melhorando continuamente a experiência do Teams e usamos esses comentários para melhorar o Teams.

> [!NOTE]
> As políticas de comentários não estão disponíveis em implantações GCC, GCC High ou DOD.

**O **recurso Fornecer comentários****

Os usuários podem enviar comentários e sugestões sobre o Teams para nós acessando **Ajuda** > **para fornecer comentários** na área de trabalho e na Web do Teams.


![Fornecer a opção de comentários no Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

Acessar comentários no celular usando **a Ajuda de Configurações** > **& enviar comentários** > .

![Fornecer a opção de comentários no Teams em dispositivos móveis](media/feedback3.jpg)

 Os dados enviados  por meio de Fornecer comentários e Enviar **comentários** são considerados "Dados de Suporte" em seu contrato do Microsoft 365 ou Office 365, incluindo informações que, de outra forma, seriam consideradas "Dados do Cliente" ou "Dados Pessoais".



**Pesquisas**

Os usuários também podem classificar sua experiência com o Teams e nos enviar detalhes sobre a classificação fornecida por eles. Essa pesquisa pop-up é exibida aos usuários de tempos em tempos no Teams. Quando um usuário seleciona **Fornecer comentários** na notificação, a pesquisa é exibida para que ele seja concluído.

![a notificação e formulário da pesquisa no Teams.](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Definir se os usuários podem enviar comentários sobre o Teams para a Microsoft

Como administrador, você pode controlar se os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft e se eles recebem a pesquisa. Por padrão, todos os usuários em sua organização recebem automaticamente a política global (padrão em toda a organização) e o recurso de comentários e a pesquisa são habilitados na política. A exceção é Teams para Educação, em que os recursos são habilitados para professores e desabilitados para alunos.

Você pode editar a política global ou criar e atribuir uma política personalizada. Depois de editar a política global ou atribuir uma política personalizada, pode levar algumas horas para que as alterações entre em vigor.

Por exemplo, você deseja permitir que todos os usuários em sua organização enviem comentários e recebam pesquisas, exceto para novas contratações no treinamento. Nesse cenário, você cria uma política personalizada para desativar os dois recursos e atribuí-la a novas contratações. Todos os outros usuários em sua organização obtêm a política global com os recursos ativados.  

Gerencie políticas de comentários usando o PowerShell. Use o [cmdlet **New-CsTeamsFeedbackPolicy**](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) para criar uma política personalizada. Use o cmdlet **Grant-CsTeamsFeedbackPolicy para atribuí-lo** a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição. Use **Set-CsTeamsFeedbackPolicy** para definir sinalizadores específicos.

Para desativar e ativar os recursos, defina os seguintes parâmetros:

 - **Enviar comentários**: defina **o parâmetro userInitiatedMode** como habilitado para permitir que os usuários atribuídos à política forneçam comentários. Definir o parâmetro como **desabilitado** desativa o recurso e os usuários que recebem a política não têm a opção de fornecer comentários.

 - Pesquisas: defina o **parâmetro receiveSurveysMode** como  habilitado para permitir que os usuários **atribuídos** à política recebam a pesquisa. Para que os usuários recebam a pesquisa e permitam que eles recusem, defina o parâmetro **como enabledUserOverride**. No Teams, os usuários podem acessar **Configurações de** > **Privacidade** e escolher se querem participar de pesquisas. Definir o parâmetro como **desabilitado** desativa o recurso e os usuários que recebem a política não receberão a pesquisa.

 - **Email**: use o **sinalizador AllowEmailCollection** para adicionar um campo de email.
 - **Coleção de** logs: use **o sinalizador AllowLogCollection** para adicionar a aceitação da coleção de logs para os usuários. Atualmente, a coleta de logs está habilitada somente em dispositivos móveis. Para obter mais detalhes sobre quais dados são compartilhados por meio de logs, [saiba mais](https://go.microsoft.com/fwlink/?linkid=2168178).

## <a name="create-a-custom-feedback-policy"></a>Criar uma política de comentários personalizada

Neste exemplo, criamos uma política de comentários chamada Política de Comentários de Nova Contratação e desativamos a capacidade de enviar comentários por meio de Fornecer **comentários** e da pesquisa.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Atribuir uma política de comentários personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Neste exemplo, atribuímos uma política personalizada chamada Política de Comentários de Nova Contratação a um usuário chamado user1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)
