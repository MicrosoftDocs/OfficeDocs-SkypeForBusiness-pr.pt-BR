---
title: Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de roteamento de chamadas de emergência Microsoft Teams configurar números de emergência e especificar como as chamadas de emergência são roteada.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 582036d6168a235744b092f7f11bfd34442f5221
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634910"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto

Se você tiver [](direct-routing-landing-page.md) implantado o Roteamento Direto em sua organização, poderá usar políticas de roteamento de chamadas de emergência Microsoft Teams configurar números de emergência e especificar como as chamadas de emergência são roteadas. Uma política de roteamento de chamadas de emergência determina se os serviços de emergência aprimorados estão habilitados para usuários atribuídos à política, os números usados para chamar serviços de emergência (por exemplo, 911 nos Estados Unidos) e como as chamadas para serviços de emergência são roteadas. 

> [!Note]
> **Observe que essas políticas de roteamento de chamadas aplicam-se apenas ao Roteamento Direto , elas não se aplicam a Planos de Chamadas ou operador Conexão.**

Você gerencia políticas de roteamento de chamadas de emergência indo para políticas de Emergência de Voz no centro de administração Microsoft Teams   >   ou usando Windows PowerShell. As políticas podem ser atribuídas a usuários e [sites de rede.](cloud-voice-network-settings.md)

Para usuários, você pode usar a política global (padrão em toda a organização) ou criar e atribuir políticas personalizadas. Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la. Para sites de rede, você cria e atribui políticas personalizadas.

Se você atribuiu uma política de roteamento de chamadas de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política atribuída ao site de rede substituirá a política atribuída ao usuário.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Criar uma política de roteamento de chamadas de emergência personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Políticas de Emergência de Voz e clique na guia Políticas de  >   **roteamento de** chamadas.
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.
4. Para habilitar a chamada de emergência dinâmica, ative **a chamada de emergência dinâmica.** Quando a chamada de emergência dinâmica é habilitada, Teams recupera informações de política e local do serviço e inclui essas informações como parte da chamada de emergência.
5. Defina um ou mais números de emergência. Para fazer isso, em **Números de emergência,** clique em **Adicionar** e faça o seguinte:
    1. **Cadeia de caracteres de discagem** de emergência : Insira a cadeia de caracteres de discagem de emergência. Essa cadeia de caracteres de discagem indica que uma chamada é uma chamada de emergência.
        > [!NOTE]
        > **Para Roteamento Direto, Teams clientes não enviam mais chamadas de emergência com um "+" na frente da cadeia de caracteres de discagem de emergência. Certifique-se de que o padrão de rota de voz para corresponder a uma cadeia de caracteres de discagem de emergência reflita essa alteração.**
    2. **Máscara de discagem de** emergência : Para cada número de emergência, você pode especificar zero ou mais máscaras de discagem de emergência. Uma máscara de discagem é o número que você deseja converter no valor da cadeia de caracteres de discagem de emergência. Isso permite que números de emergência alternativos sejam discados e ainda tenham a chamada para alcançar os serviços de emergência. <br>Por exemplo, você adiciona 112 como máscara de discagem de emergência, que é o número de serviço de emergência para a maioria da Europa e 911 como a cadeia de caracteres de discagem de emergência. Um Teams da Europa que está visitando pode não saber que o 911 é o número de emergência nos Estados Unidos e, quando ele disca 112, a chamada é feita para 911. Para definir várias máscaras de discagem, separe cada valor por ponto e vírgula. Por exemplo, 112;212.
    3. **Registro de uso PSTN**: Selecione o registro de uso PSTN (Rede Telefônica Pública Comutado). O registro de uso PSTN é usado para determinar qual rota é usada para rotear chamadas de emergência de usuários autorizados a usá-las. A rota associada a esse uso deve apontar para um tronco SIP (Session Initiation Protocol) dedicado a chamadas de emergência ou a um gateway ELIN (Número de Identificação de Local de Emergência) que encaminha chamadas de emergência para o PSAP (Ponto de Atendimento de Segurança Pública) mais próximo.

    > [!NOTE]
    > As cadeias de caracteres de discagem e as máscaras de discagem devem ser exclusivas em uma política. Isso significa que, para uma política, você pode definir vários números de emergência e definir várias máscaras de discagem para uma cadeia de caracteres de discagem, mas cada cadeia de caracteres de discagem e máscara de discagem só devem ser usadas uma vez.

6. Clique em **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Editar uma política de roteamento de chamadas de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode editar a política global ou quaisquer políticas personalizadas que você criar.

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Políticas de Emergência de Voz e clique na guia Políticas de  >   **roteamento de** chamadas.
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. Faça as alterações que você deseja e clique em **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Atribuir uma política de roteamento de chamadas de emergência personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte também [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Atribuir uma política de roteamento de chamadas de emergência personalizada a um site de rede

Use o cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de roteamento de chamadas de emergência a um site de rede.

Este exemplo mostra como atribuir uma política chamada Política de Roteamento de Chamadas de Emergência 1 ao site Site1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de chamada de emergência em Teams](manage-emergency-calling-policies.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)