---
title: Gerenciar políticas de reunião para compartilhamento de conteúdo
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
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Saiba como gerenciar as configurações de política de reunião no Teams para compartilhamento de conteúdo.
ms.openlocfilehash: c2baa0328cd1ff0271d2b1ecbf8e1fab76f24846
ms.sourcegitcommit: 0592f9d2696fe8c840a4ed3e7f99e55ca0c9c3e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "67418610"
---
# <a name="meeting-policy-settings---content-sharing"></a>Configurações de política de reunião - Compartilhamento de conteúdo

<a name="bkcontentsharing"> </a>

Este artigo descreve as seguintes configurações de política de reunião relacionadas ao compartilhamento de conteúdo:

- [Modo de compartilhamento de tela](#screen-sharing-mode)
- [Permitir que um participante conceda ou solicite o controle](#allow-a-participant-to-give-or-request-control)
- [Os participantes externos podem dar ou solicitar controle](#external-participants-can-give-or-request-control)
- [PowerPoint Live](#powerpoint-live)
- [Quadro de comunicações](#whiteboard)
- [Anotações compartilhadas](#shared-notes)

## <a name="screen-sharing-mode"></a>Modo de compartilhamento de tela

Essa configuração é uma combinação de políticas por organizador e por usuário. Essa configuração controla se o compartilhamento de área de trabalho e janela é permitido na reunião do usuário. Os participantes da reunião que não têm nenhuma política atribuída (por exemplo, participantes externos) herdam a política do organizador da reunião.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Tela inteira**    | Compartilhamento completo de área de trabalho e compartilhamento de aplicativos são permitidos na reunião |
|**Único aplicativo**   | O compartilhamento de aplicativos é permitido na reunião        |
|**Desabilitado**     |Compartilhamento de tela e compartilhamento de aplicativos desativados na reunião.       |

Observe o exemplo a seguir.

|Usuário |Políticas de reunião |Modo de compartilhamento de tela |
|---------|---------|---------|
|Daniela  | Global   | Tela inteira |
|Amanda   | Location1MeetingPolicy  | Desabilitado |

As reuniões hospedadas pela Daniela permitem que os participantes da reunião compartilhem toda a tela ou um aplicativo específico. Se a Amanda ingressar na reunião da Daniela, a Amanda não poderá compartilhar sua tela ou um determinado aplicativo, pois a configuração de política está desabilitada. Nas reuniões hospedadas por Amanda, ninguém tem permissão para compartilhar a tela ou um único aplicativo, independentemente da política de modo de compartilhamento de tela atribuída a eles.  Consequentemente, Daniela não pode compartilhar sua tela ou um único aplicativo nas reuniões de Amanda.  

No momento, os usuários não podem reproduzir vídeo ou compartilhar a tela em uma reunião do Teams se estiverem usando o Google Chrome.

## <a name="allow-a-participant-to-give-or-request-control"></a>Permitir que um participante conceda ou solicite o controle

Essa configuração é uma política por usuário. Essa configuração controla se o usuário pode conceder o controle da área de trabalho ou da janela para outros participantes da reunião. Para dar controle, passe o mouse sobre a parte superior da tela.

Se essa configuração estiver ativada para o usuário, a opção **Atribuir controle** será exibida na barra superior de uma sessão de compartilhamento.

![Captura de tela mostrando a opção Conceder controle.](media/meeting-policies-give-control.png)

Se as configurações estiverem desativadas para o usuário, a opção **Conceder controle** não estará disponível.

![Captura de tela mostrando que a opção Conceder controle não está disponível.](media/meeting-policies-give-control-not-available.png)

Observe o exemplo a seguir.

|Usuário |Políticas de reunião  |Permitir que o participante conceda ou solicite o controle |
|---------|---------|---------|
|Daniela   | Global   | Habilitado       |
|Babek    | Location1MeetingPolicy        | Desabilitado   |

Daniela pode dar controle da área de trabalho ou janela compartilhada a outros participantes em uma reunião organizada pelo Babek. No entanto, Babek não pode dar controle a outros participantes.

Para usar o PowerShell para controlar quem pode conceder controle ou aceitar solicitações de controle, use o cmdlet AllowParticipantGiveRequestControl.

> [!NOTE]
> Para conceder e assumir o controle do conteúdo compartilhado durante o compartilhamento, as duas partes devem usar o cliente da área de trabalho do Teams. Não há suporte para controle quando ambas as partes estiverem executando o Teams em um navegador. Isso ocorre devido a uma limitação técnica de que estamos planejando corrigir.

## <a name="external-participants-can-give-or-request-control"></a>Os participantes externos podem dar ou solicitar controle

Essa configuração é uma política por usuário. Se uma organização definiu essa política para um usuário não controla o que os participantes externos podem fazer, independentemente do que o organizador da reunião definiu. Esse parâmetro controla se os participantes externos podem receber ou solicitar controle da tela de compartilhamento do participante, dependendo do que o participante do compartilhamento definiu dentro das políticas da sua organização. Os participantes externos nas reuniões das Teams podem ser categorizados da seguinte maneira:  

- Participante anônimo
- Convidados
- Usuários de acesso externo

Se os usuários de acesso externo podem dar controle a outros participantes externos enquanto o compartilhamento é controlado pelos participantes **externos** podem fornecer ou solicitar a configuração de controle em sua organização.

Para usar o PowerShell para controlar se os participantes externos podem conceder controle ou aceitar solicitações de controle, use o cmdlet AllowExternalParticipantGiveRequestControl.

### <a name="powerpoint-live"></a>PowerPoint Live

Essa é uma política por usuário. Essa configuração controla se o usuário pode compartilhar os decks de slides do PowerPoint em uma reunião. Os participantes externos, incluindo usuários anônimos, convidados e de acesso externo, herdam a política do organizador da reunião.

Observe o exemplo a seguir.

|Usuário |Políticas de reunião  |PowerPoint Live |
|---------|---------|---------|
|Daniela   | Global   | Habilitado       |
|Amanda   | Location1MeetingPolicy        | Desabilitado   |

Amanda não pode compartilhar os conjunto de slides do PowerPoint nas reuniões, mesmo que ela seja a organizadora da reunião. Daniela pode compartilhar os conjunto de slides do PowerPoint mesmo se a reunião for organizada pela Amanda. Amanda pode exibir os conjunto de slides do PowerPoint compartilhados por outras pessoas na reunião, apesar de não poder compartilhar os conjunto de slides do PowerPoint.

## <a name="whiteboard"></a>Quadro de comunicações

Essa configuração é uma política por usuário. Essa configuração controla se um usuário pode compartilhar o quadro de comunicações em uma reunião. Os participantes externos, incluindo usuários anônimos, convidados e de acesso externo, herdam a política do organizador da reunião.

Observe o exemplo a seguir.

|Usuário |Políticas de reunião  |Quadro de comunicações|
|---------|---------|---------|
|Daniela   | Global   | Habilitado       |
|Amanda   | Location1MeetingPolicy        | Desabilitado   |

Amanda não pode compartilhar o quadro de comunicações em uma reunião, mesmo que ela seja a organizadora da reunião. Daniela pode compartilhar o quadro de comunicações mesmo se uma reunião for organizada por Amanda.

Para habilitar o Whiteboard usando o PowerShell, defina o cmdlet IsWBFluidEnabled como $true [do Set-SPOTenant.](/powershell/module/sharepoint-online/set-spotenant)

### <a name="annotation"></a>Anotação

Quando o quadro de comunicações estiver habilitado, os usuários terão a opção de usar a anotação [, um](/office/use-annotation-while-sharing-your-screen-in-teams) recurso que permite que os participantes colaborem enquanto compartilham sua tela em uma reunião do Teams. Se o quadro de comunicações estiver desabilitado, os usuários não terão acesso à anotação.

## <a name="shared-notes"></a>Anotações compartilhadas

Essa configuração é uma política por usuário. Essa configuração controla se um usuário pode criar e compartilhar anotações em uma reunião. Os participantes externos, incluindo anônimos, convidados e acesso externo, herdam a política do organizador da reunião. No momento, só há suporte para a guia **Anotações de reunião** com reuniões com menos de 20 participantes.

Observe o exemplo a seguir.

|Usuário |Políticas de reunião  |Anotações compartilhadas |
|---------|---------|---------|
|Daniela   | Global   | Habilitado       |
|Amanda   | Location1MeetingPolicy | Desabilitado |

Daniela pode fazer anotações nas reuniões da Amanda e a Amanda não pode fazer anotações em qualquer reunião.




## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)
- [Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários](meeting-policies-restricted-anonymous-access.md)
