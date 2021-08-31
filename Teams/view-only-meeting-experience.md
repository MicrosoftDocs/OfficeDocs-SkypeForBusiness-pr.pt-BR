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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2af0ae753357497be6ea54b89534f2220b7cbf6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732290"
---
# <a name="teams-view-only-meeting-experience"></a>Experiência de reunião somente para visualização de Teams

> [!Note]
> As transmissões somente para visualização estão disponíveis no Microsoft 365 E3/E5 e Microsoft 365 A3/A5. Este recurso será habilitado em 1º de março de 2021 como DESLIGADO padrão. O recurso no Microsoft 365 Government Community Cloud (GCC) começará a ser implementado no final de março de 2021. Government Community Cloud High (GCCH) e Department of Defense (DoD) serão implementados posteriormente. Você deve alterar a política padrão após essa data se quiser que o recurso seja ativado por padrão. Use o Windows PowerShell para habilitar a política `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.

> [!Note]
> Se sua reunião atingir a capacidade, Teams será dimensionada perfeitamente para acomodar uma experiência de transmissão somente para exibição de 10.000 pessoas. Além disso, durante este período de maior trabalho remoto, aproveite as transmissões ainda maiores para 20.000 pessoas até o final deste ano. Atualmente, os Webinars não suportam uma experiência de transmissão somente para exibição.

O Microsoft Teams permite que até 10.000 participantes participem de uma reunião do Teams. Depois que a capacidade da reunião principal for atingida (que é quando 1.000 usuários entram em uma reunião), os participantes adicionais ingressarão com uma experiência somente de exibição.

Os participantes que ingressarem na reunião primeiro, até a capacidade da reunião principal, terão a experiência de Teams reunião completa. Eles podem compartilhar áudio e vídeo, ver vídeos compartilhados e participar do bate-papo da reunião.

Os participantes que ingressarem depois que a capacidade da reunião principal for atingida terão uma experiência somente para visualização.

Os participantes poderão ingressar na experiência somente para exibição por meio de desktop, web e Teams mobile (Android e iOS).

> [!Note]
> A capacidade de limite atual da "reunião principal", ou seja, o número de usuários totalmente interativos é 1000 e inclui GCC e webinars.

## <a name="teams-view-only-experience-controls"></a>Teams de experiência somente exibição

Você habilita a experiência somente para exibição usando o cmdlet do módulo [`Set-CsTeamsMeetingPolicy`](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) [Do SkypeForBusiness PowerShell](/powershell/module/skype/?view=skype-ps) ou pelo menos a versão 2.0.0 do módulo [MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams).

Para usar o módulo `MicrosoftTeams` recomendado:

```PowerShell
Install-Module -Name "MicrosoftTeams" -MinimumVersion 2.0.0
Connect-MicrosoftTeams
```

Para habilitar a experiência somente para exibição, você pode usar o seguinte trecho do PowerShell:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

Para desabilitar a experiência somente para exibição, você também pode usar o PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

No futuro, você poderá habilitar ou desabilitar a experiência somente exibição no Teams de administração.

## <a name="impact-to-users"></a>Impacto nos usuários

A experiência de um usuário varia de acordo com vários fatores.

Quando a capacidade da reunião principal for atingida, um participante não poderá participar da reunião se alguma das seguintes condições for verdadeira:

- Um administrador desabilitou a Teams somente exibição para o organizador ou para todo o locatário.
- O participante somente para exibição não pode ignorar o lobby. Por exemplo, se um organizador de uma  reunião optar por fazer com que apenas pessoas da minha organização ignorem o lobby e um participante que está fora da organização tentar ingressar como um participante somente para exibição, eles não poderão participar.

Quando a capacidade da reunião principal for atingida, o organizador da reunião e os apresentadores verão uma faixa informando que os novos participantes ingressarão como participantes somente para exibição.

  ![a Teams cliente e a mensagem em faixa para organizadores e apresentadores.](media/chat-and-banner-message.png)

Quando a capacidade da reunião principal for atingida, os participantes da reunião serão informados na tela de pré-entrada que eles estão entrando no modo somente visualização.

  ![a Teams de pré-participação e a mensagem para os participantes dizendo que eles ingressarão no modo somente exibição.](media/view-only-pre-join-screen.png)

Se houver espaço, um usuário sempre participará da reunião principal. Se a reunião principal atingir a capacidade máxima e um ou mais participantes deixarem a reunião principal, a reunião principal terá capacidade disponível. Os participantes que ingressarem (ou reingressarem) na reunião entrarão na reunião principal até que ela atinja sua capacidade novamente. Os participantes que estão na experiência somente exibição não serão promovidos automaticamente para a reunião principal e não poderão ser promovidos manualmente para a reunião principal.

Se as funções de apresentador e participante foram definidas e um apresentador tenta ingressar em uma reunião depois que a reunião principal tiver atingido a capacidade, ele ingressará como um participante somente para exibição e terá as mesmas limitações que outros participantes somente para exibição. Suporte para garantir que todos os apresentadores participem da reunião principal serão colocados em uma data posterior. O organizador sempre terá espaço garantido na reunião principal.

## <a name="impact-to-meeting-presenters-and-organizers"></a>Impacto para apresentadores e organizadores de reuniões

As limitações para apresentadores de reunião e organizadores incluem:

- Você não terá informações sobre o participante somente visualização. Não oferecemos suporte ao E-discovery para participantes somente para visualização.
- Os usuários da reunião principal não podem ver os participantes somente de exibição.
- Você não pode remover um participante somente visualização da reunião.

> [!Note]
> A contagem de participantes refletirá apenas as pessoas na reunião principal e não as pessoas na sala somente para exibição. Portanto, os apresentadores não podem obter uma contagem exata de quem está na experiência somente visualização.

## <a name="experience-for-view-only-attendees"></a>Experiência para participantes somente visualização

A experiência do Teams apenas para visualização permite que os participantes:

- Ouça os participantes da reunião das equipes principais.
- Veja o feed de vídeo do locutor ativo (se o locutor ativo estiver compartilhando vídeo).
- Consulte conteúdo compartilhado usando a funcionalidade de área de trabalho ou tela de compartilhamento.

O participante somente visualização não poderá experimentar as seguintes opções nas reuniões:

- Participe da reunião se o participante não tiver permissão para ignorar o lobby com base nas políticas ou opções de lobby definidas.
- Entre na sala somente para visualização usando a conferência de áudio.
- Participe da sala somente exibição usando o Salas do Microsoft Teams ou usando serviços CVI (Cloud Video Interop).
- Compartilhe seu áudio ou vídeo.
- Veja ou participe do chat da reunião.
- Veja o feed de vídeo dos participantes da reunião, a menos que o participante seja o palestrante ativo.
- Consulte PowerPoint arquivos compartilhados usando a funcionalidade PowerPoint Live ou compartilhamentos individuais de aplicativos (diferente do compartilhamento de área de trabalho ou tela).
- Levante a mão na reunião.
- Enviar ou ver reações.
- Interaja com qualquer aplicativo 3P que se integre à reunião Teams, incluindo votações.

## <a name="view-only-feature-limitations"></a>Limitações do recurso somente visualização

- Os participantes somente para exibição poderão ver Live Captions na Área de Trabalho e na Web. Apenas legendas em inglês são suportadas no momento.
- Os participantes somente exibição não podem se registrar no Webinars.
- Os participantes somente para visualização terão o suporte da tecnologia de streaming.
- Os participantes somente para visualização não serão incluídos no relatório de presença.
- Os participantes somente para visualização terão uma única experiência de vídeo. Eles podem ver o locutor ativo ou o conteúdo que está sendo compartilhado, mas não ambos.
- No momento, não oferecemos suporte para **Galeria**, **Galeria grande** ou **Modo conferência** layouts para participantes somente para visualização.
- Os participantes somente para exibição são suportados pelas seguintes políticas de lobby: "Somente Você", "Pessoas na minha organização e convidados", "Pessoas em minha organização e organizações confiáveis e convidados" e "Todos". Se você usar uma política de lobby que não dá suporte a participantes somente exibição, os participantes somente exibição serão rejeitados da reunião. 
- Os participantes somente para visualização não terão a mesma latência de um participante normal. <sup>1</sup>

  <sup>1</sup> Os participantes somente para visualização terão um atraso de 30 segundos de vídeo e áudio na reunião.  
