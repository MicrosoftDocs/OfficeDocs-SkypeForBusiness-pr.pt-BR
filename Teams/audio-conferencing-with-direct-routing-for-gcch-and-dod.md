---
title: Conferência de áudio com roteamento direto, GCCH e DoD
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: O administrador pode saber mais sobre como usar a conferência de áudio com roteamento direto em ambientes GCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262488"
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
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
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


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Etapa 4: definir uma política de roteamento de voz global para habilitar o roteamento de chamadas de saída de reuniões

O roteamento de chamadas de saída feitas à PSTN de reuniões organizadas por usuários em sua organização é definido pela política de roteamento de voz global da sua organização. Se a sua organização tiver uma política global de roteamento de voz definida, verifique se a política de roteamento de voz global permite as chamadas de saída para a PSTN que devem ser iniciadas a partir de reuniões organizadas por usuários da sua organização. Se a sua organização não tiver uma política global de roteamento de voz definida, você precisará definir uma para habilitar o roteamento de chamadas de saída para a PSTN de reuniões organizadas por usuários em sua organização. Observe que a política de roteamento de voz global da sua organização também se aplica a chamadas individuais feitas à PSTN pelos usuários da sua organização. Se as chamadas individuais para a PSTN estiverem habilitadas para os usuários de sua organização, certifique-se de que a política de roteamento de voz global atenda às necessidades da sua organização para ambos os tipos de chamadas. 

> [!NOTE]
> O roteamento baseado em local não está disponível nas implantações do Microsoft 365 governo Community Cloud (GCC) de alta ou DoD. Ao habilitar a conferência de áudio, verifique se nenhum usuário de videoconferência nos ambientes GCC High ou DoD está habilitado para roteamento baseado em local.

#### <a name="defining-a-global-voice-routing-policy"></a>Definindo uma política de roteamento de voz global

Uma política de roteamento de voz global pode ser definida definindo um uso de PSTN, uma rota de voz, uma política de roteamento de voz e atribuindo a nova política de roteamento de voz como a política de roteamento de voz global da sua organização.

As etapas a seguir descrevem como definir uma nova política de roteamento de voz global para uma organização sem uma. Se a sua organização já tiver políticas de roteamento de voz definidas, verifique se a seguinte configuração não está em conflito com as políticas de roteamento de voz existentes da sua organização.

Para criar um novo uso de PSTN em uma sessão remota do PowerShell no Skype for Business Online, use o seguinte comando:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Para obter informações adicionais, consulte [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).

Para criar uma nova rota de voz, use o seguinte comando:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Ao definir uma nova rota de voz para sua organização, especifique um ou vários dos gateways PSTN online PSTN que foram definidos para a sua organização durante a configuração de roteamento direto. 

O padrão de número especifica quais chamadas serão roteadas na lista especificada de gateways com base no número de telefone de destino da chamada. No exemplo acima, as chamadas para todos os destinos do mundo corresponderão à rota de voz. Se quiser restringir os números de telefone que podem ser discados das reuniões de usuários em sua organização, você pode alterar o padrão de número para que a rota de voz corresponda apenas os padrões de número dos destinos permitidos. Observe que, se não houver rotas de voz que correspondam ao padrão de número do número de telefone de destino de uma determinada chamada, a chamada não será roteada.

Para obter informações adicionais, consulte [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).

Para criar uma nova política de roteamento de voz, use o seguinte comando:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Se vários usos de PSTN estiverem sendo definidos na política de roteamento de voz, eles serão avaliados na ordem em que estão definidos. É recomendável que os usos de PSTN sejam definidos na ordem do mais específico para o mais genérico em termos dos padrões de número das rotas de voz associadas aos usos de PSTN. Por exemplo, se um uso de PSTN foi definido para direcionar chamadas para os Estados Unidos, e outro uso de PSTN foi definido para direcionar chamadas para qualquer outro local do mundo, o uso de PSTN para chamadas para os Estados Unidos deve estar listado na política de roteamento de voz à frente do uso de PSTN para direcionar chamadas para qualquer outro local do mundo.

Para obter informações adicionais, consulte [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Para atribuir a nova rota de voz à política de roteamento de voz global da sua organização, use o seguinte comando:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Para obter informações adicionais, consulte [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Após a definição da política de roteamento de voz global, todas as chamadas feitas a partir de reuniões organizadas por usuários em sua organização serão avaliadas em relação às rotas de voz associadas aos usos de PSTN da política de roteamento de voz global. As chamadas de saída serão roteadas de acordo com a primeira rota de voz que corresponde ao padrão de número do número de telefone discado.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Etapa 5: atribuir uma conferência de áudio com roteamento direto para licenças de GCC elevada ou DoD para seus usuários

Para atribuir uma conferência de áudio com roteamento direto para licenças de GCC elevada ou DoD para o usuário, consulte [atribuir licenças aos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Etapa 6: (opcional) Veja uma lista de números de conferência de áudio no Microsoft Teams

Para ver a lista de números de conferência de áudio da sua organização, vá para [ver uma lista de números de conferência de áudio no Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Etapa 7: (opcional) definir idiomas do atendedor automático para os números de discagem da conferência de áudio da sua organização

Para alterar os idiomas dos números de discagem da conferência de áudio da sua organização, consulte [definir idiomas do atendedor automático para videoconferências no Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Etapa 8: (opcional) alterar as configurações da ponte de conferência de áudio da sua organização

Para alterar as configurações da ponte de conferência de áudio da sua organização, consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Etapa 9: (opcional) definir os números de telefone incluídos nos convites para reunião dos usuários em sua organização

Para alterar o conjunto de números de telefone que estão incluídos nos convites de reunião dos usuários em sua organização, confira [definir os números de telefone incluídos nos convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Os recursos de audioconferência não são compatíveis com a videoconferências com roteamento direto para GCC High e DoD

Veja a seguir os recursos de audioconferência que não têm suporte na videoconferência com roteamento direto para GCC High e DoD:

- Notificações de entrada e saída usando a gravação de nomes. Para videoconferências com roteamento direto, as notificações de entrada e saída são reproduzidas na reunião como tons.

- Políticas de restrição de chamadas de saída para videoconferência. Os controles em nível de usuário para restringir chamadas de saída não são aplicáveis a chamadas discadas de reunião roteadas via roteamento direto.

- Desative o uso de números de chamada gratuita para o organizador de reuniões específico. Os controles em nível de usuário para restringir o uso de números de chamada gratuita para ingressar nas reuniões de sua organização não são aplicáveis a chamadas roteadas via roteamento direto.

- Enviar emails de notificação para os usuários quando as configurações forem alteradas. Os emails de notificação de audioconferência não têm suporte para videoconferências com roteamento direto para GCC High e DoD.
