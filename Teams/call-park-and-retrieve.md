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
description: Saiba mais sobre como usar o estacionamento de chamadas e recuperar para fazer uma chamada em espera no Microsoft Teams.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424573"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamento e recuperação de chamadas no Microsoft Teams

O estacionamento de chamadas e a recuperação são um recurso que permite que um usuário faça uma chamada em espera. Quando uma chamada está estacionada, o serviço gera um código exclusivo para recuperação de chamadas. O usuário que estacionau a chamada ou outra pessoa pode usar esse código com um aplicativo ou dispositivo com suporte para recuperar a chamada. (Veja Confira [o parque de uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) para obter detalhes.)

Alguns dos cenários comuns para usar o parque de chamadas são:

- Um recepcionista é um pedido de alguém trabalhando em uma fábrica. Em seguida, o recepcionista anuncia a chamada e o número do código pelo sistema de endereços público. O usuário para o qual a chamada é para pode pegar um telefone de equipe no chão de fábrica e digitar o código para recuperar a chamada.
- Um usuário representa uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia. Em seguida, o usuário pode inserir o código para recuperar a chamada em um telefone de mesa do teams.
- Um representante de suporte tem um representante do cliente e envia um comunicado em um canal de equipe para que um especialista para recuperar a chamada e ajudar o cliente. Um especialista insere o código em clientes do teams para recuperar a chamada

Para estacionar e recuperar chamadas, um usuário deve ser um usuário do Enterprise Voice e deve ser incluído em uma política de estacionamento de chamadas.

> [!NOTE]
> O estacionamento e a recuperação de chamadas só estão disponíveis no [modo de implantação do teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e não são compatíveis com telefones IP do Skype for Business.

## <a name="configure-call-park-and-retrieve"></a>Configurar o estacionamento e a recuperação de chamadas

Você deve ser um administrador do teams para configurar o estacionamento e a recuperação de chamadas. Ele é desabilitado por padrão. Você pode habilitá-lo para usuários e criar grupos de usuários usando a política de estacionamento de chamadas. Quando você aplica a mesma política a um conjunto de usuários, ele pode estacionar e recuperar chamadas entre si.

Para habilitar uma política de estacionamento de chamadas

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de estacionamento de chamada**de voz.
2. Na guia **gerenciar políticas** , clique em **Adicionar**.
3. Dê um nome à política e, em seguida, alterne **permitir estacionamento de chamada** para **ativado**.

    ![Captura de tela das configurações de política do estacionamento de chamada](media/call-park-add-policy.png)

4. Selecione **salvar**.

Você pode editar a política selecionando-a na lista e clicando em **Editar**.

Para que a política funcione, ela deve ser atribuída aos usuários. Você pode [atribuir a política a usuários individualmente](assign-policies.md) ou atribuí-las a um grupo.

Para atribuir uma política de peça de chamada a um grupo

1. Na página **políticas de estacionamento de chamada** , na guia **atribuição de política de grupo** , clique em **Adicionar grupo**.
2. Procure o grupo que você deseja usar e clique em **Adicionar**.
3. Escolha uma classificação em comparação com outras tarefas de grupo.
4. Em **Selecione uma política**, escolha a política à qual você deseja atribuir esse grupo.

    ![](media/call-park-assign-policy-to-group.png)

5. Clique em **Aplicar**.

## <a name="related-topics"></a>Tópicos relacionados

[Estacionar uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Atribuir políticas a seus usuários no Teams](assign-policies.md)

[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)