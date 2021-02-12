---
title: Gerenciar políticas de ID de chamada no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Saiba como usar e gerenciar políticas de ID de chamador no Microsoft Teams para alterar ou bloquear a ID de chamador dos usuários do Teams em sua organização.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255524"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gerenciar políticas de ID de chamada no Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Como administrador, você pode usar políticas de ID de chamada no Microsoft Teams para alterar ou bloquear a ID de chamador (também conhecida como ID de linha de chamada). Por padrão, o número de telefone dos usuários do Teams pode ser visto quando eles fazem uma chamada para um telefone PSTN e o número de telefone de chamadores PSTN pode ser visto quando eles ligarem para um usuário do Teams. Você pode usar políticas de ID de chamadas para exibir um número de telefone alternativo para usuários do Teams em sua organização ou impedir que um número de entrada seja exibido.

Por exemplo, quando os usuários fazem uma chamada, você pode alterar a ID de chamadas para exibir o número de telefone principal da sua organização em vez dos números de telefone dos usuários.

Você gerencia políticas de ID de chamadas indo **para** políticas de ID do  >  **Chamador de** Voz no Centro de administração do Microsoft Teams. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada.

## <a name="create-a-custom-caller-id-policy"></a>Criar uma política de ID de chamada personalizada

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **políticas** de  >  **ID do Chamador de Voz.**
2. Clique em **Adicionar**. <br>
![Captura de tela da nova página de política de ID de chamada no centro de administração](media/caller-id-policies-add-policy.png)
3. Insira um nome e uma descrição para a política.
4. A partir daqui, escolha as configurações que você deseja:

    - **Bloquear a ID de chamadas** de entrada: a ligue essa configuração para impedir que a ID de chamadas de entrada seja exibida.
    - **Substituir a política de ID** de chamada: ativação dessa configuração para permitir que os usuários substituam as configurações na política sobre como exibir seu número para os chamador ou não. Isso significa que os usuários podem optar por exibir a ID de chamada. Para saber mais, confira [o controle do usuário final da ID de chamada de saída.](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)
    - **Substitua a ID de chamador por:** Deverão exibir a ID de chamada para os usuários selecionando uma das seguintes:

        - **Número do usuário:** exibe o número do usuário. 
        - **Número de** serviço: permite definir um número de telefone de serviço para ser exibido como a ID do chamador.
        - **Anônimo:** exibe a ID de chamada como Anônimo.

    - **Substitua a ID de chamada por este** número de serviço: escolha um número de serviço para substituir a ID de chamada dos usuários. Essa opção estará disponível se você tiver selecionado **o** número do serviço em Substituir **a ID do chamador por**.

5. Clique em **Salvar**.

## <a name="edit-a-caller-id-policy"></a>Editar uma política de ID de chamada

Você pode editar a política global ou quaisquer políticas personalizadas que criar. 

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **políticas** de  >  **ID do Chamador de Voz.**
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. Altere as configurações que você deseja e clique em **Salvar.**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Atribuir uma política de ID de chamada personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Tópicos relacionados

[New-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Atribua políticas a seus usuários no Teams](assign-policies.md)
