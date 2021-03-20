---
title: Experiência de reunião somente para visualização
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre a experiência de reunião somente visualização do Teams para administradores, apresentadores e participantes
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875051"
---
# <a name="teams-view-only-meeting-experience"></a>Experiência de reunião somente para visualização de Teams

> [!Note]
> As transmissões somente para visualização estão disponíveis no Microsoft 365 E3/E5 e Microsoft 365 A3/A5. Este recurso será habilitado em 1º de março de 2021 como DESLIGADO padrão. O recurso no Microsoft 365 Government Community Cloud (GCC) começará a ser implementado no final de março de 2021. Government Community Cloud High (GCCH) e Department of Defense (DoD) serão implementados posteriormente. Você deve alterar a política padrão após essa data se quiser que o recurso seja ativado por padrão. Use o Windows PowerShell para habilitar a política `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.

> [!Note]
> Se a sua reunião ou webinar atingir a capacidade máxima, o Teams será perfeitamente escalado para acomodar uma experiência de transmissão somente visualização para 10.000 pessoas. Além disso, durante este período de maior trabalho remoto, aproveite as transmissões ainda maiores para 20.000 pessoas até o final deste ano.

O Microsoft Teams permite que até 10.000 participantes participem de uma reunião do Teams. Depois que a capacidade da reunião principal for atingida, os participantes adicionais entrarão em uma experiência somente de visualização.

Os participantes que ingressarem primeiro na reunião, até a capacidade máxima da reunião, terão a experiência completa de reunião do Teams. Eles podem compartilhar áudio e vídeo, ver vídeos compartilhados e participar do bate-papo da reunião.

Os participantes que ingressarem depois que a capacidade da reunião principal for atingida terão uma experiência somente para visualização.

Temos suporte móvel completo para Android e iOS para a adesão de um participante.

> [!Note]
> O limite atual para o número de pessoas que podem bater papo e ligar para uma reunião é 300 na WW e 250 no GCC, GCC High e DoD.

A experiência somente visualização é desabilitada por padrão para qualquer organizador que tenha E3/E5/A3/A5 SKU. Nenhuma configuração ou instalação adicional é necessária.

## <a name="disable-teams-view-only-experience"></a>Desativar experiência somente para visualização do Teams

Os administradores podem desabilitar a experiência somente visualização usando o Windows PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

No futuro, os administradores também poderão desativar a experiência somente visualização no centro de administração do Teams.

## <a name="impact-to-users"></a>Impacto nos usuários

A experiência de um usuário varia de acordo com vários fatores.

Quando a capacidade da reunião principal for atingida, um participante não poderá participar da reunião se alguma das seguintes condições for verdadeira:

- Um administrador desativou a experiência somente visualização do Teams.
- O participante não tem permissão para ignorar o saguão.

Quando a capacidade da reunião principal for atingida, o organizador da reunião e os apresentadores verão um banner informando que a capacidade da reunião foi atingida e que os novos participantes ingressarão em um participante somente para visualização.

  ![o cliente do Teams e a mensagem do banner para organizadores e apresentadores](media/chat-and-banner-message.png)

Quando a capacidade da reunião principal for atingida, os participantes da reunião serão informados na tela de pré-entrada que eles estão entrando no modo somente visualização.

  ![a tela de pré-adesão das equipes e a mensagem para os participantes informando que eles entrarão no modo somente visualização](media/view-only-pre-join-screen.png)

Se houver espaço, um usuário sempre participará da reunião principal. Se a reunião principal atingir a capacidade máxima e um ou mais participantes deixarem a reunião principal, a reunião principal terá capacidade disponível. Os participantes que ingressarem (ou reingressarem) na reunião entrarão na reunião principal até que ela atinja sua capacidade novamente. Os participantes que estão na experiência somente visualização não serão promovidos automaticamente para a reunião principal e não podem ser promovidos manualmente para a reunião principal no momento.

Se as funções de apresentador / participante não tiverem sido definidas, os espaços na reunião principal serão preenchidos por ordem de chegada. Assim que a capacidade de reunião for atingida, todos os outros usuários ingressarão com uma experiência somente visualização.

## <a name="impact-to-meeting-presenters"></a>Impacto para os apresentadores da reunião

As limitações para apresentadores de reuniões incluem:

- Você não terá informações sobre o participante somente visualização. Não oferecemos suporte ao E-discovery para participantes somente para visualização.
- Os usuários não podem ver os participantes somente para visualização.
- Você não pode remover um participante somente visualização da reunião.

> [!Note]
> A contagem de participantes refletirá apenas as pessoas na reunião e não as pessoas na sala somente para visualização. Portanto, os apresentadores não podem obter uma contagem exata de quem está na experiência somente visualização.

## <a name="experience-for-view-only-attendees"></a>Experiência para participantes somente visualização

A experiência do Teams apenas para visualização permite que os participantes:

- Ouça os participantes da reunião das equipes principais.
- Veja o feed de vídeo do locutor ativo (se o locutor ativo estiver compartilhando vídeo).
- Veja o conteúdo sendo compartilhado usando a funcionalidade de compartilhamento da área de trabalho.

O participante somente visualização não poderá experimentar as seguintes opções nas reuniões:

- Participe da reunião se o participante não tiver permissão para ignorar o lobby com base nas políticas ou opções de lobby definidas.
- Entre na sala somente para visualização usando a conferência de áudio.
- Participe da sala somente para visualização usando o sistema Sala do Microsoft Teams ou os serviços Cloud Video Interop (CVI).
- Compartilhe seu áudio ou vídeo.
- Veja ou participe do chat da reunião.
- Veja o feed de vídeo dos participantes da reunião, a menos que o participante seja o palestrante ativo.
- Consulte os arquivos do PowerPoint que são compartilhados usando a funcionalidade de compartilhamento nativo do PowerPoint ou compartilhamentos de aplicativos individuais (diferente do compartilhamento da área de trabalho).

## <a name="view-only-feature-limitations"></a>Limitações do recurso somente visualização

- Os participantes somente para visualização sempre verão as legendas ao vivo, independentemente da configuração das legendas ao vivo para aquela reunião. Apenas legendas em inglês são suportadas no momento.
- Os participantes somente para visualização terão o suporte da tecnologia de streaming.
- Os participantes somente para visualização não serão incluídos no relatório de presença.
- Os participantes somente para visualização terão uma única experiência de vídeo. Eles podem ver o locutor ativo ou o conteúdo que está sendo compartilhado, mas não ambos.
- No momento, não oferecemos suporte para **Galeria**, **Galeria grande** ou **Modo conferência** layouts para participantes somente para visualização.  
- Os participantes somente para visualização não terão a mesma latência de um participante normal. <sup>1</sup>

  <sup>1</sup> Os participantes somente para visualização terão um atraso de 30 segundos de vídeo e áudio na reunião.  
