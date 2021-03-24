---
title: Estacionamento e recuperação de chamadas no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Saiba como usar o estacionamento de chamada e recuperar para colocar uma chamada em espera no Microsoft Teams.
ms.openlocfilehash: efc36a2bc90b64abf2e886c5e768a26704bd6550
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102797"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamento e recuperação de chamadas no Microsoft Teams

Estacionamento de chamada e recuperação é um recurso que permite que um usuário coloque uma chamada em espera. Quando uma chamada é estacionada, o serviço gera um código exclusivo para recuperação de chamada. O usuário que estacionou a chamada ou outra pessoa pode usar esse código com um aplicativo ou dispositivo com suporte para recuperar a chamada. (Consulte [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)

Alguns dos cenários comuns para o uso do estacionamento de chamada são:

- Uma recepcionista estaciona uma chamada para alguém que trabalha em uma fábrica. Em seguida, a recepcionista anuncia a chamada e o número de código no sistema de endereços público. O usuário para quem a chamada é pode, em seguida, pegar um telefone do Teams no piso da fábrica e inserir o código para recuperar a chamada.
- Um usuário estaciona uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia. Em seguida, o usuário pode inserir o código para recuperar a chamada de um telefone de mesa do Teams.
- Um representante de suporte estaciona uma chamada do cliente e envia um comunicado em um canal do Teams para que um especialista recupere a chamada e ajude o cliente. Um especialista inssi o código nos clientes do Teams para recuperar a chamada

Para estacionar e recuperar chamadas, um usuário deve ser um usuário Enterprise Voice e deve ser incluído em uma política de estacionamento de chamadas.

> [!NOTE]
> Estacionamento de chamadas e recuperação só está disponível no modo de implantação somente do [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e não tem suporte em telefones IP do Skype for Business.

## <a name="configure-call-park-and-retrieve"></a>Configurar estacionamento de chamada e recuperar

Você deve ser um administrador do Teams para configurar o estacionamento de chamada e recuperar. Ele está desabilitado por padrão. Você pode habilita-lo para usuários e criar grupos de usuários usando a política de estacionamento de chamada. Quando você aplica a mesma política a um conjunto de usuários, eles podem estacionar e recuperar chamadas entre si.

Para habilitar uma política de estacionamento de chamada

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Políticas**  >  **de estacionamento de Chamada de Voz.**
2. Na guia **Gerenciar políticas,** clique em **Adicionar**.
3. Dê um nome à política e **alterne Permitir** estacionamento de chamada para **On**.

    ![Captura de tela das configurações de política de estacionamento de chamada](media/call-park-add-policy.png)

4. Selecione **Salvar**.

Você pode editar a política selecionando-a na lista e clicando em **Editar**.

Para que a política funcione, ela deve ser atribuída aos usuários. Você pode [atribuir a política aos usuários individualmente](assign-policies.md) ou atribuí-la a um grupo.

Para atribuir uma política de parte de chamada a um grupo

1. Na página **Políticas de estacionamento de** chamada, na guia Atribuição de **política** de grupo, clique em **Adicionar grupo**.
2. Pesquise o grupo que você deseja usar e clique em **Adicionar**.
3. Escolha uma classificação em comparação com outras atribuições de grupo.
4. Em **Selecionar uma política,** escolha a política à qual você deseja atribuir esse grupo.

    ![imagem de políticas de estacionamento](media/call-park-assign-policy-to-group.png)

5. Selecione **Aplicar**.

## <a name="related-topics"></a>Tópicos relacionados

[Estacionar uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Atribua políticas a seus usuários no Teams](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)