---
title: Gerenciar políticas de reunião para áudio e vídeo
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- seo-marvel-apr2020
description: Aprenda a gerenciar configurações de política de reunião em Teams para áudio e vídeo.
ms.openlocfilehash: 4f8de802fd2ddf90555a34ac0b8d66d2d7021f79
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726560"
---
# <a name="meeting-policy-settings-for-audio--video"></a>Configurações de política de reunião para vídeo & áudio

<a name="bkaudioandvideo"> </a>
<a name="ndi"> </a>

Este artigo descreve as configurações de política de reunião específicas para áudio e vídeo. Eles incluem o seguinte:

- [Permitir transcrição](#allow-transcription)
- [Permitir gravação em nuvem](#allow-cloud-recording)
- [Modo de áudio IP](#mode-for-ip-audio)
- [Modo de vídeo IP](#mode-for-ip-video)
- [Permitir vídeo IP](#allow-ip-video)
- [Taxa de bits de mídia (Kbs)](#media-bit-rate-kbs)
- [Modo de filtros de vídeo](#video-filters-mode)
- [Permitir configurações de plano de fundo personalizadas](#allow-custom-background-settings)

### <a name="allow-transcription"></a>Permitir transcrição

Esta é uma combinação de uma política por usuário e por organizador. Essa configuração controla se as legendas e os recursos de transcrição estão disponíveis durante a reprodução das gravações de reunião. Se você desativar essa opção, as opções **Pesquisar** e **CC** não estarão disponíveis durante a reprodução de uma gravação de reunião. A pessoa que iniciou a gravação precisa dessa configuração ativada para que a gravação também inclua a transcrição.

Observe que, no momento, só há suporte para transcrição para reuniões gravadas para usuários que têm o idioma do Teams definido para o português e quando se fala português na reunião.

### <a name="allow-cloud-recording"></a>Permitir gravação na nuvem

Esta é uma combinação de uma política por usuário e por organizador. Essa configuração controla se as reuniões desse usuário podem ser gravadas. A gravação poderá ser iniciada pelo organizador da reunião ou por outro participante se a configuração de política estiver ativada para o participante e se for um usuário autenticado da mesma organização.

Pessoas de fora da sua organização, como usuários federados e anônimos, não conseguem iniciar a gravação. Os usuários convidados não podem iniciar ou interromper a gravação.

![Captura de tela mostrando opções de gravação.](media/meeting-policies-recording.png)

Observe o exemplo a seguir.

|Usuário |Políticas de reunião  |Permitir gravação na nuvem |
|---------|---------|---------|
|Daniela | Global   | Desabilitado |
|Amanda | Location1MeetingPolicy | Habilitado|
|João (usuário externo) | Não aplicável | Não aplicável|

As reuniões organizadas por Daniela não podem ser gravadas e Amanda, que tem a configuração de política habilitada, não pode gravar reuniões organizadas por Daniela. As reuniões organizadas por Amanda podem ser registradas, no entanto, Daniela, que tem a configuração de política desabilitada e João que é um usuário externo, não podem gravar reuniões organizadas por Amanda.

Para saber mais sobre a gravação de reunião na nuvem, confira [Gravação de reunião na nuvem do Teams](cloud-recording.md).

### <a name="mode-for-ip-audio"></a>Modo de áudio IP

Esta é uma política por usuário. Essa configuração controla se o áudio pode ser habilitado em reuniões e chamadas em grupo. Esses são os valores dessa configuração.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Áudio de saída e entrada habilitado**    |O vídeo de saída e entrada, que é permitido na reunião, é a configuração padrão. |
|**Desabilitado**     |O áudio de entrada e saída não é permitido na reunião.     |

Se definido como **Desabilitada** para um usuário, esse usuário ainda poderá agendar e organizar reuniões, mas não poderá usar o áudio. Para participar de uma reunião, eles devem discar por meio da PSTN (Rede Telefônica Pública Comutada) ou fazer com que a reunião seja chamada e ingressar por telefone. Os participantes da reunião que não têm políticas atribuídas (por exemplo, participantes anônimos) têm essa configuração para **Áudio de saída e de entrada habilitado** por padrão. Em clientes móveis do Teams, se essa configuração estiver desabilitada, o usuário precisará discar para a reunião por meio da PSTN.

Essa configuração não se aplica à chamadas 1:1. Para restringir chamadas 1:1, configure uma [política de chamada](teams-calling-policy.md) e desabilite a configuração **Fazer chamadas privadas**. Essa configuração também não se aplica aos dispositivos da sala de conferência, como dispositivos de Surface Hub e Salas do Microsoft Teams. 

Essa configuração ainda não está disponível para ambientes de Nuvem da Comunidade Governamental (GCC) da Microsoft 365, GCC Altos ou para o Departamento de Defesa (DoD).

Para saber mais, confira [Gerenciar áudio/vídeo para participantes da reunião](#manage-audiovideo-for-meeting-participants).

### <a name="mode-for-ip-video"></a>Modo de vídeo IP

Essa é uma política por usuário. Essa configuração controla se o vídeo pode ser habilitado em reuniões e chamadas em grupo. Esses são os valores dessa configuração.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Vídeo de saída e entrada habilitado**    | O vídeo de entrada e saída é permitido na reunião. Essa é a configuração padrão. |
|**Desabilitado**     | O vídeo de entrada e saída não é permitido na reunião. Em clientes móveis do Teams, os usuários não podem compartilhar vídeos ou fotos na reunião. <br><br>Observe que, se o **Modo de áudio IP** estiver desabilitado, o **Modo de vídeo IP** também permanecerá desabilitado.  |

Se definido como **Desabilitado** para um usuário, esse usuário não poderá ativar o vídeo ou exibir vídeos compartilhados por outros participantes da reunião. Os participantes da reunião que não têm políticas atribuídas (por exemplo, participantes anônimos) têm essa configuração para **Vídeo de saída e de entrada habilitado** por padrão.

Essa configuração não se aplica aos dispositivos da sala de conferência, como dispositivos de Surface Hub e Salas do Microsoft Teams. 

Essa configuração ainda não está disponível para ambientes de Nuvem da Comunidade Governamental (GCC) da Microsoft 365, GCC Altos ou para o Departamento de Defesa (DoD).

> [!NOTE]
> Lembre-se de que essa configuração controla o vídeo de saída e de entrada, enquanto a configuração **Permitir vídeo IP** controla o vídeo de saída. Para saber mais, confira [Qual configuração de política de vídeo IP tem prioridade?](#which-ip-video-policy-setting-takes-precedence) e [Gerenciar áudio/vídeo para os participantes da reunião](#manage-audiovideo-for-meeting-participants).

Para saber mais, confira [Gerenciar áudio/vídeo para participantes da reunião](#manage-audiovideo-for-meeting-participants).

### <a name="allow-ip-video"></a>Permitir vídeo IP

Esta é uma combinação de uma política por usuário e por organizador. O vídeo é um componente fundamental para reuniões. Em algumas organizações, os administradores podem querer ter mais controle sobre quais reuniões têm vídeo. Essa configuração controla se o vídeo pode ser habilitado em reuniões hospedadas por um usuário e em chamadas 1:1 e de grupo iniciadas por um usuário. Em Teams clientes móveis, essa configuração controla se os usuários podem compartilhar fotos e vídeos em uma reunião.

As reuniões organizadas por um usuário que possui essa configuração de política habilitada permitem o compartilhamento de vídeo na reunião pelos participantes da reunião, caso os participantes também tenham a configuração de política habilitada. Os participantes da reunião que não possuem políticas atribuídas (por exemplo, participantes anônimos e federados) herdam a política do organizador da reunião.

> [!NOTE]
> Lembre-se de que essa configuração controla o vídeo de saída, enquanto a configuração **Modo de vídeo IP** controla o vídeo de entrada e saída. Para saber mais, confira [Qual configuração de política de vídeo IP tem prioridade?](#which-ip-video-policy-setting-takes-precedence) e [Gerenciar áudio/vídeo para os participantes da reunião](#manage-audiovideo-for-meeting-participants).

| Cliente Teams da Web e da área de trabalho |Cliente de dispositivo móvel do Teams  |
|:-------:|:-------:|
|![Captura de tela mostrando a junção de reunião com configurações de áudio/vídeo na área de trabalho.](media/meeting-policies-audio-video-settings.png)    |![Captura de tela mostrando a tela de ingresso à reunião com as configurações de áudio/vídeo no dispositivo móvel](media/meeting-policies-mobile-join.png)          |

Observe o exemplo a seguir.

|Usuário |Políticas de reunião  |Permitir vídeo IP |
|---------|---------|---------|
|Daniela   | Global   | Habilitado       |
|Amanda    | Location1MeetingPolicy        | Desabilitado      |

Reuniões hospedadas pela Daniela permitem que o vídeo seja habilitado. A Daniela pode entrar na reunião e ativar o vídeo. A Amanda não pode ativar o vídeo na reunião da Daniela porque a política da Amanda está definida para não permitir o vídeo. A Amanda pode ver os vídeos compartilhados por outros participantes da reunião.

Nas reuniões hospedadas por Amanda, ninguém poderá ativar o vídeo, independentemente da política de vídeo atribuída a eles. Isso significa que a Daniela não pode ativar o vídeo nas reuniões da Amanda.  

Se Daniela liga para a Amanda com o vídeo habilitado, a Amanda poderá atender à chamada somente com o áudio.  Quando a chamada estiver conectada, a Amanda poderá ver o vídeo da Daniela, mas não poderá ativar o vídeo. Se a Amanda liga para a Daniela, Daniela poderá atender à chamada com vídeo e áudio. Quando a chamada estiver conectada, a Daniela poderá ativar ou desativar o vídeo, se necessário.

Para saber mais, confira [Gerenciar áudio/vídeo para participantes da reunião](#manage-audiovideo-for-meeting-participants).

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>Qual configuração de política de vídeo IP tem precedência?

Para um usuário, a configuração de política mais restritiva para o vídeo tem prioridade. Veja alguns exemplos.

|Permitir vídeo IP|Modo de vídeo IP|Experiência de compartilhamento|
|---------|---------|---------|
|Organizador: **Habilitado**<br><br>Participante: **Habilitado** |Participante: **Desabilitado**        |A configuração **Modo para vídeo IP** tem prioridade. O participante atribuído a essa política não poderá ativar nem exibir vídeos compartilhados por outras pessoas.|
|Organizador: **Habilitado**<br><br>Participante: **Habilitado** |Participante: **Vídeo de saída e de entrada habilitado**          |O participante atribuído a essa política poderá ativar e exibir vídeos compartilhados por outras pessoas.         |
|Organizador: **Habilitado**<br><br>Participante: **Desabilitado** |Participante: **Vídeo de saída e de entrada habilitado**         |A configuração **Permitir modo de vídeo IP** tem prioridade. Os participantes só poderão ver os vídeos recebidos e não poderão enviar vídeo de saída.         |
|Organizador: **Habilitado**<br><br>Participante: **Desabilitado** |Participante: **Desabilitado**         |A configuração **Modo de vídeo IP** tem prioridade. O participante não consegue ver o vídeo de entrada ou de saída.|
|Organizador: **Desabilitado**    |       |A configuração **Permitir vídeo IP** tem prioridade porque está desativada para o organizador. Ninguém pode ativar o vídeo em reuniões organizadas pelo usuário que recebeu essa política.         |

### <a name="manage-audiovideo-for-meeting-participants"></a>Gerenciar áudio/vídeo para participantes da reunião

|Se desejar...  |Definir as seguintes configurações de política  |
|---------|---------|
|Desabilitar áudio e vídeo para os participantes das reuniões  |Modo de áudio IP: **Desabilitado**<br> Modo de vídeo IP: **Desabilitado**<br>Permitir vídeo IP: N/A       |
|Habilitar apenas vídeo e áudio de entrada para os participantes nas reuniões  |Modo de áudio IP: **Áudio de entrada e saída habilitado**<br> Modo de vídeo IP: **Vídeo de entrada e saída habilitado**<br>Permitir vídeo IP: **Desativado**       |
|Desabilitar o vídeo para os participantes nas reuniões (os participantes só têm áudio)|  Modo de áudio IP: **Habilitar o áudio de entrada e saída**<br> Modo de vídeo IP: **Desabilitado**<br>Permitir vídeo IP: N/A
|Habilitar áudio e vídeo para os participantes das reuniões    |Modo de áudio IP: **Áudio de entrada e saída habilitado** (padrão)<br> Modo de vídeo IP: **Vídeo de entrada e saída habilitado** (padrão)<br>Permitir vídeo IP: **Habilitado** (padrão)    |

A política mais restritiva entre a política do organizador da reunião e a política do usuário será aplicada. Por exemplo, se um organizador tiver uma política que restringe vídeo e a política de um usuário não restringe vídeo, os participantes da reunião herdam a política do organizador da reunião e não têm acesso ao vídeo em reuniões. Isso significa que eles podem ingressar à reunião apenas com o áudio.

> [!NOTE]
> Quando um usuário iniciar uma chamada de grupo para entrar por telefone, a tela **Usar telefone para áudio** não será exibida. Esse é um problema conhecido que estamos trabalhando para resolver. Para evitar esse problema, selecione **Áudio do telefone** em **Outras opções de ingresso**.  

#### <a name="teams-mobile-clients"></a>Cliente de dispositivo móvel do Teams

Para os usuários do Teams em dispositivo móvel, a capacidade de compartilhar fotos e vídeos durante uma reunião também é determinada pela configuração **Permitir vídeo IP** ou **Modo de vídeo de IP**. Dependendo da configuração da política, a capacidade de compartilhar vídeos e fotos não estará disponível. Isso não afeta o compartilhamento de tela, que você configura usando um modo separado de [Compartilhamento de tela](meeting-policies-content-sharing.md#screen-sharing-mode). Além disso, você pode definir uma [Política de mobilidade do Teams](/powershell/module/skype/new-csteamsmobilitypolicy) para impedir que os usuários móveis usem o vídeo por meio de uma conexão de rede celular, o que significa que devem usar uma conexão WiFi.

### <a name="media-bit-rate-kbs"></a>Taxa de bits de mídia (Kbs)

Essa é uma política por usuário. Essa configuração determina a taxa de bits de mídia para as transmissões de compartilhamento de áudio, vídeo e aplicativos baseados em vídeo em chamadas e reuniões do usuário. Ela é aplicada à travessia da mídia de uplink e de downlink para os usuários da chamada ou da reunião. Essa configuração oferece controle meticuloso sobre o gerenciamento de largura de banda na sua organização. Dependendo dos cenários de reuniões necessários para os usuários, recomendamos o uso de largura de banda suficiente para ter uma boa experiência de qualidade. O valor mínimo é de 30 kbps e o valor máximo depende do cenário da reunião. Para saber mais sobre a largura de banda mínima recomendável para reuniões em boas-qualidade, chamadas e eventos ao vivo no Teams, confira [Requisitos de largura de banda](prepare-network.md#bandwidth-requirements).

Se não houver largura de banda suficiente para uma reunião, os participantes verão uma mensagem que indica uma qualidade de rede ruim.

Para reuniões que precisem da experiência de qualidade de vídeo mais alta, como as reuniões da diretoria e eventos ao vivo do Teams, recomendamos que você defina a largura de banda como 10 Mbps. Mesmo quando a experiência máxima é definida, a pilha das mídias da do Teams se adapta às condições de baixa largura de banda quando determinadas condições de rede são detectadas, dependendo do cenário.

## <a name="video-filters-mode"></a>Modo de filtros de vídeo

<a name="bkvideofilters"> </a>

Essa é uma política por usuário. Essa configuração controla se os usuários podem personalizar o plano de fundo do vídeo em uma reunião.

No momento, você só pode usar o PowerShell para definir essa política. Você pode editar uma política de reunião do Teams existente usando o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). Ou crie uma nova política de reunião do Teams usando o cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e atribua essa política aos usuários.

Para especificar se os usuários podem personalizar o plano de fundo do vídeo em uma reunião, defina o parâmetro **VideoFiltersMode** da seguinte maneira:

|Valor de configuração no PowerShell |Comportamento  |
|---------|---------|
|**NoFilters**     |O usuário não pode personalizar o plano de fundo do vídeo.|
|**BlurOnly**     |O usuário tem a opção de borrar o plano de fundo do vídeo. |
|**BlurandDefaultBackgrounds**     |O usuário tem a opção de borrar o plano de fundo do vídeo ou escolher entre o conjunto padrão de imagens a ser usado como plano de fundo. |
|**AllFilters**     |O usuário tem a opção de borrar o plano de fundo do vídeo, escolher entre o conjunto padrão de imagens, ou fazer o upload de imagens personalizadas a serem usadas como plano de fundo. |

> [!NOTE]
> As imagens carregadas pelos usuários não são filtradas pelo Teams. Quando você usa a configuração **AllFilters**, você deve ter políticas internas da organização para impedir que os usuários façam o upload de imagens ofensivas ou inadequadas, ou imagens que sua organização não tem direitos de uso para os planos de fundo de reunião do Teams.

### <a name="allow-custom-background-settings"></a>Permitir configurações de plano de fundo personalizadas

Você pode adicionar imagens de plano de fundo personalizadas a serem usadas por locatário. Esse recurso permite que as empresas apliquem a identidade visual corporativa a Teams reuniões.

1. Entre no Centro de administração do Teams.

2. Selecione **Políticas de Reunião** Personalizar imagens de  >  **reunião**.

   ![A seleção de políticas de reunião com o botão Personalizar imagens de reunião realçada.](media/custom-background-image-button.png)

3. Selecione **Em em** Imagens de plano de fundo de toda a **organização.**

4. Selecione **+ Adicionar imagens**.

5. No painel Gerenciando plano de fundo, selecione **Adicionar imagem**.

6. Verifique se as imagens atendem a esses requisitos:
  
   - Tamanho mínimo 360 px
   - Tamanho máximo 2048 px
   - Tipo de arquivo de PNG, JPG ou BMP
   - Máximo de 50 imagens podem ser carregadas

7. Visualize as imagens selecionadas e selecione **Fechar**.

8. Revise as imagens e adicione mais conforme necessário.

9. Selecione **Salvar**.

Os participantes da reunião verão uma seleção de imagens em segundo plano que podem ser usadas ao participar de uma reunião.

> [!NOTE]
> Pode levar até 24 horas para que as alterações entre em vigor.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md)
