---
title: Gerenciar políticas de chamadas de emergência no Microsoft Teams
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
description: Saiba como usar e gerenciar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do teams na sua organização faz uma chamada de emergência.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: e58f428fbaa25b03534ce9f168ecf347b183eda3
ms.sourcegitcommit: d6e97621b1bfe9c3fbd8bc41b30a94bafd17b28f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49973135"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gerenciar políticas de chamadas de emergência no Microsoft Teams

Se a sua organização usar [planos de chamadas](set-up-calling-plans.md) ou [Roteamento direto do sistema telefônico](direct-routing-landing-page.md)implantado, você poderá usar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do teams na sua organização faz uma chamada de emergência. Você pode definir quem deseja notificar e como eles são notificados quando um usuário ao qual a política é atribuída faz chamadas de serviços de emergência. Por exemplo, você pode definir as configurações de política para notificar automaticamente a equipe de segurança da sua organização e fazer com que elas escutem em chamadas de emergência.  

Para gerenciar as políticas de chamadas de emergência ,  >  acesse **as políticas de emergência** de voz no centro de administração do Microsoft Teams ou usando o Windows PowerShell. As políticas podem ser atribuídas a usuários e [sites de rede](cloud-voice-network-settings.md).

Para os usuários, você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la. Para sites de rede, você cria e atribui políticas personalizadas.

Se você tiver atribuído uma política de chamadas de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.

## <a name="create-a-custom-emergency-calling-policy"></a>Criar uma política de chamadas de emergência personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  e clique na guia **políticas de chamadas** .
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.
4. Defina como você deseja notificar as pessoas em sua organização, geralmente a segurança, quando uma chamada de emergência é feita. Para fazer isso, em **modo de notificação**, selecione uma das seguintes opções:
    - **Enviar somente notificação**: uma mensagem de chat do teams é enviada aos usuários e grupos que você especificar.
    - **Em conferência com mudo ativado e não é possível desativar o mudo**: uma mensagem de chat do teams é enviada para os usuários e grupos que você especifica e podem ouvir (mas não participar) da conversa entre o chamador e o operador PSAP.
    - **Em conferência desativada, mas** pode desativar o mudo: uma mensagem de chat do teams é enviada para os usuários e grupos que você especifica e pode desativar mudo para ouvir e participar da conversa entre o chamador e o operador PSAP.
5.  Se você selecionou um dos modos de notificação **em mudo** , na caixa **números para discar para notificações de chamadas de emergência** , você pode digitar um número de telefone PSTN de um usuário ou grupo para chamar e ingressar na chamada de emergência. Por exemplo, digite o número da central de segurança da sua organização, que receberá uma chamada quando uma chamada de emergência for feita e poderá ouvi-la na chamada. Não é possível desativar o mudo do telefone PSTN mesmo quando o modo está definido como **em conferência em mudo, mas é possível desativar o mudo**.
6. Procure e selecione um ou mais usuários ou grupos, como a mesa de segurança da sua organização, para notificar quando uma chamada de emergência é feita.  A notificação pode ser enviada para endereços de email de usuários, grupos de distribuição e grupos de segurança. Um máximo de 50 usuários pode ser notificado.
7. Clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Veja [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Editar uma política de chamadas de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode editar a política global ou qualquer política personalizada criada.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  e clique na guia **políticas de chamadas** .
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Faça as alterações desejadas e clique em **aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Atribuir uma política de chamadas de emergência personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte também [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Atribuir uma política de chamadas de emergência personalizada a um site de rede

Use o cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de chamadas de emergência a um site de rede.

O exemplo a seguir mostra como atribuir uma política chamada política de chamada de emergência da Contoso 1 ao site do site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de roteamento de chamadas de emergência no Teams](manage-emergency-call-routing-policies.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md)
