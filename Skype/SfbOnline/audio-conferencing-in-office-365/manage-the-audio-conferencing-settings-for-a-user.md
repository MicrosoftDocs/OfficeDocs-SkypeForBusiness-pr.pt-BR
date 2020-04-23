---
title: Gerenciar as configurações de audioconferência para um usuário no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Como um administrador do Office 365, você pode editar as configurações de audioconferência do Skype for Business Online — como o provedor, número padrão de chamada tarifada ou de chamada gratuita, ID de conferência ou PIN — para um usuário individual em sua organização. '
ms.openlocfilehash: fe6814bee547e80d6bcb6fc367d055dce13d513d
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777986"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Gerenciar as configurações de audioconferência para um usuário no Skype for Business Online

> [!Note]
> Se você deseja gerenciar a configurações de usuário no Microsoft Teams, consulte [Gerenciar as configurações de audioconferência para um usuário no Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

As an Office 365 admin, you can edit the Audio Conferencing settings—such as the provider, default toll or toll-free number, conference ID, or PIN—for an individual user in your organization. If you want to edit settings for your organization, see [Manage the Audio Conferencing settings for my organization](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Entre com sua conta corporativa ou de estudante.
    
2. Escolha **Centros de administração** > **Skype for Business**.
    
3. No centro de administração do Skype for Business, escolha **usuários**.
    
4. Selecione o usuário para o qual você deseja gerenciar as configurações e, em seguida, no painel de ações, clique em **Editar**![Exibe o ícone Editar](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Escolha **Audioconferência** no painel de navegação esquerdo e, em seguida, na página **Propriedades** do usuário, modifique qualquer uma das seguintes opções:
    
|**Configuração**|**Descrição**|
|:-----|:-----|
|**Nome do provedor** <br/> |Escolha seu provedor na lista.  <br/><br/> **Observação:** O restante das configurações nesta tabela se aplicam somente se você selecionar Microsoft como um provedor de audioconferência.           |
|**Número de Chamada Tarifada padrão** (necessário) <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Número de chamada gratuita padrão** <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Permita o uso de números de chamada gratuita na ponte do Microsoft de sua organização para ingressar em reuniões deste usuário** <br/> |Selecione essa opção se desejar permitir que o usuário de números de chamada gratuita participe de reuniões.  <br/> |
|**Enviar informações de conferência por email** <br/> |Click this link only if you want to immediately send an email to the user with his or her conference ID and phone number. (This email does not include the PIN.) See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**ID de conferência** <br/> |Select **Reset** if you need to reset the conference ID for the user. For more information, see [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Select **Reset** if you need to reset the PIN for the user. For more information, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).  <br/> |
|**Permitir que os chamadores não autenticados sejam as primeira pessoas em uma reunião** <br/> |Selecione essa opção para permitir que os chamadores não autenticados sejam os primeiros a ingressarem em reuniões.  <br/> |
|**Restrições para chamadas de reuniões deste usuário** <br/> |Selecione uma opção nessa lista se desejar restringir as chamadas apenas para domésticas ou se desejar impedir todas as chamadas de reuniões.  <br/> |
  
![Exibe a página Propriedades de audioconferência para um usuário](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência em minha organização](manage-the-audio-conferencing-settings-for-my-organization.md)

[Perguntas comuns sobre a Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions)
