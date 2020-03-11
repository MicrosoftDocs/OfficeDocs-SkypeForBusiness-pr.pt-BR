---
title: Gerenciar seus dispositivos no Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Saiba como gerenciar dispositivos usados com o Microsoft Teams em sua organização.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587313"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gerenciar seus dispositivos no Microsoft Teams

Como administrador, você pode gerenciar os dispositivos usados com o Microsoft Teams em sua organização usando o centro de administração do Microsoft Teams. Você pode exibir e gerenciar o inventário de dispositivos da sua organização e executar tarefas como atualizar, reiniciar e monitorar o diagnóstico de dispositivos. Você também pode criar e atribuir perfis de configuração a um dispositivo ou grupos de dispositivos. 

## <a name="what-devices-can-you-manage"></a>Quais dispositivos você pode gerenciar?
Você pode gerenciar qualquer dispositivo certificado e inscrito no Microsoft Teams. Um dispositivo é registrado automaticamente na primeira vez que o usuário entra no Microsoft Teams no dispositivo. Para obter uma lista de dispositivos certificados que podem ser gerenciados, consulte:

- [Telefones de conferência](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [Telefones de mesa](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- Barras de colaboração

Os dispositivos são gerenciados no [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com) em **dispositivos** na navegação à esquerda.

> [!NOTE]
> Se você tiver o Microsoft Intune, os dispositivos são registrados automaticamente no Intune. Depois que um dispositivo é registrado, a conformidade do dispositivo é confirmada e as políticas de acesso condicional são aplicadas ao dispositivo.

## <a name="manage-phones-and-collaboration-bars-in-teams"></a>Gerenciar telefones e barras de colaboração no Teams

Embora os telefones e as barras de colaboração sejam gerenciados da mesma maneira no centro de administração do Microsoft Teams, eles têm suas próprias seções na navegação à esquerda em **dispositivos**. Isso permite que você gerencie cada tipo de dispositivo separadamente.

Aqui, você pode exibir e gerenciar telefones e barras de colaboração registrados no Microsoft Teams em sua organização. As informações que você verá para cada dispositivo inclui o nome do dispositivo, o fabricante, o modelo, o usuário, o status, a ação, o último visto e o histórico. Você pode personalizar o modo de exibição para mostrar as informações que atendem às suas necessidades.

Veja alguns exemplos de como você pode gerenciar os dispositivos da equipe em sua organização.  
    
|Para fazer isso...  |Fazer isso |
|---------|---------|
|Alterar as informações do dispositivo   | Selecione um dispositivo > **Editar**. Você pode editar detalhes, como o nome do dispositivo, a marca de ativos e adicionar anotações.     |
|Gerenciar atualizações de software   |Selecione um dispositivo > **atualização**. Você pode exibir a lista de atualizações de software e firmware disponíveis para o dispositivo e escolher as atualizações a serem instaladas.    |
|Reiniciar um dispositivo   |Selecione um dispositivo > **reiniciar**.          |
|Exibir o histórico de dispositivos  | Selecione um > **histórico**de dispositivos. Você pode exibir o histórico de atualizações do dispositivo.     |
|Exibir diagnósticos  | Selecione um dispositivo > **diagnóstico**.        |

## <a name="use-configuration-profiles-in-teams"></a>Usar perfis de configuração no Teams

Use perfis de configuração para gerenciar as configurações e os recursos dos dispositivos de equipe em sua organização. Você pode criar ou carregar perfis de configuração para incluir configurações e recursos que você deseja habilitar ou desabilitar e atribuir um perfil a um dispositivo ou grupos de dispositivos. 

### <a name="create-a-configuration-profile"></a>Criar um perfil de configuração

1. No painel de navegação esquerdo, vá para**perfis de configuração**de **dispositivos** > .
2. Clique em **Adicionar**.
3. Digite um nome para o perfil e, se desejar, adicione uma descrição amigável.
4. Especifique as configurações desejadas para o perfil e clique em **salvar**.

### <a name="assign-a-configuration-profile"></a>Atribuir um perfil de configuração

1. No painel de navegação esquerdo, vá para**perfis de configuração**de **dispositivos** > .
2. Selecione o **perfil de configuração** que você deseja atribuir e clique em **atribuir a dispositivo**.  
3. No painel **atribuir dispositivos a um perfil de configuração** , procure e selecione os dispositivos que você deseja atribuir.
4. Clique em **Salvar**.
