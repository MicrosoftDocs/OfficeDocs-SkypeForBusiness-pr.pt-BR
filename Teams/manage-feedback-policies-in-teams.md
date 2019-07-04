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
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540949"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gerenciar políticas de comentários no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Os usuários podem enviar comentários e sugestões sobre o Microsoft Teams para a Microsoft para **ajudar** > a**fornecer comentários** sobre os clientes do teams. Estamos melhorando continuamente a experiência do Teams e usamos esses comentários para melhorar a equipe.

![Captura de tela da opção fornecer comentários no Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

Os dados enviados por meio de **comentários** são considerados como "dados de suporte" em seu contrato do Office 365, incluindo informações que, de outra forma, seriam consideradas "dados do cliente" ou "dados pessoais".

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Definir se os usuários podem enviar comentários sobre o Microsoft Teams para a Microsoft

Como administrador, você pode controlar se os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft. Por padrão, todos os usuários de sua organização recebem automaticamente a política global (padrão para toda a organização) e o recurso é habilitado na política. A exceção é o Teams for Education, em que o recurso está habilitado para professores e desabilitado para estudantes.

Você pode editar a política global ou criar e atribuir uma política personalizada. Se for atribuída uma política personalizada a um usuário, essa política se aplicará ao usuário. Se um usuário não estiver atribuído a uma política personalizada, a política global se aplicará ao usuário. Depois de editar a política global ou atribuir uma política, pode levar até 24 horas para que as alterações entrem em vigor.

Digamos, por exemplo, que você queira permitir que todos os usuários da sua organização enviem comentários, exceto para novas contratações no treinamento. Nesse cenário, você cria uma política personalizada para desativar o recurso e atribuí-lo a novas contratações. Todos os outros usuários da sua organização obtêm a política global com o recurso ativado.  

Use o cmdlet **New-CsTeamsFeedbackPolicy** para criar uma política personalizada e o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-lo a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição. 

Defina o **** parâmetro userinicioumode como **Enabled** para permitir que os usuários atribuídos à política forneçam comentários. Definir o parâmetro como **desativado** desativa o recurso e os usuários atribuídos à política não têm a opção de enviar comentários.

## <a name="create-a-custom-feedback-policy"></a>Criar uma política de comentários personalizada

Neste exemplo, criamos uma política de comentários chamada nova política de feedback de contratar e desativamos a capacidade de enviar comentários.

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
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
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)