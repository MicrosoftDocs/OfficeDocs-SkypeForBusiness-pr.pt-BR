---
title: Gerenciar políticas de chamada de emergência no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de chamada de emergência no Microsoft Teams para definir o que acontece quando um usuário do Teams em sua organização faz uma chamada de emergência.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120562"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gerenciar políticas de chamada de emergência no Microsoft Teams

Se sua organização usa [Planos](set-up-calling-plans.md) de Chamada ou roteamento Direto do Sistema de Telefonia [implantado,](direct-routing-landing-page.md)você pode usar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do Teams em sua organização faz uma chamada de emergência. Você pode definir quem notificar e como eles são notificados quando um usuário que recebe a política chama os serviços de emergência. Por exemplo, você pode definir configurações de política para notificar automaticamente o escritório de segurança da sua organização e fazer com que eles ouçam chamadas de emergência.  

Você gerencia políticas de chamadas de emergência indo **para** políticas de Emergência de Voz no Centro de administração do Microsoft Teams ou  >   usando Windows PowerShell. As políticas podem ser atribuídas a usuários e [sites de rede.](cloud-voice-network-settings.md)

Para usuários, você pode usar a política global (padrão em toda a organização) ou criar e atribuir políticas personalizadas. Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la. Para sites de rede, você cria e atribui políticas personalizadas.

Se você atribuiu uma política de chamada de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política atribuída ao site de rede substituirá a política atribuída ao usuário.

## <a name="create-a-custom-emergency-calling-policy"></a>Criar uma política de chamada de emergência personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Políticas de Emergência de Voz e clique  >  na guia **Políticas de** chamadas.
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.
4. De definir como você deseja notificar as pessoas em sua organização, normalmente o escritório de segurança, quando uma chamada de emergência é feita. Para fazer isso, em **Modo de Notificação,** selecione um dos seguintes:
    - **Somente notificação de** envio: uma mensagem de chat do Teams é enviada para os usuários e grupos que você especificar.
    - **Conferência em mudo** e não é possível desativar : uma mensagem de chat do Teams é enviada aos usuários e grupos que você especificar e eles podem ouvir (mas não participar) da conversa entre o chamador e o operador PSAP.
    - **Conferência em mudo,** mas são capazes de desativar : uma mensagem de chat do Teams é enviada para os usuários e grupos que você especificar e eles podem desatar para ouvir e participar da conversa entre o chamador e o operador PSAP.
5.  Se você selecionou uma das Conferências em  modos de notificação em mudo, na caixa Números para discar para notificações de chamadas de emergência, você pode inserir um número de telefone PSTN de um usuário ou grupo para chamar e ingressar na chamada de emergência.  Por exemplo, insira o número do escritório de segurança da sua organização, que receberá uma chamada quando uma chamada de emergência for feita e poderá ouvir a chamada. O telefone PSTN não pode ser desmutado mesmo quando o modo é definido como Conferenced em mudo, mas é capaz de **desmute**.
6. Procure e selecione um ou mais usuários ou grupos, como o escritório de segurança da sua organização, para notificar quando uma chamada de emergência é feita.  A notificação pode ser enviada para endereços de email de usuários, grupos de distribuição e grupos de segurança. No máximo 50 usuários podem ser notificados.
7. Clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Editar uma política de chamada de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode editar a política global ou quaisquer políticas personalizadas que você criar.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Políticas de Emergência de Voz e clique  >  na guia **Políticas de** chamadas.
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. Faça as alterações que você deseja e clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Atribuir uma política de chamada de emergência personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte também [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Atribuir uma política de chamada de emergência personalizada a um site de rede

Use o cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de chamada de emergência a um site de rede.

O exemplo a seguir mostra como atribuir uma política chamada Contoso Emergency Calling Policy 1 ao site Site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de roteamento de chamadas de emergência no Teams](manage-emergency-call-routing-policies.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Atribua políticas a seus usuários no Teams](assign-policies.md)