---
title: Conferência de áudio com roteamento direto para GCCH e DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Saiba como você pode usar a conferência de áudio com roteamento direto em ambientes GCCH e DoD.
ms.openlocfilehash: 6c1403fedbbb47231780916eb8c7acb8014539e9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992891"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Conferências de Áudio com Roteamento Direto para GCC Alto e DoD

Conferência de áudio com roteamento direto para GCC elevado e DoD permite que os participantes ingressem em reuniões de equipe na sua organização GCC alta ou DoD usando um dispositivo de telefone. Os participantes da reunião podem preferir usar um dispositivo de telefone para ingressar em reuniões de equipe em cenários, como quando a conectividade com a Internet é limitada ou quando os usuários estão em trânsito e não têm acesso ao Teams. Os participantes podem optar por ingressar em reuniões discando para um número de telefone de discagem para a sua organização ou fazendo com que a reunião disque para o dispositivo telefônico.

Com o roteamento direto para GCC High e DoD, a sua organização usa seus próprios números como números de telefone de discagem e todas as chamadas discadas na reunião para dispositivos telefônicos são roteadas via roteamento direto. Para habilitar o serviço, as organizações precisam configurar o roteamento direto e configurar os números de telefone que podem ser usados como números de telefone de discagem. A necessidade de usar o roteamento direto é diferente do serviço de audioconferência, que é oferecido a organizações não-GCC altas e não-DoD nas quais os números de telefone de discagem são fornecidos pela Microsoft.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Implantar a videoconferência com roteamento direto para GCC elevado e DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Etapa 1: obter a conferência de áudio com roteamento direto para licenças GCC elevadas ou DoD 

Para usar a conferência de áudio no GCC High ou DoD, sua organização e os usuários da sua organização precisam ter uma conferência de áudio com licença de roteamento direto atribuída. Aqui estão as licenças de que você precisa para habilitar a audioconferência com roteamento direto para GCC High ou DoD.

- GCC alto: uma conferência de áudio-GCC alta licença de locatário para sua organização e conferência de áudio-GCC licenças elevadas para seus usuários.

- DoD: uma conferência de áudio-licença de locatário DoD para sua organização e conferência de áudio – licenças DoD para seus usuários.

É preciso ter uma licença de locatário e pelo menos uma licença de usuário para habilitar o serviço. Você não pode habilitar o serviço apenas com a licença de locatário ou com apenas licenças de usuário. Para obter licenças de serviço para o seu locatário e os usuários da sua organização, entre em contato com a equipe da sua conta.

> [!IMPORTANT]
> Os usuários não podem ser habilitados para conferências de áudio com roteamento direto até que os números de telefone de discagem estejam configurados. Recomendamos que você não atribua conferências de áudio com roteamento direto para licenças de GCC elevada ou DoD para os usuários até configurar números de telefone de discagem conforme descrito neste artigo.

### <a name="step-2-set-up-direct-routing"></a>Etapa 2: configurar o roteamento direto

Para configurar o roteamento direto, consulte os seguintes artigos:

- [Planejar o Roteamento Direto](direct-routing-plan.md)

- [Configurar o Roteamento Direto](direct-routing-configure.md)

> [!NOTE]
> Ao configurar o roteamento direto, lembre-se de usar os FQDNs e as portas do GCC superiores ou DoD específicas descritos nestes dois artigos.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Etapa 3: configurar números de telefone de discagem

Os números de telefone de discagem são os números de telefone associados à sua ponte de audioconferência. Esses números são usados pelos participantes para ingressar em reuniões agendadas pelos usuários da sua organização. Esses números também estão incluídos nos convites de reunião dos usuários que agendam reuniões em sua organização e na página "encontrar um número local".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definir números de telefone de serviço em seu locatário

Você pode usar o cmdlet New-csHybridTelephoneNumber do PowerShell para definir números de telefone de serviço em seu locatário que podem ser usados para direcionar chamadas para o serviço de audioconferência via roteamento direto. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Por exemplo:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Atribuir os números de telefone do serviço à ponte de videoconferência da sua organização

Você pode atribuir números de telefone de serviço à ponte de videoconferência da sua organização usando o cmdlet Register-Csonlinedialinconferencingservicenumberhttp do PowerShell.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Você pode ver a identificação da sua ponte de conferência de áudio usando Get-CsOnlineDialInConferencingBridge. Por exemplo:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Etapa 4: atribuir uma conferência de áudio com roteamento direto para licenças de GCC elevada ou DoD para seus usuários

Para atribuir uma conferência de áudio com roteamento direto para licenças de GCC elevada ou DoD para o usuário, consulte [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Etapa 5: (opcional) Veja uma lista de números de conferência de áudio no Microsoft Teams

Para ver a lista de números de conferência de áudio da sua organização, acesse [ver uma lista de números de conferência de áudio no Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Etapa 6: (opcional) definir idiomas do atendedor automático para os números de discagem da conferência de áudio da sua organização

Para alterar os idiomas dos números de discagem da conferência de áudio da sua organização, consulte [definir idiomas do atendedor automático para videoconferências no Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Etapa 7: (opcional) alterar as configurações da ponte de conferência de áudio da sua organização

Para alterar as configurações da ponte de conferência de áudio da sua organização, consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Etapa 8: (opcional) definir os números de telefone incluídos nos convites para reunião dos usuários em sua organização

Para alterar o conjunto de números de telefone que estão incluídos nos convites de reunião dos usuários em sua organização, confira [definir os números de telefone incluídos nos convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Os recursos de audioconferência não são compatíveis com a videoconferências com roteamento direto para GCC High e DoD

Veja a seguir os recursos de audioconferência que não têm suporte na videoconferência com roteamento direto para GCC High e DoD:

- Notificações de entrada e saída usando a gravação de nomes. Para videoconferências com roteamento direto, as notificações de entrada e saída são reproduzidas na reunião como tons.

- Políticas de restrição de chamadas de saída para videoconferência. Os controles em nível de usuário para restringir chamadas de saída não são aplicáveis a chamadas discadas de reunião roteadas via roteamento direto.

- Desative o uso de números de chamada gratuita para o organizador de reuniões específico. Os controles em nível de usuário para restringir o uso de números de chamada gratuita para ingressar nas reuniões de sua organização não são aplicáveis a chamadas roteadas via roteamento direto.

- Enviar emails de notificação para os usuários quando as configurações forem alteradas. Os emails de notificação de audioconferência não têm suporte para videoconferências com roteamento direto para GCC High e DoD.
