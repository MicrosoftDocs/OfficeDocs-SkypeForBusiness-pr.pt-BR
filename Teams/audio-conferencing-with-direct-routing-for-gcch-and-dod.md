---
title: Audioconferência com Roteamento Direto, GCCH e DoD
author: HowlinWolf-92
ms.author: v-mahoffman
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
ms.localizationpriority: medium
description: O administrador pode aprender sobre como usar a Audioconferência com Roteamento Direto em ambientes GCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1e4500e5560a1e5b14af51137f98e98823f7b333
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853945"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Conferências de Áudio com Roteamento Direto para GCC Alto e DoD

A Audioconferência com Roteamento Direto para GCC Alta e DoD permite que os participantes participem de reuniões Teams reuniões em sua organização do GCC High ou DoD usando um dispositivo de telefone. Os participantes da reunião podem preferir usar um dispositivo de telefone para participar de reuniões Teams em cenários como quando a conectividade com a Internet é limitada ou quando os usuários estão na estrada e não têm acesso a Teams. Os participantes podem optar por participar de reuniões discando em um número de telefone discado para sua organização ou fazendo a reunião discar para o dispositivo de telefone.

Com a Audioconferência com Roteamento Direto para GCC Alta e DoD, sua organização usa seus próprios números como números de telefone discados e todos os discagem de reunião para dispositivos de telefone são roteados via Roteamento Direto. Para habilitar o serviço, as organizações precisam configurar o Roteamento Direto e configurar números de telefone que podem ser usados como números de telefone discados. O requisito para usar o Roteamento Direto é diferente do serviço de Audioconferência oferecido a organizações que não são GCC high e non-DoD em que os números de telefone de discagem são fornecidos pela Microsoft.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Implantar Audioconferência com Roteamento Direto para GCC Alta e DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Etapa 1: Obter Audioconferência com Roteamento Direto para GCC licenças High ou DoD 

Para usar a Audioconferência em GCC High ou DoD, sua organização e os usuários em sua organização precisam ter uma licença de Audioconferência com Roteamento Direto atribuída. Aqui estão as licenças que você precisa para habilitar a Audioconferência com Roteamento Direto para GCC Alta ou DoD.

- GCC Alta: Uma Audioconferência - GCC licença de Alto Locatário para sua organização e Audioconferência - GCC licenças de alta para seus usuários.

- DoD: Uma Audioconferência - Licença de Locatário do DoD para sua organização e Audioconferência - Licenças do DoD para seus usuários.

Uma licença de locatário e pelo menos uma licença de usuário são necessárias para habilitar o serviço. Você não pode habilitar o serviço com apenas a licença de locatário ou com apenas licenças de usuário. Para obter licenças de serviço para seu locatário e os usuários em sua organização, entre em contato com sua equipe de conta.

> [!IMPORTANT]
> Os usuários não podem ser habilitados para Audioconferência com Roteamento Direto até que os números de telefone discados sejam definidos. Recomendamos que você não atribua a Audioconferência com Roteamento Direto para licenças GCC Alta ou DoD aos usuários até configurar números de telefone de discagem conforme descrito neste artigo.  A falha ao seguir essas diretrizes pode fazer com que o bloco de discagem seja completamente ausente no Teams cliente.

### <a name="step-2-set-up-direct-routing"></a>Etapa 2: Configurar Roteamento Direto

Para configurar o Roteamento Direto, consulte os seguintes artigos:

- [Planejar o Roteamento Direto](direct-routing-plan.md)

- [Configurar o Roteamento Direto](direct-routing-configure.md)

> [!NOTE]
> Ao configurar o Roteamento Direto, lembre-se de usar os FQDNs e portas específicos do GCC High ou DoD que estão descritos nestes dois artigos.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Etapa 3: Configurar números de telefone discados

Números de telefone discados são os números de telefone associados à ponte de Audioconferência. Esses números são usados pelos participantes para participar de reuniões agendadas pelos usuários em sua organização. Esses números também estão incluídos nos convites de reunião dos usuários que agendam reuniões em sua organização e na página "Encontrar um número local".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definir números de telefone de serviço em seu locatário

Você pode usar o cmdlet New-csHybridTelephoneNumber PowerShell para definir números de telefone de serviço em seu locatário que podem ser usados para rotear chamadas para o serviço de Audioconferência por meio de Roteamento Direto. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Por exemplo:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Atribuir os números de telefone de serviço à ponte de Audioconferência da sua organização

Você pode atribuir números de telefone de serviço à ponte de Audioconferência da sua organização usando o cmdlet Register-csOnlineDialInConferencingServiceNumber PowerShell.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Você pode ver a ID da ponte de audioconferência usando Get-CsOnlineDialInConferencingBridge. Por exemplo:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Etapa 4: Definir uma política de roteamento de voz global para habilitar o roteamento de chamadas de saída de reuniões

O roteamento de chamadas de saída feitas para o PSTN a partir de reuniões organizadas por usuários em sua organização é definida pela política de roteamento de voz global da sua organização. Se sua organização tiver uma política de roteamento de voz global definida, verifique se a política de roteamento de voz global permite as chamadas de saída para a PSTN que devem ser iniciadas a partir de reuniões organizadas pelos usuários em sua organização. Se sua organização não tiver uma política de roteamento de voz global definida, você precisará definir uma para habilitar o roteamento de chamadas de saída para o PSTN a partir de reuniões organizadas pelos usuários em sua organização. Observe que a política de roteamento de voz global da sua organização também se aplica às chamadas um para uma feitas ao PSTN pelos usuários em sua organização. Se as chamadas um para um para o PSTN estão habilitadas para usuários em sua organização, certifique-se de que a política de roteamento de voz global atenda às necessidades da sua organização para ambos os tipos de chamadas. 

