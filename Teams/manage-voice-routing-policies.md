---
title: Gerenciar políticas de roteamento de voz no Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802551"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Gerenciar políticas de roteamento de voz no Microsoft Teams

Se você implantou o Roteamento Direto do Sistema Telefônico em sua organização, use as políticas de roteamento de voz para permitir que os usuários do Teams e do Skype for Business Online recebam e façam chamadas telefônicas para a PSTN (Rede Telefônica Pública Comutado) usando sua infraestrutura de telefonia local. [](direct-routing-landing-page.md)

Uma política de roteamento de voz é um contêiner para registros de uso de PSTN. Crie e gerencie políticas de roteamento de voz indo para políticas de roteamento de **Voz** no Centro de administração do Microsoft Teams ou  >   usando o Windows PowerShell.

Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.

É importante saber que a atribuição de uma política de roteamento de voz a um usuário não permite que ele faça chamadas PSTN no Teams. Você também precisará habilitar o usuário para Roteamento Direto do Sistema de Telefonia e concluir outras etapas de configuração. Para saber mais, consulte [Configurar Roteamento Direto.](direct-routing-configure.md)

## <a name="create-a-custom-voice-routing-policy"></a>Criar uma política de roteamento de voz personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas de roteamento do **Voice** Voice e  >  clique em **Adicionar.**<br>
    ![Captura de tela da página Adicionar política de roteamento de voz no Centro de administração do Microsoft Teams ](media/manage-voice-routing-policies.png) 
2. Insira um nome e uma descrição para a política.
3. Em **registros de uso PSTN,** clique em Adicionar uso de **PSTN** e selecione os registros que você deseja adicionar. Se você precisar criar um novo registro de uso de PSTN, clique em **Adicionar.**
4. Se você adicionou vários registros de uso de PSTN, organize-os na ordem que você deseja.
5. Quando terminar, clique em **Aplicar.**
6. Clique em **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-voice-routing-policy"></a>Editar uma política de roteamento de voz

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Você pode editar a política global ou quaisquer políticas personalizadas que criar.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas de roteamento **do Voice**  >  **Voice.**
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. Clique **em Adicionar/remover registros de uso de PSTN,** faça as alterações que você deseja e clique em **Salvar.**

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Atribuir uma política de roteamento de voz personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Confira também [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Configurar o roteamento de voz para Roteamento Direto](direct-routing-voice-routing.md)

[Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)

[Atribua políticas a seus usuários no Teams](assign-policies.md)
