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
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar políticas de comentários para controlar se os usuários de equipes em sua organização podem enviar comentários sobre o Teams para a Microsoft.
ms.openlocfilehash: 148ba1dc19eecba4e447dd7049ae580c920a7bdf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242145"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gerenciar políticas de comentários no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Os usuários em sua organização podem enviar comentários sobre as equipes para a Microsoft nos informar como estamos fazendo, diretamente dentro dos clientes da área de trabalho e da Web do teams. Estamos melhorando continuamente a experiência do Teams e usamos esses comentários para melhorar a equipe.

**O recurso fornecer comentários**

Os usuários podem enviar comentários e sugestões sobre equipes para nós indo para **ajudar** > a enviar**comentários** sobre o Microsoft Teams. Os dados enviados por meio de **comentários** são considerados como "dados de suporte" em seu contrato do Office 365, incluindo informações que, de outra forma, seriam consideradas "dados do cliente" ou "dados pessoais".

![Captura de tela da opção fornecer comentários no Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Formulários**

Os usuários também podem classificar sua experiência com o Microsoft Teams e nos enviar detalhes sobre a classificação que elas oferecem. Esta pesquisa instantânea é exibida para os usuários de tempos em tempos no Teams. Quando um usuário clica em **fornecer comentários** na notificação, a pesquisa é exibida para que elas sejam concluídas.

![Captura de tela da notificação de pesquisa e do formulário no Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Definir se os usuários podem enviar comentários sobre o Microsoft Teams para a Microsoft

Como administrador, você pode controlar se os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft por meio de **comentários** e se eles recebem a pesquisa. Por padrão, todos os usuários de sua organização recebem automaticamente a atribuição da política global (padrão da organização), e o recurso **fornecer comentários** e a pesquisa são habilitados na política. A exceção é o Teams for Education, em que os recursos são habilitados para professores e desabilitado para estudantes.

Você pode editar a política global ou criar e atribuir uma política personalizada. Se for atribuída uma política personalizada a um usuário, essa política se aplicará ao usuário. Se um usuário não estiver atribuído a uma política personalizada, a política global se aplicará ao usuário. Depois de editar a política global ou atribuir uma política, pode levar até 24 horas para que as alterações entrem em vigor.

Digamos, por exemplo, permitir que todos os usuários em sua organização enviem comentários por meio de **comentários** e recebam pesquisas, exceto para novas contratações no treinamento. Nesse cenário, você cria uma política personalizada para desativar os dois recursos e atribuí-lo a novas contratações. Todos os outros usuários da sua organização obtêm a política global com os recursos ativados.  

Use o cmdlet **New-CsTeamsFeedbackPolicy** para criar uma política personalizada e o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-lo a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição.

Para desativar e ativar os recursos, defina os seguintes parâmetros:

 - **Enviar comentários**: defina o **** parâmetro useriniciad como **Enabled** para permitir que os usuários atribuídos à política forneçam comentários. Definir o parâmetro como **desativado** desativa o recurso e os usuários atribuídos à política não têm a opção de enviar comentários.
 - **Pesquisas**: defina o parâmetro **receiveSurveysMode** como **Enabled** para permitir que os usuários atribuídos à política recebam a pesquisa. Para que os usuários recebam a pesquisa e permitam que eles se recusem, defina o parâmetro como **enabledUserOverride**. No Teams, os usuários podem ir até a**privacidade** **das configurações** > e escolher se desejam participar de pesquisas. Definir o parâmetro como **desativado** desativa o recurso e os usuários atribuídos a política não receberão a pesquisa.

## <a name="create-a-custom-feedback-policy"></a>Criar uma política de comentários personalizada

Neste exemplo, criamos uma política de comentários chamada nova política de feedback de contratar e desativamos a capacidade de enviar comentários por meio de **comentários** e a pesquisa.

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>Atribuir uma política de comentários personalizada

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>Atribuir uma política de comentários personalizada a um usuário

Neste exemplo, atribuímos uma política personalizada chamada nova política de feedback de contratação a um usuário chamado Usuário1.

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>Atribuir uma política de comentários personalizada aos usuários em um grupo

Você pode querer atribuir uma política de comentários personalizada a vários usuários que você já tenha identificado. Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança.

Neste exemplo, atribuímos uma política de comentários personalizada chamada nova política de feedback de contratação a todos os usuários no novo grupo contoso contratações.  

Obtenha o GroupObjectId do grupo específico.
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
Obter os membros do grupo especificado.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Atribua todos os usuários do grupo a uma política de comentários específica. Neste exemplo, a nova política de feedback para contratação.
```
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)