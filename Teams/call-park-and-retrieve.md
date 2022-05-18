---
title: Estacionamento e recuperação de chamadas no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Saiba mais sobre como usar o estacionamento de chamada e recuperar para colocar uma chamada em espera Microsoft Teams.
ms.openlocfilehash: a2a70515bbe263716fab8e2deded75e44d12fd6e
ms.sourcegitcommit: 3cb40132e36717dfbdc6dfe83e7ea319f3ec9347
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465442"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamento e recuperação de chamadas no Microsoft Teams

Estacionamento de chamada e recuperação é um recurso que permite que um usuário coloque uma chamada em espera. Quando uma chamada é estacionada, o serviço gera um código exclusivo para recuperação de chamadas. O usuário que estacionou a chamada ou outra pessoa pode usar esse código com um aplicativo ou dispositivo com suporte para recuperar a chamada. (Consulte [Park uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) para obter detalhes.)

Alguns dos cenários comuns para usar o estacionamento de chamada são:

- Uma recepção estaciona uma chamada para alguém que trabalha em uma fábrica. Em seguida, a recepção anuncia a chamada e o número de código no sistema de endereços públicos. O usuário para quem a chamada é, em seguida, pode pegar um telefone Teams no chão de fábrica e inserir o código para recuperar a chamada.
- Um usuário para uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia. Em seguida, o usuário pode inserir o código para recuperar a chamada de um Teams de mesa.
- Um representante de suporte para uma chamada de cliente e envia um comunicado em um canal Teams para um especialista recuperar a chamada e ajudar o cliente. Um especialista insere o código em Teams clientes para recuperar a chamada

Para estacionar e recuperar chamadas, um usuário deve ser Enterprise Voice usuário e deve ser incluído em uma política de estacionamento de chamada.

> [!NOTE]
> O estacionamento de chamada e a recuperação só estão disponíveis [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) modo de implantação e não têm suporte em telefones IP Skype for Business ip.

## <a name="configure-call-park-and-retrieve"></a>Configurar o estacionamento de chamada e recuperar

Você deve ser um administrador Teams para configurar o estacionamento de chamada e recuperá-lo. Ele está desabilitado por padrão. Você pode habilita-lo para usuários e criar grupos de usuários usando a política de estacionamento de chamada. Quando você aplica a mesma política a um conjunto de usuários, eles podem estacionar e recuperar chamadas entre si.

Por padrão, o intervalo de números de recebimento de chamadas é de 10 a 99. Você também pode criar seu próprio intervalo personalizado entre 10 e 9999. A primeira chamada estacionada será renderizada como um código de retirada do início do intervalo (por exemplo, 10). A próxima chamada estacionada será renderizada um código de retirada incrementado em 1; ou seja, 11 e assim por diante, até o final do intervalo ser renderizado como um código de retirada. Depois disso, os códigos de retirada renderizados começam novamente do início do intervalo novamente. 

Você pode especificar um tempo limite como o número de segundos de espera antes de tocar de volta quando a chamada estacionada não tiver sido atendia. O intervalo permitido é de 120 a 1800 segundos e o valor padrão é 300 segundos.

Para habilitar uma política de estacionamento de chamada:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para políticas **de estacionamento do VoiceCall** > .
2. Na guia **Gerenciar políticas** , clique em **Adicionar**.
3. Dê um nome à política e, em seguida, **alterne Permitir estacionamento de chamada** para **Ativado**.
4. Altere o intervalo e o tempo limite do parque conforme necessário.
5. Selecione **Salvar**.

Você pode editar a política selecionando-a na lista e clicando em **Editar**.

Para que a política funcione, ela deve ser atribuída aos usuários. Você pode [atribuir a política aos usuários individualmente ou](assign-policies-users-and-groups.md) atribuí-la a um grupo.

Para atribuir uma política de estacionamento de chamada a um grupo

1. Na página **Políticas de estacionamento de** chamada, na guia **Atribuição de política de** grupo, clique **em Adicionar grupo**.
2. Pesquise o grupo que você deseja usar e clique em **Adicionar**.
3. Escolha uma classificação em comparação com outras atribuições de grupo.
4. Em **Selecionar uma política**, escolha a política à qual você deseja atribuir esse grupo.

    ![imagem de políticas de parque.](media/call-park-assign-policy-to-group.png)

5. Selecione **Aplicar**.

## <a name="related-topics"></a>Tópicos relacionados

[Estacione uma chamada em Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
