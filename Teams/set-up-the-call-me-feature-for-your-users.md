---
title: Configurar o recurso Telefonar para Mim para os usuários
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o recurso ligar para mim no Microsoft Teams para que os usuários possam ingressar na parte de áudio por telefone quando o uso do computador para áudio pode não ser possível.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c2343ce76e404ce2462cdbfc443130058112dcc4
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140854"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurar o recurso Telefonar para Mim para os usuários

No Microsoft Teams, o recurso **Call me** fornece aos usuários uma maneira de ingressar na parte de áudio de uma reunião por telefone. Isso é útil em cenários em que o uso de um computador para áudio pode não ser possível. Os usuários obtêm a parte de áudio da reunião por meio de seu telefone celular ou linha terrestre e a parte&mdash;de conteúdo da reunião, quando outro participante da reunião compartilha sua&mdash;tela ou reproduz um vídeo por meio de seu computador.

> [!IMPORTANT]
> Durante a duração da epidemia de COVID-19, recomendamos que os usuários ingressem nas reuniões clicando no botão **Participar das reuniões do Teams** em vez de discarem usando os números de conferência PSTN ou usando o **Ligue para mim em**</strong>. Isso é principalmente devido ao congestionamento nas infraestruturas de telefonia dos países afetados por COVID-19. Ao evitar chamadas PSTN, você provavelmente terá uma melhor qualidade de áudio. 

## <a name="the-user-experience"></a>A experiência do usuário

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Ingressar em uma reunião usando o telefone para áudio

Clique em **ingressar** para ingressar em uma reunião e, em seguida, clique em **áudio do telefone** na tela **escolher suas configurações de áudio e vídeo** . Aqui, os usuários podem ter a chamada de reunião e participar delas ou discar manualmente para a reunião.

![Captura de tela da opção áudio do telefone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Permitir que a reunião do teams seja chamada**

Na tela **usar telefone para áudio** , o usuário insere o número de telefone e, em seguida, clica em **telefonar para mim**. A reunião chama o usuário e a une à reunião.

![Captura de tela da opção ligar para mim na tela usar telefone para áudio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Discar manualmente**

Outra maneira de ingressar é discar diretamente para a reunião. Na tela **usar telefone para áudio** , clique em **discar manualmente** para obter uma lista de números de telefone a serem usados para discar para a reunião.

![Captura de tela da opção discar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Fazer uma chamada de retorno quando algo der errado com o áudio durante uma reunião

Se um usuário enfrentar problemas de áudio ao usar o computador durante uma reunião, o usuário poderá facilmente alternar para usar o telefone de áudio. O Microsoft Teams detecta quando um problema de áudio ou dispositivo ocorre e redireciona o usuário para usar o telefone ao exibir uma opção **ligar para mim** .

Veja um exemplo da mensagem e a opção **ligar para mim** que é exibida quando o Microsoft Teams não detecta um microfone.

![Captura de tela da opção ligar para fazer chamadas](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

O usuário clica em **ligar para mim de volta**, que exibe a tela **usar telefone para áudio** . A partir daqui, eles podem digitar seu número de telefone e fazer com que as equipes de reunião liguem e ingressem na reunião ou discarem manualmente para a reunião.

## <a name="set-up-the-call-me-feature"></a>Configurar o recurso ligar para mim

Para habilitar o recurso ligar para mim para os usuários de sua organização, é necessário configurar o seguinte:

- A audioconferência está habilitada para os usuários de sua organização que agendam reuniões (organizadores da reunião). Para saber mais, consulte [Configurar a conferência de áudio para o Microsoft Teams](set-up-audio-conferencing-in-teams.md) e [gerenciar as configurações de audioconferência para um usuário no Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- Os usuários podem discar de reuniões. Para saber mais, consulte [gerenciar as configurações de audioconferência de áudio para um usuário no Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Se um usuário não tiver discagem de reuniões habilitada, a opção **ligar para mim** não estará disponível e o usuário não receberá uma chamada para ingressar nela na reunião. Em vez disso, o usuário vê uma lista de números de telefone na tela **usar telefone para áudio** que pode ser usada para discar manualmente para a reunião em seu telefone.
