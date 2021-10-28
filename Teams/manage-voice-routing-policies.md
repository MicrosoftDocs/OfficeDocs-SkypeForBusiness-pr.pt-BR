---
title: Gerenciar políticas de roteamento de voz para Roteamento Direto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como criar e gerenciar políticas de roteamento de voz Microsoft Teams.
ms.openlocfilehash: d9bd26f2322d9b99b0e2ff8e8ba01f0569abc24e
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605573"
---
# <a name="manage-voice-routing-policies-for-direct-routing"></a>Gerenciar políticas de roteamento de voz para Roteamento Direto

Se você tiver implantado Sistema de Telefonia Roteamento Direto em sua organização, use políticas de roteamento de voz para permitir que os usuários do Teams e do Skype for Business Online recebam e façam chamadas telefônicas para [a](direct-routing-landing-page.md) PSTN (Rede Telefônica Pública Comugada) usando sua infraestrutura de telefonia local.

Uma política de roteamento de voz é um contêiner para registros de uso PSTN. Você cria e gerencia políticas de roteamento de voz indo para políticas de roteamento do **Voice** Voice no centro de administração Microsoft Teams  >   ou usando Windows PowerShell.

Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.

É importante saber que atribuir uma política de roteamento de voz a um usuário não permite que ele faça chamadas PSTN em Teams. Você também precisará habilitar o usuário para Sistema de Telefonia Roteamento Direto e concluir outras etapas de configuração. Para saber mais, consulte [Configure Direct Routing](direct-routing-configure.md).

## <a name="create-a-custom-voice-routing-policy"></a>Criar uma política de roteamento de voz personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Políticas de roteamento **do Voice** Voice e clique  >  em **Adicionar**.<br>
    ![Captura de tela da página Adicionar política de roteamento de voz no centro Microsoft Teams administrador.](media/manage-voice-routing-policies.png) 
2. Insira um nome e uma descrição para a política.
3. Em **Registros de uso PSTN,** clique em Adicionar uso de **PSTN** e selecione os registros que você deseja adicionar. Se você precisar criar um novo registro de uso PSTN, clique em **Adicionar**.
4. Se você adicionou vários registros de uso de PSTN, organize-os na ordem que você deseja.
5. Quando terminar, clique em **Aplicar**.
6. Clique em **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-voice-routing-policy"></a>Editar uma política de roteamento de voz

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode editar a política global ou quaisquer políticas personalizadas que você criar.

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Políticas de roteamento **do Voice**  >  **Voice**.
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. Clique **em Adicionar/remover registros de uso de PSTN,** fazer as alterações que você deseja e clique em **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Atribuir uma política de roteamento de voz personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte também [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Configurar roteamento de voz para Roteamento Direto](direct-routing-voice-routing.md)

[Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)

[Atribua políticas a seus usuários no Teams](policy-assignment-overview.md)