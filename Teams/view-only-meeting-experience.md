---
title: Experiência de reunião somente exibição
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre a experiência de reunião somente para exibição do Teams para administradores, apresentadores e participantes
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875051"
---
# <a name="teams-view-only-meeting-experience"></a>Experiência de reunião somente para exibição do Teams

> [!Note]
> As transmissões somente para exibição estão disponíveis no Microsoft 365 E3/E5 e no Microsoft 365 A3/A5. Esse recurso será habilitado em 1º de março de 2021 como off padrão. O recurso no Microsoft 365 Government Community Cloud (GCC) começará a ser apresentado no final de março de 2021. O Government Community Cloud High (GCCH) e o Departamento de Defesa (DoD) serão divulgados posteriormente. Você deve alterar a política padrão após essa data se quiser que o recurso seja on padrão. Use o PowerShell para habilitar a política `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` .

> [!Note]
> Se sua reunião ou webinar atingir a capacidade, o Teams será dimensionado perfeitamente para acomodar uma experiência de transmissão somente para exibição de 10.000 pessoas. Além disso, durante esse período de maior trabalho remoto, aproveite as transmissões ainda maiores de 20.000 pessoas até o final deste ano.

O Microsoft Teams permite que até 10.000 participantes participem de uma reunião do Teams. Depois que a capacidade da reunião principal tiver sido atingida, participantes adicionais ingressarão com uma experiência somente para exibição.

Os participantes que ingressarem na reunião primeiro, até a capacidade da reunião, terão a experiência de reunião completa do Teams. Eles podem compartilhar áudio e vídeo, ver vídeos compartilhados e participar do chat de reunião.

Os participantes que ingressarem depois que a capacidade de reunião principal tiver sido atingida terão uma experiência somente para exibição.

Temos suporte completo para android e iOS para um participante participar.

> [!Note]
> O limite atual para o número de pessoas que podem conversar e ligar para uma reunião é 300 na WW e 250 no GCC, GCC High e DoD.

A experiência somente para exibição é desabilitada por padrão para qualquer organizador que tenha SKU E3/E5/A3/A5. Nenhuma configuração ou configuração posterior é necessária.

## <a name="disable-teams-view-only-experience"></a>Desabilitar a experiência somente para exibição do Teams

Os administradores podem desabilitar a experiência somente para exibição usando o PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

No futuro, também será possível que os administradores desabilitem a experiência somente para exibição no centro de administração do Teams.

## <a name="impact-to-users"></a>Impacto para os usuários

A experiência de um usuário variará dependendo de vários fatores.

Quando a capacidade da reunião principal for atingida, um participante não poderá participar da reunião se qualquer um dos seguintes eventos for verdadeiro:

- Um administrador desabilitou a experiência somente de exibição do Teams.
- O participante não tem permissão para ignorar o lobby.

Quando a capacidade da reunião principal for atingida, o organizador da reunião e os apresentadores verão uma faixa informando que a capacidade de reunião foi atingida e que os novos participantes ingressarão em um participante somente para exibição.

  ![a mensagem de cliente e faixa do Teams para organizadores e apresentadores](media/chat-and-banner-message.png)

Quando a capacidade da reunião principal for atingida, os participantes da reunião serão informados na tela de pré-entrada de que eles estão in joining no modo somente exibição.

  ![a tela de pré-participação do Teams e a mensagem para os participantes dizendo que eles ingressarão no modo somente exibição](media/view-only-pre-join-screen.png)

Se houver espaço, um usuário sempre ingressará na reunião principal. Se a reunião principal atingir a capacidade e um ou mais participantes saírem da reunião principal, a reunião principal terá capacidade disponível. Os participantes que ingressarem (ou ingressarem) na reunião participarão da reunião principal até que ela atinja a capacidade novamente. Os participantes que estão na experiência somente exibição não serão promovidos automaticamente para a reunião principal e não poderão ser promovidos manualmente para a reunião principal.

Se as funções de apresentador/participante não foram definidas, os espaços na reunião principal serão preenchidos por primeira vez. Depois que a capacidade de reunião tiver sido atingida, todos os outros usuários ingressarão com uma experiência somente de exibição.

## <a name="impact-to-meeting-presenters"></a>Impacto para apresentadores de reunião

As limitações para apresentadores de reunião incluem:

- Você não terá informações sobre o participante somente para exibição. Não há suporte à descoberta de E para participantes somente de exibição.
- Os usuários não podem ver os participantes somente para exibição.
- Não é possível remover um participante somente para exibição da reunião.

> [!Note]
> A contagem de participantes refletirá apenas as pessoas na reunião e não as pessoas na sala somente para exibição. Portanto, os apresentadores não podem obter uma contagem exata de quem está na experiência somente de exibição.

## <a name="experience-for-view-only-attendees"></a>Experiência para participantes somente exibição

A experiência somente de exibição do Teams permite que os participantes:

- Ouça os participantes da reunião principal do Teams.
- Consulte o feed de vídeo do alto-falante ativo (se o alto-falante ativo estiver compartilhando vídeo).
- Consulte o conteúdo que está sendo compartilhado usando a funcionalidade da área de trabalho de compartilhamento.

O participante somente para exibição não poderá experimentar as seguintes opções em reuniões:

- Participe da reunião se o participante não tiver permissão para ignorar o lobby com base em políticas ou opções de lobby definidas.
- Participe da sala somente exibição usando Audioconferência.
- Participe da sala somente exibição usando o sistema da Sala do Microsoft Teams ou usando serviços CVI (Cloud Video Interop).
- Compartilhe seu áudio ou vídeo.
- Consulte ou participe do chat da reunião.
- Consulte o feed de vídeo dos participantes da reunião, a menos que o participante seja o orador ativo.
- Consulte Arquivos do PowerPoint compartilhados usando a funcionalidade nativa do PowerPoint ou compartilhamentos de aplicativos individuais (diferente do compartilhamento de área de trabalho).

## <a name="view-only-feature-limitations"></a>Limitações de recursos somente exibição

- Os participantes somente exibição sempre verão legendas ao vivo, independentemente da configuração de legendas ao vivo para essa reunião. Somente legendas em inglês são suportadas no momento.
- Os participantes somente para exibição terão suporte da tecnologia de streaming.
- Os participantes somente exibição não serão incluídos no relatório de presença.
- Os participantes somente para exibição terão uma única experiência em vídeo. Eles podem ver o alto-falante ativo ou o conteúdo sendo compartilhado, mas não ambos.
- No momento, não há suporte a  Layouts de modo **Galeria,** **Galeria** Grande ou Modo Juntos para participantes somente para exibição.  
- Os participantes somente exibição não terão a mesma latência que um participante regular. <sup>1</sup>

  <sup>1</sup> Os participantes somente exibição estarão com um atraso de vídeo e áudio de 30 segundos na reunião.  
