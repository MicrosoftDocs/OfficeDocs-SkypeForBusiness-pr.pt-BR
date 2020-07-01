---
title: Gerenciar políticas de identificação de chamadas no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de identificação de chamadas no Microsoft Teams para alterar ou bloquear a identificação de chamadas de usuários do teams em sua organização.
ms.openlocfilehash: 41466640f33769a64ce14d5d3dc47959c876a5bc
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938460"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gerenciar políticas de identificação de chamadas no Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Como administrador, você pode usar as políticas de identificação de chamada no Microsoft Teams para alterar ou bloquear a identificação de chamadas (também conhecida como identificação da linha de chamada). Por padrão, o número de telefone dos usuários do teams pode ser visto ao fazer uma chamada para um telefone PSTN, e o número de telefone PSTN pode ser visto quando ele chama um usuário do teams. Você pode usar as políticas de identificação de chamadas para exibir um número de telefone alternativo para usuários do teams em sua organização ou impedir que um número recebido seja exibido.

Por exemplo, quando os usuários fazem uma chamada, você pode alterar a identificação de chamadas para exibir o número de telefone principal da sua organização, em vez de números de telefone dos usuários.

Você gerencia as políticas de identificação de chamadas **Voice**indo para  >  **políticas de identificação de chamadas** de voz no centro de administração do Microsoft Teams. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada.

## <a name="create-a-custom-caller-id-policy"></a>Criar uma política de identificação de chamadas personalizada

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de identificação de chamadas**de voz.
2. Clique em **Adicionar**. <br>
![Captura de tela da página nova política de identificação de chamadas no centro de administração](media/caller-id-policies-add-policy.png)
3. Insira um nome e uma descrição para a política.
4. Aqui, escolha as configurações desejadas:

    - **Bloquear a identificação**de chamadas de entrada: Ative essa configuração para impedir que a identificação de chamadas de chamadas de entrada seja exibida.
    - **Substituir a política de identificação de chamadas**: Ative essa configuração para permitir que os usuários substituam as configurações na política para exibir seu número para chamar ou não. Isso significa que os usuários podem escolher se desejam exibir a identificação de chamadas. Para obter mais informações, consulte [controle do usuário final da identificação de chamadas de saída](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).
    - **Substituir a identificação de chamadas**por: definir a identificação de chamadas a ser exibida para os usuários selecionando uma das seguintes opções:

        - **Número do usuário**: exibe o número do usuário. 
        - **Número do serviço**: permite que você defina um número de telefone de serviço para ser exibido como a identificação de chamadas.
        - **Anônimo**: EXIBE a identificação de chamadas como anônima.

    - **Substituir a identificação de chamadas por este número de serviço**: escolha um número de serviço para substituir a identificação de chamadas dos usuários. Essa opção estará disponível se você tiver selecionado **número de serviço** em **substituir a identificação de chamadas por**.

5. Clique em **Salvar**.

## <a name="edit-a-caller-id-policy"></a>Editar uma política de identificação de chamadas

Você pode editar a política global ou qualquer política personalizada criada. 

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de identificação de chamadas**de voz.
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Altere as configurações desejadas e clique em **salvar**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Atribuir uma política de identificação de chamadas personalizada a usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Tópicos relacionados

[New-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Atribuir políticas a seus usuários no Teams](assign-policies.md)
