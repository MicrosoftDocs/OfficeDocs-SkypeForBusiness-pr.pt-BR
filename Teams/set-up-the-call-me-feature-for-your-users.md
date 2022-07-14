---
title: Configurar o recurso Telefonar para Mim para os usuários
author: CarolynRowe
ms.author: crowe
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o recurso Ligar para mim no Teams para que os usuários possam ingressar na parte de áudio por telefone ao usar o computador para áudio.
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a144e6a751f44ff520ee0317dbbcb390f30abbfd
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794529"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurar o recurso Telefonar para Mim para os usuários

No Microsoft Teams, o **recurso Chamar-me** oferece aos usuários uma maneira de ingressar na parte de áudio de uma reunião por telefone. Isso é útil em cenários em que o uso de um computador para áudio pode não ser possível. Os usuários&mdash;obtêm a parte de áudio da reunião por meio de seu telefone celular ou telefone fixo e a parte de conteúdo da reunião, como quando outro participante da reunião compartilha sua&mdash;tela ou reproduz um vídeo por meio de seu computador.

> [!IMPORTANT]
> 
> Em períodos com quantidade elevada de reuniões (que estamos passando durante a epidemia de COVID-19), recomendamos que os usuários ingressem em reuniões clicando no botão <strong>Participar de reunião do Teams</strong> em vez de discarem usando os números de conferência PSTN ou usando o <strong>Ligar para mim em</strong>. Isso ajuda a garantir a qualidade do áudio durante os períodos em que grandes quantidades de reunião estão congestionando a rede PSTN.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>A experiência do usuário

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Ingressar em uma reunião usando o telefone para áudio

Clique **em Ingressar** para ingressar em uma reunião, em seguida,  telefone **áudio** na tela Escolher suas opções de vídeo e áudio e clique **em Ingressar agora**. A partir daqui, os usuários podem fazer a chamada de reunião e ingressá-los ou discar manualmente para a reunião.

![Captura de tela da opção de áudio Telefone.](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Permitir a chamada de reunião do Teams**

Na tela **Usar telefone para áudio** , o usuário insere o número de telefone e clica em **Ligar para mim**. A reunião chama o usuário e o ingressa na reunião.

![Captura de tela da opção Chamar-me na tela Usar telefone para áudio.](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Discar manualmente**

Outra maneira de ingressar é discar diretamente para a reunião. Na tela **Usar telefone para áudio** , clique em Discar **manualmente** para obter uma lista de números de telefone a serem usadas para discar para a reunião.

![Captura de tela da opção Discar manualmente.](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Receber uma chamada de volta quando algo der errado com o áudio durante uma reunião

Se um usuário tiver problemas de áudio ao usar o computador durante uma reunião, o usuário poderá mudar facilmente para o uso do telefone para áudio. O Teams detecta quando ocorre um problema de áudio ou dispositivo e redireciona o usuário para usar seu telefone exibindo uma **opção Ligar para mim de** volta.

Aqui está um exemplo da mensagem e a opção **Chamar-me** de volta que é exibida quando o Teams não detecta um microfone.

![Captura de tela da opção Chamar-me de volta.](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

O usuário clica em **Chamar-me de volta**, o que abre a **tela Usar telefone para** áudio. A partir daqui, eles podem inserir seu número de telefone e fazer a chamada de reunião do Teams e ingressá-los na reunião ou discar manualmente para a reunião.

## <a name="set-up-the-call-me-feature"></a>Configurar o recurso Chamar-me

Para habilitar o recurso Chamar-me para usuários em sua organização, o seguinte deve ser configurado:

- A Audioconferência está habilitada para usuários em sua organização que agendam reuniões (organizadores da reunião). Para saber mais, confira [Configurar a Audioconferência para o Teams](set-up-audio-conferencing-in-teams.md) e gerenciar as configurações de [Audioconferência para um usuário no Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- O organizador da reunião pode discar de reuniões. Para saber mais, confira [Gerenciar as configurações de Audioconferência para um usuário no Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Se o organizador da reunião não tiver a discagem das reuniões habilitada, a  opção de áudio Telefone na  tela Escolher opções de áudio e vídeo não estará disponível para ninguém e outros usuários não poderão receber uma chamada para ingressá-los na reunião. Para usuários com discagem habilitada, depois de ingressar na reunião, eles podem ingressar em outras pessoas discando seu número no ícone Mostrar **participantes** .
