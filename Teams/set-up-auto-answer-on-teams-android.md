---
title: Configurar a resposta automática para Teams Android dispositivos
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: kponnus
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Saiba como configurar o recurso de resposta automática para Salas do Microsoft Teams em Android e Teams de vídeo com o PowerShell.
ms.openlocfilehash: fac458a2b7b100a2074dbaac0e209fbdd3527eef
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646590"
---
# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Configurar a resposta automática para Salas do Microsoft Teams em Android e Teams de vídeo

Este artigo ajudará você a configurar o recurso de resposta automática no Salas do Microsoft Teams em Android e Teams de vídeo. A resposta automática permite que as pessoas em sua organização com privilégios administrativos alterem suas configurações de dispositivo para aceitar automaticamente convites de reunião de entrada e aceitar automaticamente chamadas com vídeo.

## <a name="enable-auto-answer-with-powershell"></a>Habilitar a resposta automática com o PowerShell

Use os seguintes atributos para habilitar a resposta automática Salas do Microsoft Teams em Android e Teams de vídeo:

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Ativar a resposta automática para convites de reunião de entrada

Use **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** para ativar a resposta automática para convites de reunião recebidos. A resposta automática **é desativada** por padrão. Essa política só se aplica a convites de reunião de entrada e não dá suporte a outros tipos de chamada. Leia [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) para obter mais informações sobre o cmdlet.

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Definir o modo de entrada do dispositivo

Você usa **Set-CsTeamsIPPhonePolicy -SignInMode** para definir o modo de entrada do dispositivo para determinar o comportamento ao entrar no Teams. Leia [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) para obter mais informações sobre o cmdlet.

Há três opções para o modo de entrada:

- **UserSignIn:** Habilita uma experiência Teams usuário individual no telefone.
- **CommonAreaPhoneSignIn:** Habilita uma experiência de telefone de área comum no telefone.
- **MeetingSignIn:** Habilita uma experiência de sala de reunião no telefone.

Por exemplo, a política a seguir define o modo de entrada para uma experiência de sala de reunião.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Definir configurações do dispositivo

Depois de habilitar a resposta automática, os usuários com permissões administrativas podem ativar o recurso nas configurações do dispositivo. Para habilitar o recurso no nível do dispositivo, você precisa ativar a aceitação automática de **convites de reunião de entrada**. Você também pode ativar a **aceitação automática com vídeo**. As duas configurações estão desativadas por padrão.

## <a name="related-topics"></a>Tópicos relacionados

[Suporte da Microsoft: chamadas e dispositivos](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
