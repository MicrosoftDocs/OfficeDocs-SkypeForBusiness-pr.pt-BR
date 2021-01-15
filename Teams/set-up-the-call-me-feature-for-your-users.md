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
description: Saiba como configurar o recurso Telefonar-me no Teams para que os usuários possam participar da parte de áudio por telefone ao usar o computador para áudio pode não ser possível.
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

No Microsoft Teams, o **recurso Telefonar-me** oferece aos usuários uma maneira de participar da parte de áudio de uma reunião por telefone. Isso é útil em cenários em que o uso de um computador para áudio pode não ser possível. Os usuários podem obter a parte de áudio da reunião por meio de seu telefone celular ou linha fixa e a parte de conteúdo da reunião, como quando outro participante da reunião compartilha sua tela ou reproduz um vídeo pelo &mdash; &mdash; computador.

> [!IMPORTANT]
> 
> Em períodos com quantidade elevada de reuniões (que estamos passando durante a epidemia de COVID-19), recomendamos que os usuários ingressem em reuniões clicando no botão <strong>Participar de reunião do Teams</strong> em vez de discarem usando os números de conferência PSTN ou usando o <strong>Ligar para mim em</strong>. Isso ajuda a garantir a qualidade do áudio durante os períodos em que grandes quantidades de reunião estão congestionando a rede PSTN. 

> [!IMPORTANT]
> Durante a duração da epidemia de COVID-19, recomendamos que os usuários ingressem nas reuniões clicando no botão **Participar das reuniões do Teams** em vez de discarem usando os números de conferência PSTN ou usando o **Ligue para mim em**</strong>. Isso é principalmente devido ao congestionamento nas infraestruturas de telefonia dos países afetados por COVID-19. Ao evitar chamadas PSTN, você provavelmente terá uma melhor qualidade de áudio. 

## <a name="the-user-experience"></a>A experiência do usuário

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Ingressar em uma reunião usando telefone para áudio

Clique **em** Ingressar para participar de uma reunião e clique em **Áudio** do telefone na tela  **Escolher configurações de** áudio e vídeo. A partir daqui, os usuários podem fazer a chamada de reunião e participar deles ou discar manualmente para a reunião.

![Captura de tela da opção de áudio Telefone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Permitir a chamada de reunião do Teams**

Na tela **Usar telefone para áudio,** o usuário ins dá o número de telefone e clica em **Ligar para mim.** A reunião chama o usuário e o une à reunião.

![Captura de tela da opção Chamar-me no telefone Usar para tela de áudio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Discar manualmente**

Outra maneira de ingressar é discar diretamente para a reunião. Na tela **Usar telefone para** áudio, clique em Discar **manualmente** para obter uma lista de números de telefone para usar para discar para a reunião.

![Captura de tela da opção Discar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Receber uma chamada de volta quando algo der errado com o áudio durante uma reunião

Se um usuário tiver problemas de áudio ao usar o computador durante uma reunião, o usuário poderá alternar facilmente para usar o telefone para áudio. O Teams detecta quando ocorre um problema de áudio ou dispositivo e redireciona o usuário para usar o telefone exibindo uma opção **De retorno de** chamada.

Veja um exemplo da mensagem  e da opção Retornar Chamada que é exibida quando o Teams não detecta um microfone.

![Screen shot of the Call me back option](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

O usuário clica em **Ligar-me de volta,** o que exibe o **telefone Usar para tela de** áudio. A partir daqui, eles podem inserir seu número de telefone e fazer a chamada de reunião do Teams e ingressá-los na reunião ou discar manualmente para a reunião.

## <a name="set-up-the-call-me-feature"></a>Configurar o recurso Chamar-me

Para habilitar o recurso Telefonar para os usuários em sua organização, o seguinte deve ser configurado:

- A Audioconferência está habilitada para usuários em sua organização que agendam reuniões (organizadores da reunião). Para saber mais, consulte [Configurar audioconferência](set-up-audio-conferencing-in-teams.md) para o Teams e gerenciar as configurações de [audioconferência para](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)um usuário no Teams.

- Os usuários podem discar de reuniões. Para saber mais, confira [Gerenciar as configurações de Audioconferência para um usuário no Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

Se um usuário não tiver a discagem  de reuniões habilitada, a opção Telefonar para Mim não estará disponível e o usuário não receberá uma chamada para participar da reunião. Em vez disso, o usuário vê  uma lista de números de telefone no telefone Usar para tela de áudio que ele pode usar para discar manualmente para a reunião em seu telefone.
