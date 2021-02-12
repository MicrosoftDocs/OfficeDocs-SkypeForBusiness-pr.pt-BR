---
title: Gerenciar políticas de roteamento de chamada
author: cichur
ms.author: v-cichur
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
description: Saiba como usar e gerenciar políticas de roteamento de chamadas de emergência no Microsoft Teams para configurar números de emergência e especificar como as chamadas de emergência são roteada.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: f2e7ce7ee2557745f3819efc84dada77b4a70635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804671"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Gerenciar políticas de roteamento de chamadas de emergência no Microsoft Teams

Se você implantou o Roteamento Direto do Sistema telefônico em sua organização, pode usar políticas de roteamento de chamadas de emergência no Microsoft Teams para configurar números de emergência e especificar como as chamadas de emergência são roteadas. [](direct-routing-landing-page.md) Uma política de roteamento de chamadas de emergência determina se os serviços de emergência aprimorados estão habilitados para usuários que têm a política atribuída, os números usados para ligar para serviços de emergência (por exemplo, 911 nos Estados Unidos) e como as chamadas para serviços de emergência são roteadas.

Você gerencia políticas de roteamento de chamadas de emergência indo para **políticas** de Emergência de Voz no Centro de administração do  >   Microsoft Teams ou usando o Windows PowerShell. As políticas podem ser atribuídas a usuários e [sites de rede.](cloud-voice-network-settings.md)

Para os usuários, você pode usar a política global (padrão de toda a organização) ou criar e atribuir políticas personalizadas. Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la. Para sites de rede, você cria e atribui políticas personalizadas.

Se você atribuiu uma política de roteamento de chamada de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política atribuída ao site de rede substituirá a política atribuída ao usuário.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Criar uma política de roteamento de chamadas de emergência personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas de Emergência de Voz e clique na  >  guia Políticas **de roteamento de** chamadas.
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.
4. Para habilitar uma chamada de emergência dinâmica, ative **as chamada de emergência dinâmicas.** Quando a chamada de emergência dinâmica está habilitada, o Teams recupera informações de localização e política do serviço e inclui essas informações como parte da chamada de emergência.
5. Defina um ou mais números de emergência. Para fazer isso, em **Números de emergência,** clique em **Adicionar** e faça o seguinte:
    1. **Cadeia de discagem de emergência:** insira a cadeia de caracteres de discagem de emergência. Essa cadeia de caracteres de discagem indica que uma chamada é uma chamada de emergência.
        > [!NOTE]
        > Para Roteamento Direto, estamos nos afastando dos clientes do Teams que enviam chamadas de emergência com um "+" na frente da cadeia de discagem de emergência. Até que a transição seja concluída, o padrão de rota de voz para corresponder a uma cadeia de discagem de emergência deve garantir que uma combinação seja feita para cadeias de caracteres que têm e não têm um "+", como 911 e +911. Por exemplo, ^ \\ +?911 ou .*.
    2. **Máscara de discagem de** emergência: para cada número de emergência, você pode especificar zero ou mais máscaras de discagem de emergência. Uma máscara de discagem é o número que você deseja traduzir para o valor da cadeia de discagem de emergência. Isso permite que números de emergência alternativos sejam discados e ainda que a chamada chegue aos serviços de emergência. <br>Por exemplo, você adiciona 112 como a máscara de discagem de emergência, que é o número de serviço de emergência da maioria da Europa, e 911 como a cadeia de discagem de emergência. Um usuário do Teams da Europa que está visitando pode não saber que 911 é o número de emergência nos Estados Unidos e, quando eles discam para 112, a chamada é feita para 911. Para definir várias máscaras de discagem, separe cada valor por ponto e vírgula. Por exemplo, 112;212.
    3. **Registro de uso PSTN:** selecione o registro de uso de PSTN (Rede Telefônica Pública Comutado). O registro de uso PSTN é usado para determinar qual rota é usada para encaminhar chamadas de emergência de usuários autorizados a usá-las. A rota associada a esse uso deve apontar para um tronco sip dedicado a chamadas de emergência ou a um gateway ELIN (Número de Identificação de Localização de Emergência) que encaminha chamadas de emergência para o PSAP (Ponto de Atendimento de Segurança Pública) mais próximo.

    > [!NOTE]
    > As cadeias de caracteres de discagem e as máscaras de discagem devem ser exclusivas em uma política. Isso significa que, para uma política, você pode definir vários números de emergência e definir várias máscaras de discagem para uma cadeia de caracteres de discagem, mas cada cadeia de discagem e máscara de discagem só devem ser usadas uma vez.

6. Clique em **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)

## <a name="edit-an-emergency-call-routing-policy"></a>Editar uma política de roteamento de chamadas de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode editar a política global ou quaisquer políticas personalizadas que criar.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas de Emergência de Voz e clique na  >  guia Políticas **de roteamento de** chamadas.
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. Faça as alterações que você deseja e clique em **Salvar.**

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Atribuir uma política de roteamento de chamada de emergência personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Confira também [Grant-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Atribuir uma política de roteamento de chamada de emergência personalizada a um site de rede

Use o cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de roteamento de chamadas de emergência a um site de rede.

Este exemplo mostra como atribuir uma política chamada Política de Roteamento de Chamada de Emergência 1 ao site1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de chamada de emergência no Teams](manage-emergency-calling-policies.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Atribua políticas a seus usuários no Teams](assign-policies.md)
