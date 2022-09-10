---
title: Audioconferência com Roteamento Direto, GCCH e DoD
author: MicrosoftHeidi
ms.author: heidip
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
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Administração saber mais sobre como usar a Audioconferência com Roteamento Direto em ambientes GCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd467b9da8d296c21d4a0405d651bbaa6b001fd3
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641772"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Conferências de Áudio com Roteamento Direto para GCC Alto e DoD

A Audioconferência com Roteamento Direto para GCC High e DoD permite que os participantes participem de reuniões do Teams em sua organização GCC High ou DoD usando um dispositivo de telefone. Os participantes da reunião podem preferir usar um dispositivo de telefone para ingressar em reuniões do Teams em cenários como quando a conectividade com a Internet é limitada ou quando os usuários estão em trânsito e não têm acesso ao Teams. Os participantes podem optar por ingressar em reuniões discando para um número de telefone discado para sua organização ou fazendo com que a reunião disque para seu dispositivo de telefone.

Com a Audioconferência com Roteamento Direto para GCC High e DoD, sua organização usa seus próprios números como números de telefone de discagem e todas as discagem de reunião para dispositivos de telefone são roteadas por meio do Roteamento Direto. Para habilitar o serviço, as organizações precisam configurar o Roteamento Direto e configurar números de telefone que podem ser usados como números de telefone discados. O requisito para usar o Roteamento Direto é diferente do serviço de Audioconferência oferecido a organizações não GCC High e não DoD em que os números de telefone de discagem são fornecidos pela Microsoft.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Implantar audioconferência com roteamento direto para GCC High e DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Etapa 1: Obter Audioconferência com Roteamento Direto para licenças GCC High ou DoD

Para usar a Audioconferência no GCC High ou no DoD, sua organização e os usuários em sua organização precisam ter uma audioconferência com licença de Roteamento Direto atribuída. Aqui estão as licenças necessárias para habilitar a Audioconferência com Roteamento Direto para GCC High ou DoD.

- GCC High: Uma licença de Audioconferência – GCC High Tenant para sua organização e Audioconferência – licenças GCC High para seus usuários.

- DoD: uma audioconferência – licença de locatário do DoD para sua organização e audioconferência – licenças do DoD para seus usuários.

Uma licença de locatário e pelo menos uma licença de usuário são necessárias para habilitar o serviço. Você não pode habilitar o serviço apenas com a licença de locatário ou apenas com licenças de usuário. Para obter licenças de serviço para seu locatário e os usuários em sua organização, entre em contato com sua equipe de conta.

> [!IMPORTANT]
> Os usuários não podem ser habilitados para Audioconferência com Roteamento Direto até que os números de telefone de discagem sejam configurados. Recomendamos que você não atribua a Audioconferência com o Roteamento Direto para licenças GCC High ou DoD aos usuários até configurar números de telefone de discagem, conforme descrito neste artigo.  A falha ao seguir essas diretrizes pode fazer com que o teclado de discagem esteja completamente ausente no cliente do Teams.

### <a name="step-2-set-up-direct-routing"></a>Etapa 2: Configurar o Roteamento Direto

Para configurar o Roteamento Direto, consulte os seguintes artigos:

- [Planejar o Roteamento Direto](direct-routing-plan.md)

- [Configurar o Roteamento Direto](direct-routing-configure.md)

> [!NOTE]
> Ao configurar o Roteamento Direto, lembre-se de usar os FQDNs e portas específicos do GCC High ou do DoD descritos nesses dois artigos.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Etapa 3: Configurar números de telefone de discagem

Números de telefone discados são os números de telefone associados à ponte de Audioconferência. Esses números são usados pelos participantes para ingressar em reuniões agendadas pelos usuários em sua organização. Esses números também estão incluídos nos convites da reunião dos usuários que agendam reuniões em sua organização e na página "Localizar um número local".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definir números de telefone de serviço em seu locatário

Você pode usar o cmdlet New-csHybridTelephoneNumber do PowerShell para definir números de telefone de serviço em seu locatário que podem ser usados para rotear chamadas para o serviço de Audioconferência por meio do Roteamento Direto.

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Por exemplo:

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Atribuir os números de telefone de serviço à ponte de Audioconferência da sua organização

Você pode atribuir números de telefone de serviço à ponte de Audioconferência da sua organização usando o cmdlet Register-csOnlineDialInConferencingServiceNumber do PowerShell.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Você pode ver a ID da ponte de audioconferência usando Get-CsOnlineDialInConferencingBridge. Por exemplo:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Etapa 4: Definir uma política de roteamento de voz global para habilitar o roteamento de chamadas de saída de reuniões

O roteamento de chamadas de saída feitas para o PSTN a partir de reuniões organizadas por usuários em sua organização é definido pela política de roteamento de voz global da sua organização. Se sua organização tiver uma política de roteamento de voz global definida, verifique se a política de roteamento de voz global permite as chamadas de saída para o PSTN que devem ser iniciadas a partir de reuniões organizadas por usuários em sua organização. Se sua organização não tiver uma política de roteamento de voz global definida, você precisará definir uma para habilitar o roteamento de chamadas de saída para o PSTN de reuniões organizadas por usuários em sua organização. Observe que a política global de roteamento de voz da sua organização também se aplica a chamadas um-para-um feitas ao PSTN por usuários em sua organização. Se as chamadas um-para-um para o PSTN forem habilitadas para usuários em sua organização, verifique se a política de roteamento de voz global atende às necessidades da sua organização para ambos os tipos de chamadas.

