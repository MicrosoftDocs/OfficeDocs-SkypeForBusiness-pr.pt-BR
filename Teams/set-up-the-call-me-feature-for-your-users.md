---
title: Configurar o recurso ligar para mim para seus usuários
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como configurar o recurso ligar para mim no Microsoft Teams para que os usuários possam ingressar na parte de áudio por telefone em cenários em que o uso do computador para áudio pode não ser possível.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f1ffee416b1d5674e831fda4c5bb15a89c510f4
ms.sourcegitcommit: 1ddd29e3839e50387efb4ec7b9d2154991bb2642
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35432115"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurar o recurso ligar para mim para seus usuários

No Microsoft Teams, o recurso **Call me** fornece aos usuários uma maneira de ingressar na parte de áudio de uma reunião por telefone. Isso é útil em cenários em que o uso de um computador para áudio pode não ser possível. Os usuários obtêm a parte de áudio da reunião por meio de seu telefone celular ou linha terrestre e a parte&mdash;de conteúdo da reunião, quando outro participante da reunião compartilha sua&mdash;tela ou reproduz um vídeo por meio de seu computador.

## <a name="the-user-experience"></a>A experiência do usuário

Clique **** em ingressar para ingressar em uma reunião e, em seguida, clique em **áudio do telefone** na tela **escolher suas configurações de áudio e vídeo** . Aqui, os usuários podem ter a chamada de reunião e participar delas ou discar manualmente para a reunião.

![Captura de tela da opção áudio do telefone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Permitir que a reunião do teams seja chamada**

Na tela **usar telefone para áudio** , o usuário insere o número de telefone e, em seguida, clica em **telefonar para mim**. A reunião chama o usuário e a une à reunião.

![Captura de tela da opção ligar para mim na tela usar telefone para áudio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Discar manualmente**

Outra maneira de ingressar é discar diretamente para a reunião. Na tela **usar telefone para áudio** , clique em **discar manualmente** para obter uma lista de números de telefone a serem usados para discar para a reunião.

![Captura de tela da opção discar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a>Configurar o recurso ligar para mim

Para habilitar o recurso ligar para mim para os usuários de sua organização, é necessário configurar o seguinte:

- A audioconferência está habilitada para os usuários de sua organização que agendam reuniões (organizadores da reunião). Para saber mais, consulte [Configurar a conferência de áudio para](set-up-audio-conferencing-in-teams.md) o Microsoft Teams e [gerenciar as configurações de audioconferência para um usuário no Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- Os usuários podem discar de reuniões. Para saber mais, consulte [gerenciar as configurações de audioconferência de áudio para um usuário no](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)Microsoft Teams.

Se um usuário não tiver discagem de reuniões habilitada, a opção **ligar para mim** não estará disponível e o usuário não receberá uma chamada para ingressar nela na reunião. Em vez disso, o usuário vê uma lista de números de telefone na tela **usar telefone para áudio** que pode ser usada para discar manualmente para a reunião em seu telefone.

