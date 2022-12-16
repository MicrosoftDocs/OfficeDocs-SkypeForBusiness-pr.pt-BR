---
title: Gerenciar políticas de identificação de chamadas no Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de ID do chamador no Microsoft o Teams para alterar ou bloquear a ID de chamador de usuários do Teams em sua organização.
ms.openlocfilehash: 4abeccb7a536885707ec43874d00f2a05a14551d
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414699"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gerenciar políticas de identificação de chamadas no Microsoft Teams

Por padrão, quando um usuário do Teams faz uma chamada para um telefone PSTN, o número de telefone do usuário do Teams fica visível. Da mesma forma, quando um chamador PSTN faz uma chamada para um usuário do Teams, o número de telefone do chamador PSTN fica visível.

Como administrador, você pode usar políticas de ID do chamador para alterar ou bloquear a ID do chamador (também conhecida como ID da linha de chamada). Você pode usar políticas de ID do chamador para exibir um número de telefone alternativo para usuários do Teams em sua organização, bloquear o número de telefone de saída, bloquear a exibição de um número de entrada ou definir o CNAM (Nome da Parte de Chamada). Por exemplo, quando um usuário faz uma chamada, você pode alterar a ID do chamador para exibir o número de telefone principal da sua organização e o nome da empresa em vez do número de telefone do usuário.

Você gerencia as políticas de ID do chamador acessando **políticas de ID do Chamador** de **Voz** >  no centro de administração do Microsoft Teams. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada.

## <a name="create-a-custom-caller-id-policy"></a>Criar uma política de ID de chamador personalizada

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **políticas de ID do Chamador de** **Voz** > .
2. Clique em **Adicionar**. <br>
![Captura de tela da nova página de política de ID do chamador no centro de administração.](media/caller-id-policies-add-policy.png)
3. Insira um nome e uma descrição para a política.
4. A partir daqui, escolha as configurações desejadas:

    - **Bloquear a ID do chamador de entrada**: ative essa configuração para impedir que a ID do chamador de chamadas recebidas seja exibida.
    - **Substitua a política de ID do chamador**: ative essa configuração para permitir que os usuários substituam as configurações na política em relação à exibição de seu número para callees ou não. Isso significa que os usuários podem escolher se devem exibir a ID do chamador. Para obter mais informações, consulte [Controle de usuário final da ID do chamador de saída](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).
    - **Substitua a ID do chamador** por: Defina a ID do chamador a ser exibida para os usuários selecionando um dos seguintes:

        - **Número do usuário**: exibe o número do usuário. 
        - **Número de serviço**: permite definir um número de telefone de serviço a ser exibido como a ID do chamador.
        - **Anônimo**: exibe a ID do chamador como Anônimo.

    - **Substitua a ID do chamador por esse número de serviço**: escolha um número de serviço para substituir a ID do chamador dos usuários. Essa opção estará disponível se você selecionou **o número de serviço** em **Substituir a ID do chamador**.

5. Clique em **Salvar**.

## <a name="edit-a-caller-id-policy"></a>Editar uma política de ID do chamador

Você pode editar a política global ou quaisquer políticas personalizadas que você criar. 

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **políticas de ID do Chamador de** **Voz** > .
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. Altere as configurações desejadas e clique em **Salvar**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Atribuir uma política de ID de chamador personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Tópicos relacionados

[Entidade New-CsCallingLineId](/powershell/module/skype/new-cscallinglineidentity)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity)

[Atribua políticas a seus usuários no Teams](policy-assignment-overview.md)
