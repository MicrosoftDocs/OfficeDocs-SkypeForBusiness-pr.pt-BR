---
title: Gerenciar políticas de chamada de emergência no Microsoft Teams
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
description: Saiba como usar e gerenciar políticas de chamada de emergência no Microsoft Teams para definir o que acontece quando um usuário do Teams em sua organização faz uma chamada de emergência.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 1d2dc0e2213f6294e2c596722a4f5ab49bec8487
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727743"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gerenciar políticas de chamada de emergência no Microsoft Teams

Se sua organização usar Planos de Chamada da Microsoft, Operator Connect, Teams Phone Mobile ou Roteamento Direto como [sua opção de conectividade PSTN](pstn-connectivity.md), você poderá usar políticas de chamada de emergência no Microsoft Teams para definir o que acontece quando um usuário do Teams em sua organização faz uma chamada de emergência.

Você pode definir quem notificar e como eles são notificados quando um usuário que recebe a política chama serviços de emergência. Por exemplo, você pode configurar as configurações de política para notificar automaticamente o balcão de segurança da sua organização e fazer com que elas ouçam em chamadas de emergência.  

Você gerencia políticas de chamada de emergência acessando **políticas de Emergência** de **Voz** >  no centro de administração do Microsoft Teams ou usando Windows PowerShell. As políticas podem ser atribuídas a usuários e [sites de rede](cloud-voice-network-settings.md).

Para usuários, você pode usar a política global (padrão em toda a organização) ou criar e atribuir políticas personalizadas. Os usuários obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Tenha em mente que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la. Para sites de rede, você cria e atribui políticas personalizadas.

Se você atribuiu uma política de chamada de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política atribuída ao site de rede substituirá a política atribuída ao usuário.

## <a name="create-a-custom-emergency-calling-policy"></a>Criar uma política de chamada de emergência personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Políticas de Emergência de** **Voz** >  e clique na guia **Políticas de chamada**.

2. Clique em **Adicionar**.

3. Insira um nome e uma descrição para a política.

4. Defina o **modo de pesquisa de localização externa** como ativado para permitir que os usuários finais configurem o endereço de emergência quando estiverem trabalhando em um local de rede fora da rede corporativa.

5. Defina como você deseja notificar as pessoas em sua organização, normalmente o balcão de segurança, quando uma chamada de emergência é feita. Para fazer isso, no **modo de notificação**, selecione um dos seguintes procedimentos:

    - **Enviar somente notificação**: uma mensagem de chat do Teams é enviada aos usuários e grupos que você especificar.
    - **Conferência em mas são mudos**: uma mensagem de chat do Teams é enviada aos usuários e grupos que você especifica e eles podem ouvir (mas não participar) na conversa entre o chamador e o operador PSAP.
    - **Conferência e não deslocamento**: uma mensagem de chat do Teams é enviada aos usuários e grupos que você especifica e eles podem desmutar para ouvir e participar da conversa entre o chamador e o operador PSAP.

6.  Defina a **isenção de responsabilidade do serviço de** emergência para mostrar uma faixa para lembrar os usuários finais para confirmar o local de emergência.

7.  Se você selecionou uma das **conferências em** modos de notificação mudos, na caixa **Números para discar para notificações de chamadas de emergência** , você poderá inserir um número de telefone PSTN de um usuário ou grupo para chamar e ingressar na chamada de emergência. Por exemplo, insira o número do balcão de segurança da sua organização, que receberá uma chamada quando uma chamada de emergência for feita e, em seguida, poderá escutar na chamada. O telefone PSTN não pode ser desmutado mesmo quando o modo é definido como **Conferenced em mudo, mas é capaz de desmutar**.

8. Defina quem você deseja notificar quando uma chamada de emergência for feita, por exemplo, o pessoal do seu repositório de segurança. Você pode definir uma lista de usuários, grupos de distribuição ou grupos de segurança. No máximo 50 usuários podem ser notificados.

9. Clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Editar uma política de chamada de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode editar a política global ou quaisquer políticas personalizadas que você criar.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Políticas de Emergência de** **Voz** >  e clique na guia **Políticas de chamada**.
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. Faça as alterações desejadas e clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Atribuir uma política de chamada de emergência personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte também [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Atribuir uma política de chamada de emergência personalizada a um site de rede

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode atribuir a política global ou quaisquer políticas personalizadas que você criar.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Topologia de Rede** de **Locais** >  e clique na guia **Sites** de rede.
2. Selecione o site clicando à esquerda do nome e clique em **Editar**.
3. Em **Política de chamada de emergência**, selecione a política e clique em **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell
Use o cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de chamada de emergência a um site de rede.

O exemplo a seguir mostra como atribuir uma política chamada Contoso Emergency Calling Policy 1 ao site site do Site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de roteamento de chamadas de emergência no Teams](manage-emergency-call-routing-policies.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)
