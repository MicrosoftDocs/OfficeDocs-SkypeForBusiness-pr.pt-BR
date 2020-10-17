---
title: Gerenciar políticas de roteamento de chamada
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de roteamento de chamadas de emergência no Microsoft Teams para configurar números de emergência e especificar como as chamadas de emergência são roteadas.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 2ec28dfa2e3e3c685ea70d882c4dd6d4d342ec7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532748"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Gerenciar políticas de roteamento de chamadas de emergência no Microsoft Teams

Se você implantou o [Roteamento direto do sistema telefônico](direct-routing-landing-page.md) em sua organização, poderá usar as políticas de roteamento de chamadas de emergência no Microsoft Teams para configurar os números de emergência e especificar como as chamadas de emergência serão roteadas. Uma política de roteamento de chamadas de emergência determina se os serviços de emergência avançados estão habilitados para usuários que receberam a política, os números usados para chamar serviços de emergência (por exemplo, 911 nos Estados Unidos) e como as chamadas para serviços de emergência são roteadas.

Para gerenciar as políticas de roteamento de chamadas de **Voice**emergência,  >  acesse**as políticas de emergência** de voz no centro de administração do Microsoft Teams ou usando o Windows PowerShell. As políticas podem ser atribuídas a usuários e [sites de rede](cloud-voice-network-settings.md).

Para os usuários, você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la. Para sites de rede, você cria e atribui políticas personalizadas.

Se você tiver atribuído uma política de roteamento de chamadas de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Criar uma política de roteamento de chamada de emergência personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  **Emergency policies**e clique na guia **políticas de roteamento de chamadas** .
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.
4. Para habilitar a chamada de emergência dinâmica, ative as **chamadas de emergência dinâmicas**. Quando a chamada de emergência dinâmica está habilitada, o Teams recupera informações de política e local do serviço e inclui essas informações como parte da chamada de emergência.
5. Defina um ou mais números de emergência. Para fazer isso, em **números de emergência**, clique em **Adicionar**e, em seguida, faça o seguinte:
    1. **Cadeia de discagem de emergência**: digite a cadeia de caracteres de discagem de emergência. Esta cadeia de caracteres de discagem indica que uma chamada é uma chamada de emergência.
        > [!NOTE]
        > Para roteamento direto, estamos migrando de clientes do teams que enviam chamadas de emergência com "+" na frente da cadeia de discagem de emergência. Até que a transição seja concluída, o padrão de rota de voz para corresponder a uma cadeia de discagem de emergência deve garantir que seja feita uma correspondência para cadeias de caracteres que tenham e não tenham um "+" anterior, como 911 e + 911. Por exemplo, ^ \\ +? 911 ou. *.
    2. **Máscara de discagem de emergência**: para cada número de emergência, você pode especificar zero ou mais máscaras de discagem de emergência. Uma máscara de discagem é o número que você deseja traduzir para o valor da cadeia de caracteres de discagem de emergência. Isso permite que números de emergência alternativos sejam discados e ainda que a chamada atinja serviços de emergência. <br>Por exemplo, você adiciona 112 como a máscara de discagem de emergência, que é o número do serviço de emergência para a maioria da Europa e 911 como a cadeia de discagem de emergência. Um usuário do teams da Europa que está visitando talvez não saiba que 911 é o número de emergência nos Estados Unidos e, quando discam o 112, a chamada é feita ao 911. Para definir várias máscaras de discagem, separe cada valor por um ponto-e-vírgula. Por exemplo, 112; 212.
    3. **Registro de uso de PSTN**: selecione o registro de uso da rede de telefonia pública comutada (PSTN). O registro de uso de PSTN é usado para determinar qual rota é usada para direcionar chamadas de emergência de usuários que estão autorizados a usá-los. O roteiro associado a esse uso deve apontar para um tronco SIP (Session Initiation Protocol) dedicado a chamadas de emergência ou a um gateway de número de identificação de local de emergência (ELIN) que roteia chamadas de emergência para o ponto de resposta de segurança pública mais próximo (PSAP).

    > [!NOTE]
    > As seqüências de discagem e as máscaras de discagem devem ser exclusivas dentro de uma política. Isso significa que, para uma política, você pode definir vários números de emergência e pode definir várias máscaras de discagem para uma cadeia de caracteres de discagem, mas cada cadeia de discagem e máscara de discagem devem ser usadas apenas uma vez.

6. Clique em **Salvar**.

### <a name="using-powershell"></a>Usando o PowerShell

Veja [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Editar uma política de roteamento de chamadas de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode editar a política global ou qualquer política personalizada criada.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  **Emergency policies**e clique na guia **políticas de roteamento de chamadas** .
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Faça as alterações desejadas e clique em **salvar**.

### <a name="using-powershell"></a>Usando o PowerShell

Consulte [set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Atribuir uma política de roteamento de chamada de emergência personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte também [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Atribuir uma política de roteamento de chamada de emergência personalizada a um site de rede

Use o cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de roteamento de chamadas de emergência a um site de rede.

Este exemplo mostra como atribuir uma política denominada política de roteamento de chamadas de emergência 1 para o site do site1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de chamadas de emergência no Teams](manage-emergency-calling-policies.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Atribuir políticas a seus usuários no Teams](assign-policies.md)
