---
title: Configurar a resposta automática para Teams dispositivos Android
author: KarliStites
ms.author: kastites
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
ms.custom: null
description: Saiba como configurar o recurso de resposta automática para Salas do Microsoft Teams em dispositivos de Teams de vídeo com o PowerShell.
---

# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Configurar a resposta automática para Salas do Microsoft Teams em dispositivos de telefone de Teams Android e vídeo

Este artigo ajudará você a configurar o recurso de resposta automática no Salas do Microsoft Teams em dispositivos de Teams de vídeo. A resposta automática permite que as pessoas em sua organização com privilégios administrativos alterem suas configurações de dispositivo para aceitar automaticamente convites de reunião de entrada e aceitar automaticamente chamadas com vídeo.

## <a name="enable-auto-answer-with-powershell"></a>Habilitar a resposta automática com o PowerShell

Use os atributos a seguir para habilitar a resposta automática Salas do Microsoft Teams em dispositivos de Teams android e vídeo:

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Ativar a resposta automática para convites de reunião de entrada

Use **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** para ativar a resposta automática para convites de reunião de entrada. A resposta automática **está desligada** por padrão. Essa política só se aplica a convites de reunião de entrada e não dá suporte a outros tipos de chamada. Leia [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) para obter mais informações sobre o cmdlet.

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Definir o modo de entrada do dispositivo

Use **Set-CsTeamsIPPhonePolicy -SignInMode** para definir o modo de entrada do dispositivo para determinar o comportamento ao entrar no Teams. Leia [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) para obter mais informações sobre o cmdlet.

Há três opções para o modo de login:

- **UserSignIn:** Permite que um usuário individual Teams experiência no telefone.
- **CommonAreaPhoneSignIn:** Habilita uma experiência de telefone de área comum no telefone.
- **MeetingSignIn:** Habilita uma experiência de sala de reunião no telefone.

Por exemplo, a política a seguir define o modo de login como uma experiência de sala de reunião.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Configurar configurações de dispositivo

Depois de ativar a resposta automática, os usuários com permissões administrativas podem ativar o recurso em suas configurações de dispositivo. Para habilitar o recurso no nível do dispositivo, você precisa ativar convites de reunião de entrada de aceitação **automática**. Você também pode ativar **Aceitar automaticamente com vídeo**. As duas configurações estão desligadas por padrão.

## <a name="related-topics"></a>Tópicos relacionados

[Suporte da Microsoft: chamadas e dispositivos](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
