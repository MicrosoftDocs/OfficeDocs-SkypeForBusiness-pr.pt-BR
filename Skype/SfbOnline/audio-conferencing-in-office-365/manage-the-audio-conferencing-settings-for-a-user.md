---
title: Gerenciar as configurações de conferência de áudio para um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Como um administrador do Office 365, você pode editar as configurações de conferência de áudio — como o provedor, tarifas padrão ou número de discagem gratuito, ID de conferência ou PIN — para um usuário individual em sua organização. Se você deseja editar as configurações para a sua organização, consulte Manage a conferência de áudio configurações para minha organização.
ms.openlocfilehash: 064625919cab532c10cdadd16ad95e144d301419
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703370"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user"></a>Gerenciar as configurações de conferência de áudio para um usuário

Como um administrador do Office 365, você pode editar as configurações de conferência de áudio — como o provedor, tarifas padrão ou número de discagem gratuito, ID de conferência ou PIN — para um usuário individual em sua organização. Se você deseja editar as configurações para a sua organização, consulte [Gerenciar as configurações de áudio da conferência para minha organização](manage-the-audio-conferencing-settings-for-my-organization.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, modifique qualquer uma das seguintes opções:

|**Configuração**|**Descrição**|
|:-----|:-----|
|**Serviços de audioconferência**|Para ativar a conferência de áudio ou desativado para o usuário, clique em **Editar** ao lado de **Conferência de áudio**e, em seguida, no painel de **Serviços de audioconferência** , alterne **audioconferências** ativada ou desativada.|
|**Enviar informações de conferência em email**  |Clique neste link apenas se você quiser imediatamente, envie um email para o usuário com sua conferência ID e número de telefone. (Este email não inclui o PIN.) Consulte [Enviar um email para um usuário com as informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).  |
|**ID de conferência**  |Clique em **Redefinir ID de conferência** , se você precisar redefinir o ID de conferência para o usuário. Para obter mais informações, consulte [Redefinir uma ID de conferência para um usuário](reset-a-conference-id-for-a-user.md).  |
|**PIN** |Se você precisar redefinir o PIN do usuário, clique em **Redefinir PIN** . Para obter mais informações, consulte [Redefinir o PIN de conferência de áudio](reset-the-audio-conferencing-pin.md). |
|**Padrão de número de telefone de Chamada Tarifada de conferência** (necessário) |Estes serão os números que estão definidos a ponte de conferência de áudio. Formate os números de como você deseja que apareçam na Skype para solicitações de reunião de negócios e Teams da Microsoft. Para alterar o número de Chamada Tarifada padrão, clique em **Editar** Avançar para **conferência de áudio** e além do painel de **Conferência de áudio** , selecione um número em um **número de Chamada Tarifada**. |
|**Convites deste usuário podem incluir o número de chamada gratuito**|Para alterar essa configuração, clique em **Editar** ao lado de **Conferência de áudio** e no painel de **Conferência de áudio** , ativar ou desativar o **incluir números para ligações gratuitas nas solicitações deste usuário de reunião** . |
|**Permissões de discagem**|Para alterar essa configuração, clique em **Editar** ao lado de **Conferência de áudio** e no painel de **Conferência de áudio** , escolha uma opção em **permissão de discagem de reuniões**.|

![Mostra as configurações de conferência de áudio para um usuário](../images/sfbaudioconf-usersettings.png)
 
![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**
 
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Escolha **Centros de administração** > **Skype for Business**.
    
3. No Skype para centro de administração de negócios, escolha **usuários**.
    
4. Selecione o usuário para o qual você deseja gerenciar as configurações e, em seguida, no painel de ações, clique em **Editar**![mostra o ícone Editar](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Escolha a **conferência de áudio** no painel de navegação esquerdo e, em seguida, na página **Propriedades** do usuário, modifique qualquer uma das seguintes opções:
    
|**Configuração**|**Descrição**|
|:-----|:-----|
|**Nome do provedor** <br/> |Escolha seu provedor da lista.  <br/><br/> **Observação:** O restante das configurações nessa tabela se aplicam somente se você selecionar Microsoft como um provedor de serviços de audioconferência.           |
|**Número de Chamada Tarifada padrão** (necessário) <br/> |Para um provedores de terceiros, esses números de telefone são os que você recebeu do provedor de serviços de audioconferência. Se o usuário está usando o Microsoft como um provedor de serviços de audioconferência, estes serão os números que estão definidos a ponte de conferência de áudio. Formate os números de como você deseja que apareçam na Skype para solicitações de reunião de negócios e Teams da Microsoft.  <br/> |
|**Número de chamada gratuito padrão** <br/> |Para um provedores de terceiros, esses números de telefone são os que você recebeu do provedor de serviços de audioconferência. Se o usuário está usando o Microsoft como um provedor de serviços de audioconferência, estes serão os números que estão definidos a ponte de conferência de áudio. Formate os números de como você deseja que apareçam na Skype para solicitações de reunião de negócios e Teams da Microsoft.  <br/> |
|**Permitir usando números para ligações gratuitas na ponte Microsoft da sua organização para ingressar em reuniões deste usuário** <br/> |Selecione essa opção se desejar permitir que o usuário de números para ligações gratuitas para participar de reuniões.  <br/> |
|**Enviar informações de conferência via email** <br/> |Clique neste link apenas se você quiser imediatamente, envie um email para o usuário com sua conferência ID e número de telefone. (Este email não inclui o PIN.) Consulte [Enviar um email para um usuário com as informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**ID de conferência** <br/> |Selecione **Redefinir** se você precisar redefinir o ID de conferência para o usuário. Para obter mais informações, consulte [Redefinir uma ID de conferência para um usuário](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Selecione **Redefinir** se você precisar redefinir o PIN do usuário. Para obter mais informações, consulte [Redefinir o PIN de conferência de áudio](reset-the-audio-conferencing-pin.md).  <br/> |
|**Permitir que os chamadores não autenticados ser as primeira pessoas em uma reunião** <br/> |Selecione essa opção para permitir que os chamadores não-autenticados seja o primeiro a ingressar em reuniões.  <br/> |
|**Restrições a serem dial-outs de reuniões deste usuário** <br/> |Selecione uma opção nessa lista se desejar restringir transferências de discagem para apenas domésticas ou se desejar impedir todas as transferências de discagem de reuniões.  <br/> |
  
![Mostra a página de propriedades de conferência de áudio para um usuário](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência em minha organização](manage-the-audio-conferencing-settings-for-my-organization.md)

[Perguntas comuns sobre a Audioconferência](audio-conferencing-common-questions.md)
