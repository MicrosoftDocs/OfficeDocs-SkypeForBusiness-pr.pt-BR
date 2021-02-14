---
title: Configurar o recurso Telefonar para Mim para os usuários
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o recurso Telefonar para mim no Teams para que os usuários possam ingressar na parte de áudio por telefone ao usar o computador para áudio.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821091"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurar o recurso Telefonar para Mim para os usuários

No Microsoft Teams, o **recurso Telefonar para mim** oferece aos usuários uma maneira de ingressar na parte de áudio de uma reunião por telefone. Isso é útil em cenários em que o uso de um computador para áudio pode não ser possível. Os usuários ficam com a parte de áudio da reunião por meio de seu celular ou telefone fixo e a parte de conteúdo da reunião, como quando outro participante da reunião compartilha sua tela ou reproduz um vídeo pelo &mdash; &mdash; computador.

> [!IMPORTANT]
> 
> Em períodos com quantidade elevada de reuniões (que estamos passando durante a epidemia de COVID-19), recomendamos que os usuários ingressem em reuniões clicando no botão <strong>Participar de reunião do Teams</strong> em vez de discarem usando os números de conferência PSTN ou usando o <strong>Ligar para mim em</strong>. Isso ajuda a garantir a qualidade do áudio durante os períodos em que grandes quantidades de reunião estão congestionando a rede PSTN. 

> [!IMPORTANT]
> Durante a duração da epidemia de COVID-19, recomendamos que os usuários ingressem nas reuniões clicando no botão **Participar das reuniões do Teams** em vez de discarem usando os números de conferência PSTN ou usando o **Ligue para mim em**</strong>. Isso é principalmente devido ao congestionamento nas infraestruturas de telefonia dos países afetados por COVID-19. Ao evitar chamadas PSTN, você provavelmente terá uma melhor qualidade de áudio. 

## <a name="the-user-experience"></a>A experiência do usuário

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Ingressar em uma reunião usando o telefone para áudio

Clique **em** Ingressar para ingressar  em uma reunião e, em seguida, clique em Áudio do telefone na tela Escolher suas configurações **de áudio e** vídeo. A partir daqui, os usuários podem fazer a chamada de reunião e ingressar neles ou discar manualmente para a reunião.

![Captura de tela da opção de áudio Telefone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Permitir a chamada de reunião do Teams**

Na tela **Usar telefone para áudio,** o usuário ins lista seu número de telefone e, em seguida, clica **em Telefonar para mim.** A reunião chamará o usuário e o ingressará na reunião.

![Captura de tela da opção Telefonar para mim na tela Usar telefone para áudio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Discar manualmente**

Outra maneira de ingressar é discar diretamente para a reunião. Na tela Usar telefone para **áudio,** clique em Discar **manualmente** para obter uma lista de números de telefone a usar para discar para a reunião.

![Captura de tela da opção Discar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Receber uma chamada de volta quando algo der errado com o áudio durante uma reunião

Se um usuário tiver problemas de áudio ao usar o computador durante uma reunião, o usuário poderá facilmente alternar para o uso do telefone para áudio. O Teams detecta quando ocorre um problema de áudio ou dispositivo e redireciona o usuário para usar seu telefone exibindo uma opção **Telefonar para** mim de volta.

Veja um exemplo da mensagem e da opção Ligar para mim **de** volta que é exibida quando o Teams não detecta um microfone.

![Captura de tela da opção Chamar-me de volta](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

O usuário clica em Telefonar para mim de **volta,** que exibe a **tela Usar telefone para** áudio. A partir daqui, eles podem inserir o número de telefone e fazer a chamada de reunião do Teams e ingressar na reunião ou discar manualmente para a reunião.

## <a name="set-up-the-call-me-feature"></a>Configurar o recurso Telefonar para mim

Para habilitar o recurso Telefonar para mim para usuários em sua organização, o seguinte deve ser configurado:

- A audioconferência está habilitada para usuários em sua organização que agendam reuniões (organizadores da reunião). Para saber mais, confira [Configurar a Audioconferência](set-up-audio-conferencing-in-teams.md) para o Teams e gerenciar as configurações de [Audioconferência de](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)um usuário no Teams.

- Os usuários podem discar de reuniões. Para saber mais, confira [Gerenciar as configurações de Audioconferência de um usuário no Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

Se um usuário não tiver a discagem  de reuniões habilitada, a opção Telefonar para mim não estará disponível e o usuário não receberá uma chamada para ingressar na reunião. Em vez disso, o usuário vê  uma lista de números de telefone na tela Usar telefone para áudio que ele pode usar para discar manualmente para a reunião em seu telefone.
