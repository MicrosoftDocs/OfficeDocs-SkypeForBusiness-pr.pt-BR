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
description: Saiba mais sobre como usar o parque de chamada e recuperá-lo para colocar uma chamada em espera no Microsoft Teams.
ms.openlocfilehash: d49e6a5a9bc25a0c7a3e25d548e2743b7f4584fb
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278711"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamento e recuperação de chamadas no Microsoft Teams

O parque de chamada e recuperação é um recurso que permite que um usuário coloque uma chamada em espera. Quando uma chamada é parada, o serviço gera um código exclusivo para recuperação de chamada. O usuário que estacionou a chamada ou outra pessoa pode usar esse código com um aplicativo ou dispositivo com suporte para recuperar a chamada. (Consulte Parque [uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) para obter detalhes.)

Alguns dos cenários comuns para usar o parque de chamada são:

- Um recepcionista faz uma chamada para alguém trabalhando em uma fábrica. Em seguida, o recepcionista anuncia a chamada e o número do código no sistema de endereços público. O usuário para quem a chamada é, em seguida, pode pegar um telefone do Teams no chão de fábrica e inserir o código para recuperar a chamada.
- Um usuário para de fazer uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia. Em seguida, o usuário pode inserir o código para recuperar a chamada de um telefone de mesa do Teams.
- Um representante de suporte para uma chamada de cliente e envia um comunicado em um canal do Teams para que um especialista recupere a chamada e ajude o cliente. Um especialista ins chave o código nos clientes do Teams para recuperar a chamada

Para parque e recuperação de chamadas, um usuário deve ser um usuário do Enterprise Voice e deve ser incluído em uma política de parque de chamadas.

> [!NOTE]
> O parque de chamadas e a recuperação só está disponível no modo de implantação somente do [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e não tem suporte em telefones IP do Skype for Business.

## <a name="configure-call-park-and-retrieve"></a>Configurar o parque de chamada e recuperar

Você deve ser um administrador do Teams para configurar o parque de chamada e recuperá-lo. Ele é desabilitado por padrão. Você pode habilita-lo para usuários e criar grupos de usuários usando a política de parque de chamada. Quando você aplica a mesma política a um conjunto de usuários, eles podem parquer e recuperar chamadas entre si.

Para habilitar uma política de parque de chamada

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, acesse **as** políticas do parque de  >  **Chamada de Voz.**
2. Na guia **Gerenciar políticas,** clique em **Adicionar.**
3. Dê um nome à política e, em seguida, **alternar Permitir parque de chamada** para **1.**

    ![Captura de tela das configurações de política do parque de chamada](media/call-park-add-policy.png)

4. Selecione **Salvar**.

Você pode editar a política selecionando-a na lista e clicando em **Editar.**

Para que a política funcione, ela deve ser atribuída aos usuários. Você pode [atribuir a política aos usuários individualmente](assign-policies.md) ou atribuí-la a um grupo.

Para atribuir uma política de parte de chamada a um grupo

1. Na página **Políticas do parque de** chamada, na guia de atribuição de política **de** grupo, clique em **Adicionar grupo.**
2. Pesquise o grupo que você deseja usar e clique em **Adicionar.**
3. Escolha uma classificação em comparação com outras atribuições de grupo.
4. Em **Selecionar uma política,** escolha a política à qual você deseja atribuir esse grupo.

    ![imagem de políticas de parque](media/call-park-assign-policy-to-group.png)

5. Selecione **Aplicar.**

## <a name="related-topics"></a>Tópicos relacionados

[Fazer uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Atribua políticas a seus usuários no Teams](assign-policies.md)

[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
