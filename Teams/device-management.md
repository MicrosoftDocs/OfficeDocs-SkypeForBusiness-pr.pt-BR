---
title: Gerenciar seus dispositivos no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Saiba como gerenciar dispositivos usados com o Microsoft Teams em sua organização.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06b85012adbf0967889e74fb5765b02c9b2ea18f
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "39211925"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gerenciar seus dispositivos no Microsoft Teams

::: zone target="docs"
Como administrador, você gerencia todos os dispositivos usados com o Microsoft Teams em sua organização usando o centro de administração do Microsoft Teams. Você pode exibir e gerenciar o inventário de dispositivos da sua organização e executar tarefas como atualizar, reiniciar e monitorar o diagnóstico de dispositivos. Você também pode criar e atribuir perfis de configuração a um dispositivo ou grupos de dispositivos. 

## <a name="what-devices-can-you-manage"></a>Quais dispositivos você pode gerenciar?
Os dispositivos devem ser certificados para equipes e registrados no Microsoft Teams. Um dispositivo é registrado automaticamente na primeira vez que o usuário entra no Microsoft Teams no dispositivo. Para obter uma lista de dispositivos certificados que podem ser gerenciados, consulte [telefones em conferência](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16) e [telefones de mesa](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34).

> [!NOTE]
> Se você tiver o Microsoft Intune, os dispositivos são registrados automaticamente no Intune. Depois que um dispositivo é registrado, a conformidade do dispositivo é confirmada e as políticas de acesso condicional são aplicadas ao dispositivo. 

## <a name="manage-devices-in-teams"></a>Gerenciar dispositivos no Microsoft Teams

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

1. No painel de navegação esquerdo, vá para **dispositivos** > **gerenciar dispositivos**.
2. Selecione **todos os dispositivos**.  

::: zone-end

 A partir daqui, você pode exibir e gerenciar todos os dispositivos registrados no Microsoft Teams em sua organização. As informações que você verá para cada dispositivo inclui o nome do dispositivo, o fabricante, o modelo, o usuário, o status, a ação, o último visto e o histórico. Você pode personalizar o modo de exibição para mostrar as informações que atendem às suas necessidades.

 Veja alguns exemplos de como você pode gerenciar os dispositivos da equipe em sua organização.  
    
|Para fazer isso...  |Fazer isso |
|---------|---------|
|Alterar as informações do dispositivo   | Selecione um dispositivo > **Editar**. Você pode editar detalhes, como o nome do dispositivo, as informações do usuário, a marca do ativo e adicionar anotações.     |
|Gerenciar atualizações de software   |Selecione um dispositivo > **atualização**. Você pode exibir a lista de atualizações de software e firmware disponíveis para o dispositivo e escolher as atualizações a serem instaladas.    |
|Reiniciar um dispositivo   |Selecione um dispositivo > **reiniciar**.          |
|Exibir o histórico de dispositivos  | Selecione um > **histórico**de dispositivos. Você pode exibir o histórico de atualizações do dispositivo.     |
|Exibir diagnósticos  | Selecione um dispositivo > **diagnóstico**.        |

## <a name="use-configuration-profiles-in-teams"></a>Usar perfis de configuração no Teams

Use perfis de configuração para gerenciar as configurações e os recursos dos dispositivos de equipe em sua organização. Você pode criar ou carregar perfis de configuração para incluir configurações e recursos que você deseja habilitar ou desabilitar e atribuir um perfil a um dispositivo ou grupos de dispositivos. 

### <a name="create-a-configuration-profile"></a>Criar um perfil de configuração

::: zone target="docs"

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) Usar o centro de administração do Microsoft Teams & o Skype for Business

1. No painel de navegação esquerdo, vá para **dispositivos** > **gerenciar dispositivos**.

::: zone-end

2. Selecione **perfis de configuração**e, em seguida, selecione **novo perfil de configuração**.
3. Digite um nome para o perfil e, se desejar, adicione uma descrição amigável.
4. Especifique as configurações desejadas para o perfil e clique em **salvar**.

### <a name="assign-a-configuration-profile"></a>Atribuir um perfil de configuração

::: zone target="docs"

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) Usar o centro de administração do Microsoft Teams & o Skype for Business

1. No painel de navegação esquerdo, vá para **dispositivos** > **gerenciar dispositivos**.

::: zone-end

2. Selecione **perfil de configuração**e, em **atribuída a** , no perfil que você deseja atribuir, clique no link.  
3. No painel **atribuir dispositivos a um perfil de configuração** , procure e selecione os dispositivos que você deseja atribuir.
4. Clique em **Salvar**.
