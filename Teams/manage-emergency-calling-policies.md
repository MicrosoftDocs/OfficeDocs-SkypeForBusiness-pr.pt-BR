---
title: Gerenciar políticas de chamadas de emergência no Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do Teams em sua organização faz uma chamada de emergência.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: a6fa08808c9ef5fc258236735cc043e4bde366b1
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551515"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gerenciar políticas de chamadas de emergência no Microsoft Teams

Se sua organização usa planos de chamada da Microsoft, conexão de operador, telefone móvel do Teams ou roteamento direto como sua opção de conectividade [PSTN](pstn-connectivity.md), você pode usar políticas de chamada de emergência no Microsoft Teams para definir o que acontece quando um usuário do Teams em sua organização faz uma chamada de emergência.

Você pode definir quem notificar e como eles são notificados quando um usuário que recebe a política chama os serviços de emergência. Por exemplo, você pode definir as configurações de política para notificar automaticamente o suporte de segurança da sua organização e fazer com que eles ouçam em chamadas de emergência.  

Você gerencia políticas de chamadas de emergência indo para políticas **de** > **Emergência** de Voz no Centro de administração do Microsoft Teams ou usando Windows PowerShell. As políticas podem ser atribuídas a usuários e [sites de rede](cloud-voice-network-settings.md).

Para usuários, você pode usar a política global (padrão em toda a organização) ou criar e atribuir políticas personalizadas. Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Tenha em mente que você pode editar as configurações na política global, mas não pode renomeá-la nem excluí-la. Para sites de rede, você cria e atribui políticas personalizadas.

Se você atribuiu uma política de chamada de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política atribuída ao site de rede substituirá a política atribuída ao usuário.

## <a name="create-a-custom-emergency-calling-policy"></a>Criar uma política de chamada de emergência personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá  >  para políticas de Emergência de Voz **e clique na** **guia Políticas de** chamada.

2. Clique em **Adicionar**.

3. Insira um nome e uma descrição para a política.

4. Defina **o modo de** pesquisa de localização externa como ativado para permitir que os usuários finais configurem seu endereço de emergência quando estiverem trabalhando em um local de rede fora da rede corporativa.

5. Defina como você deseja notificar as pessoas em sua organização, normalmente o suporte de segurança, quando uma chamada de emergência é feita. Para fazer isso, no **modo de notificação**, selecione um dos seguintes:

    - **Enviar notificação somente**: uma mensagem de chat do Teams é enviada aos usuários e grupos que você especificar.
    - **Conferência em mudo e** não é possível desativar o mudo: uma mensagem de chat do Teams é enviada aos usuários e grupos que você especifica e eles podem escutar (mas não participar) da conversa entre o chamador e o operador PSAP.
    - **Em conferência com mudo** mudo, mas é possível desativar o mudo: uma mensagem de chat do Teams é enviada aos usuários e grupos especificados e eles podem desativar o mudo para escutar e participar da conversa entre o chamador e o operador PSAP.

6.  Defina **o aviso de isenção de** responsabilidade do serviço de emergência para mostrar uma faixa para lembrar os usuários finais de confirmar o local de emergência.

7.  Se você selecionou uma  das Conferências em modos de notificação com mudo, na caixa Números para discar para notificações de chamadas de emergência, poderá inserir um número de telefone PSTN de um usuário ou grupo para ligar e ingressar na chamada de emergência. Por exemplo, insira o número do suporte de segurança da sua organização, que receberá uma chamada quando uma chamada de emergência for feita e poderá escutar na chamada. O telefone PSTN não pode ser alternado mesmo quando o modo é definido como Conferência em mudo mudo, mas é capaz de **desativar o mudo**.

8. Pesquise e selecione um ou mais usuários ou grupos, como o suporte de segurança da sua organização, para notificar quando uma chamada de emergência é feita.  A notificação pode ser enviada para endereços de email de usuários, grupos de distribuição e grupos de segurança. Um máximo de 50 usuários pode ser notificado.

9. Clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Editar uma política de chamada de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode editar a política global ou quaisquer políticas personalizadas que criar.

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá  >  para políticas de Emergência de Voz **e clique na** **guia Políticas de** chamada.
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. Faça as alterações desejadas e clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Atribuir uma política de chamada de emergência personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte também [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Atribuir uma política de chamada de emergência personalizada a um site de rede

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode atribuir a política global ou quaisquer políticas personalizadas que criar.

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, **acesse a** > **topologia Rede** de Locais e clique na **guia Sites de** rede.
2. Selecione o site clicando à esquerda do nome e clique em **Editar**.
3. Em **Política de chamada de emergência**, selecione a política e clique em **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell
Use o cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de chamada de emergência a um site de rede.

O exemplo a seguir mostra como atribuir uma política chamada Contoso Emergency Calling Policy 1 ao site Site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de roteamento de chamadas de emergência no Teams](manage-emergency-call-routing-policies.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)