> [!NOTE]
> Location-Based roteamento não está disponível nas implantações do Microsoft 365 Government Community Cloud (GCC) High ou DoD. Ao habilitar a Audioconferência, verifique se nenhum usuário de Audioconferência no GCC High ou nos ambientes do DoD está habilitado para Location-Based Roteamento.

#### <a name="defining-a-global-voice-routing-policy"></a>Definindo uma política de roteamento de voz global

Uma política de roteamento de voz global pode ser definida definindo um uso de PSTN, uma rota de voz, uma política de roteamento de voz e atribuindo a nova política de roteamento de voz como a política de roteamento de voz global da sua organização.

As etapas a seguir descrevem como definir uma nova política de roteamento de voz global para uma organização sem uma. Se sua organização já tiver políticas de roteamento de voz definidas, verifique se a configuração a seguir não está em conflito com as políticas de roteamento de voz existentes da sua organização.

Para criar um novo uso de PSTN em uma sessão remota do PowerShell no Teams, use o seguinte comando:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Para obter informações adicionais, [consulte Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).

Para criar uma nova rota de voz, use o seguinte comando:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Ao definir uma nova rota de voz para sua organização, especifique um ou vários dos gateways PSTN online PSTN que foram definidos para sua organização durante a configuração do Roteamento Direto.

O padrão de número especifica quais chamadas serão roteadas por meio da lista especificada de gateways com base no número de telefone de destino da chamada. No exemplo acima, as chamadas para todos os destinos no mundo corresponderão à rota de voz. Se você quiser restringir os números de telefone que podem ser discados das reuniões de usuários em sua organização, poderá alterar o padrão de número para que a rota de voz corresponda apenas aos padrões numéricos dos destinos permitidos. Observe que, se não houver rotas de voz que correspondam ao padrão de número do número de telefone de destino de uma determinada chamada, a chamada não será roteada.

Para obter informações adicionais, [consulte New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).

Para criar uma nova política de roteamento de voz, use o seguinte comando:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Se vários usos de PSTN estiverem sendo definidos na política de roteamento de voz, eles serão avaliados na ordem em que estão definidos. É recomendável que os usos de PSTN sejam definidos na ordem dos mais específicos para os mais genéricos em termos dos padrões de número das rotas de voz associadas aos usos de PSTN. Por exemplo, se um uso de PSTN foi definido para rotear chamadas para o Estados Unidos e outro uso de PSTN foi definido para rotear chamadas para qualquer outro local no mundo, o uso de PSTN para chamadas para o Estados Unidos deve ser listado na política de roteamento de voz antes do uso de PSTN para rotear chamadas para qualquer outro local no mundo.

Para obter informações adicionais, [consulte New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Para atribuir a nova rota de voz à política de roteamento de voz global da sua organização, use o seguinte comando:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Para obter informações adicionais, [consulte Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Depois que a política de roteamento de voz global for definida, todas as chamadas de saída feitas de reuniões organizadas por usuários em sua organização serão avaliadas em relação às rotas de voz associadas aos usos PSTN da política de roteamento de voz global. As chamadas de saída serão roteadas de acordo com a primeira rota de voz que corresponde ao padrão de número do número de telefone discado.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Etapa 5: Atribuir audioconferência com roteamento direto para licenças GCC High ou DoD aos usuários

Para atribuir audioconferência com roteamento direto para licenças GCC High ou DoD ao usuário, consulte Atribuir [licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Etapa 6: (Opcional) Ver uma lista de números de Audioconferência no Teams

Para ver a lista de números de Audioconferência de sua organização, acesse Ver uma lista de números de [Audioconferência no Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Etapa 7: (Opcional) Definir idiomas de atendedor automático para os números de discagem de Audioconferência de sua organização

Para alterar os idiomas dos números de discagem de Audioconferência de sua organização, consulte Definir idiomas de atendedor automático para [Audioconferência no Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Etapa 8: (Opcional) Alterar as configurações da ponte de Audioconferência da sua organização

Para alterar as configurações da ponte de Audioconferência da sua organização, consulte [Alterar as configurações de uma ponte de Audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Etapa 9: (Opcional) Definir os números de telefone incluídos nos convites da reunião dos usuários em sua organização

Para alterar o conjunto de números de telefone incluídos nos convites de reunião dos usuários, consulte Definir os números de telefone [incluídos nos convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Recursos de audioconferência sem suporte na Audioconferência com Roteamento Direto para GCC High e DoD

A seguir estão os recursos de Audioconferência que não têm suporte na Audioconferência com Roteamento Direto para GCC High e DoD:

- Notificações de entrada e saída usando a gravação de nome. Para Audioconferência com Roteamento Direto, as notificações de entrada e saída são tocadas na reunião como tons.

- Desabilite o uso de números de chamada gratuita para o organizador específico das reuniões. Controles de nível de usuário para restringir o uso de números de chamada gratuita para ingressar nas reuniões da sua organização não são aplicáveis a chamadas roteadas por meio do Roteamento Direto.

- Enviar emails de notificação aos usuários quando suas configurações mudarem. Os emails de notificação de audioconferência não têm suporte para Audioconferência com Roteamento Direto para GCC High e DoD.