> [!NOTE]
> Location-Based o roteamento não está disponível em implantações Microsoft 365 Nuvem da Comunidade Governamental (GCC) High ou DoD. Ao habilitar a Audioconferência, verifique se nenhum usuário de Audioconferência no GCC High ou nos ambientes do DoD está habilitado para roteamento Location-Based.

#### <a name="defining-a-global-voice-routing-policy"></a>Definindo uma política de roteamento de voz global

Uma política de roteamento de voz global pode ser definida definindo um uso PSTN, uma rota de voz, uma política de roteamento de voz e atribuindo a nova política de roteamento de voz como a política de roteamento de voz global da sua organização.

As etapas a seguir descrevem como definir uma nova política de roteamento de voz global para uma organização sem uma. Se sua organização já tiver políticas de roteamento de voz definidas, verifique se a configuração a seguir não entra em conflito com as políticas de roteamento de voz existentes da sua organização.

Para criar um novo uso PSTN em uma sessão remota do PowerShell no Skype for Business Online, use o seguinte comando:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Para obter informações adicionais, [consulte Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).

Para criar uma nova rota de voz, use o seguinte comando:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Ao definir uma nova rota de voz para sua organização, especifique um ou vários dos gateways PSTN online PSTN que foram definidos para sua organização durante a configuração do Roteamento Direto. 

O padrão de número especifica quais chamadas serão roteadas pela lista especificada de gateways com base no número de telefone de destino da chamada. No exemplo acima, as chamadas para quaisquer destinos no mundo corresponderão à rota de voz. Se você quiser restringir os números de telefone que podem ser discados a partir das reuniões de usuários em sua organização, você pode alterar o padrão de número para que a rota de voz corresponder apenas aos padrões de número dos destinos permitidos. Observe que, se não houver rotas de voz que corresponderem ao padrão de número do número de telefone de destino de uma determinada chamada, a chamada não será roteada.

Para obter informações adicionais, [consulte New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).

Para criar uma nova política de roteamento de voz, use o seguinte comando:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Se vários usos PSTN estão sendo definidos na política de roteamento de voz, eles serão avaliados na ordem na qual são definidos. É recomendável que os usos PSTN sejam definidos na ordem do mais específico para o mais genérico em termos dos padrões de número das rotas de voz associadas aos usos PSTN. Por exemplo, se um uso PSTN foi definido para rotear chamadas para os Estados Unidos e outro uso PSTN foi definido para rotear chamadas para qualquer outro local no mundo, o uso de PSTN para chamadas para os Estados Unidos deve ser listado na política de roteamento de voz antes do uso PSTN para rotear chamadas para qualquer outro local no mundo.

Para obter informações adicionais, [consulte New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Para atribuir a nova rota de voz à política de roteamento de voz global da sua organização, use o seguinte comando:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Para obter informações adicionais, [consulte Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Depois que a política de roteamento de voz global tiver sido definida, todas as chamadas de saída feitas a partir de reuniões organizadas pelos usuários em sua organização serão avaliadas em relação às rotas de voz associadas aos usos PSTN da política de roteamento de voz global. As chamadas de saída serão roteadas de acordo com a primeira rota de voz que corresponde ao padrão de número do número de telefone discado.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Etapa 5: Atribuir Audioconferência com Roteamento Direto para GCC licenças High ou DoD para seus usuários

Para atribuir Audioconferência com Roteamento Direto para GCC licenças High ou DoD ao usuário, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Etapa 6: (Opcional) Consulte uma lista de números de Audioconferência no Teams

Para ver a lista de números de Audioconferência de sua organização, vá para Ver uma lista de números de [Audioconferência em Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Etapa 7: (Opcional) Definir idiomas de atendimento automático para os números de discagem de Audioconferência de sua organização

Para alterar os idiomas dos números de discagem de Audioconferência da sua organização, consulte Definir idiomas de atendimento automático para [Audioconferência em Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Etapa 8: (Opcional) Alterar as configurações da ponte de Audioconferência da sua organização

Para alterar as configurações da ponte de Audioconferência da sua organização, consulte Alterar as configurações de uma ponte [de Audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Etapa 9: (Opcional) Definir os números de telefone incluídos nos convites de reunião dos usuários em sua organização

Para alterar o conjunto de números de telefone incluídos nos convites de reunião dos usuários é sua organização, consulte Definir os números de telefone incluídos em [convites](set-the-phone-numbers-included-on-invites-in-teams.md)no Microsoft Teams .

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Recursos de audioconferência não suportados em Audioconferência com Roteamento Direto para GCC Alta e DoD

A seguir estão os recursos de Audioconferência que não são suportados em Audioconferência com Roteamento Direto para GCC Alta e DoD:

- Notificações de entrada e saída usando gravação de nome. Para Audioconferência com Roteamento Direto, as notificações de entrada e saída são tocadas na reunião como tons.

- Desabilite o uso de números gratuitos para o organizador específico das reuniões. Os controles no nível do usuário para restringir o uso de números de chamada gratuita para participar das reuniões da sua organização não são aplicáveis às chamadas roteada por roteamento direto.

- Enviar emails de notificação para os usuários quando suas configurações mudarem. Os emails de notificação de audioconferência não são suportados para Audioconferência com Roteamento Direto para GCC Alta e DoD.
