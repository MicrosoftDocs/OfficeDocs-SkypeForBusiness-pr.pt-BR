---
title: Gerenciar políticas de roteamento de voz no Microsoft Teams
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Saiba como criar e gerenciar políticas de roteamento de voz no Microsoft Teams.
ms.openlocfilehash: 2bef422f22dc212b2c615e2ca2ab98806b396e9f
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217652"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Gerenciar políticas de roteamento de voz no Microsoft Teams

Se você implantou o [Roteamento direto do sistema telefônico](direct-routing-landing-page.md) em sua organização, use as políticas de roteamento de voz para permitir que as equipes e usuários do Skype for Business online recebam e façam chamadas telefônicas para a rede telefônica comutada pública (PSTN) usando sua infraestrutura de telefonia local.

Uma política de roteamento de voz é um contêiner de registros de uso de PSTN. Crie e gerencie políticas de roteamento de voz indo **Voice**para  >  **políticas de roteamento de voz** de voz no centro de administração do Microsoft Teams ou usando o Windows PowerShell.

Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.

É importante saber que atribuir uma política de roteamento de voz a um usuário não permite que elas façam chamadas PSTN no Teams. Você também precisará habilitar o usuário para o roteamento direto do sistema telefônico e concluir outras etapas de configuração. Para saber mais, consulte [Configurar o roteamento direto](direct-routing-configure.md).

## <a name="create-a-custom-voice-routing-policy"></a>Criar uma política de roteamento de voz personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de roteamento de voz de **voz**  >  **Voice routing policies**e clique em **Adicionar**.<br>
    ![Captura de tela da página Adicionar política de roteamento de voz no centro de administração do Microsoft Teams ](media/manage-voice-routing-policies.png) 
2. Insira um nome e uma descrição para a política.
3. Em **registros de uso de PSTN**, clique em **Adicionar uso PSTN**e, em seguida, selecione os registros que você deseja adicionar. Se você precisar criar um novo registro de uso PSTN, clique em **Adicionar**.
4. Se você adicionou vários registros de uso de PSTN, organize-os na ordem desejada.
5. Quando tiver terminado, clique em **aplicar**.
6. Clique em **Salvar**.

### <a name="using-powershell"></a>Usando o PowerShell

Veja [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-voice-routing-policy"></a>Editar uma política de roteamento de voz

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode editar a política global ou qualquer política personalizada criada.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse políticas **de**  >  **Roteamento de voz**.
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Clique em **Adicionar/remover registros de uso PSTN**, faça as alterações desejadas e clique em **salvar**.

### <a name="using-powershell"></a>Usando o PowerShell

Consulte [set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Atribuir uma política de roteamento de voz personalizada a usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte também [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Configurar o roteamento de voz para roteamento direto](direct-routing-voice-routing.md)

[Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)

[Atribuir políticas a seus usuários no Teams](assign-policies.md)
