---
title: Cite Teams Microsoft live eventos?
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Teams_ITAdmin_Help
ms.reviewer: tonysmit
search.appverid: MET150
description: Saiba como live eventos permitem aos usuários transmitir vídeo e conteúdo para grandes públicos on-line no Microsoft Teams, Yammer e Microsoft Stream.
appliesto:
- Microsoft Teams
ms.openlocfilehash: db8f9223c74b29f7fd2bfa27b63419abcb4219c5
ms.sourcegitcommit: de3271e1a637561f569b8e6838c94be8948a481a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405244"
---
# <a name="what-are-microsoft-teams-live-events"></a>Cite Teams Microsoft live eventos?
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="overview"></a>Visão geral

Com os eventos do Microsoft Teams ao vivo, os usuários em sua organização possam transmitir conteúdo de reunião e de vídeo para grandes públicos online. 

Eventos ao vivo do Microsoft 365 trazem vídeo ao vivo streaming para um novo nível, encorajando conexão em todo o ciclo de vida de compromisso inteira com participantes antes, durante e após eventos ao vivo. Você pode criar um evento ao vivo, onde quer que seu público-alvo, equipe ou comunidades residam, usando o Microsoft Stream, Teams da Microsoft, ou do Yammer.  

As equipes oferece colaboração baseada em bate-papo, chamada, reuniões e com eventos ao vivo, portanto você pode expandir a audiência das suas reuniões. Eventos ao vivo de equipes é uma extensão de reuniões de equipes, permitindo que os usuários transmitir conteúdo de reunião e vídeo para um grande público on-line. Essas servem para comunicações de um-para-muitos onde o host do evento é líder interações e a participação de audiência é principalmente exibir o conteúdo compartilhado por host. Os participantes podem assistir o evento ao vivo ou gravado no Yammer, equipes e/ou Microsoft Stream e podem interagir com os apresentadores usando moderado Q & uma ou uma conversa do Yammer. 

As equipes de eventos ao vivo são considerados a próxima versão do Skype transmissão de reunião e serão eventualmente substituem os recursos fornecidos na transmissão do Skype reunião. Durante a versão de demonstração pública do eventos ao vivo de equipes, podemos continuará dar suporte a transmissão do Skype reunião, sem interrupções no serviço para eventos novos ou futuros. No entanto, podemos incentivar você experimente equipes eventos ao vivo para aproveitar todos os recursos novos e interessantes, incluindo compartilhamento de tela, contagem de participantes e suporte para codificadores de software/hardware externo. 

Portanto, vamos começar. Primeiro, dê uma olhada no diagrama a seguir que mostra os componentes de nível altos envolvidas em eventos ao vivo do Microsoft 365 e como eles são conectados. 

![Diagrama que mostra os principais componentes de eventos ao vivo, a plataforma, agendar, produção, Stream Microsoft certified provedores de terceiros eCDN] (../media/teams-live-events.png  "Diagrama que mostra os principais componentes de eventos ao vivo, a plataforma, agendar, produção, Stream Microsoft certified provedores de terceiros eCDN")

## <a name="key-components"></a>Principais componentes
Assim, você pode ver na figura acima, existem quatro principais componentes que são usados com eventos ao vivo em equipes.

### <a name="scheduling"></a>Agendamento
As equipes fornece a capacidade dos organizadores criar um evento com o nome do participante apropriado permissões, designar os membros da equipe de evento, selecione o método de produção e convidar participantes. Se o evento ao vivo foi criado de dentro de um grupo do Yammer, os participantes do evento ao vivo poderão usar uma conversa do Yammer para interagir com pessoas no evento. 

![Captura de tela mostrando a nova tela de eventos para criar e agendar um novo evento ao vivo do live] (../media/teams-live-events-schedule.png "Captura de tela mostrando a nova tela de evento para criar e agendar um novo evento ao vivo do live")

### <a name="production"></a>Produção
Os eventos ao vivo no Microsoft 365 oferecem suporte a uma variedade de cenários de produção, inclua um evento de início rápido usando webcams ou um evento do codificador externo com o equipamento de qualidade studio. A entrada de vídeo é a base dos eventos ao vivo e ele pode variar de uma webcam única para a produção de vídeo professional uma câmera multi. Você pode escolher essas opções, dependendo de suas necessidades de projeto e o orçamento. Há duas maneiras para produzir eventos:

- **Produção de início rápido**: O método de produção do início rápido permite aos usuários produzir seus eventos ao vivo usando reuniões de equipes. Essa opção é melhor e mais rápida opção se desejar usar os dispositivos de áudio e vídeos conectado ao PC ou está convidando apresentadores remotos de participação no evento. Essa opção permite que os usuários facilmente use seus webcams e compartilhar sua tela como entrada para o evento. 

![As equipes de eventos ao vivo] (../media/teams-live-events-quick-start.png "Captura de tela mostrando um evento ao vivo, que é produzido usando rápido inicie o método de produção")

- **Produção codificador externo**: codificadores externos permitir que usuários produzir seus eventos ao vivo diretamente de um hardware externo ou um codificador baseada em software com a [Microsoft Stream](https://stream.microsoft.com). Esta é a melhor opção se você já tiver equipamento de qualidade studio (por exemplo, misturadores de mídia) quais streaming de suporte para um serviço (RTMP Real-Time Messaging Protocol). Esse tipo de produção é geralmente usado nos eventos de grande escala, como executivos corredores da cidade – onde um único fluxo de um mixer de mídia é transmitido para a audiência. 

![Captura de tela mostrando um evento ao vivo, que é produzido usando o método de produção do codificador externo] (../media/teams-live-events-external-encoder.png "Captura de tela mostrando um evento ao vivo, que é produzido usando o método de produção do codificador externo")

### <a name="streaming-platform"></a>Plataforma de fluxo contínuo
A plataforma de fluxo contínuo de evento ao vivo é composta das seguintes partes:

- **Azure Media Services** [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) oferece qualidade de transmissão serviços de fluxo de vídeos para alcançar maiores audiências em dispositivos móveis mais populares de hoje.   Media Services aprimora a acessibilidade, distribuição e escalabilidade e torna fácil e econômico para transmitir conteúdo aos públicos-locais ou em todo o mundo — tudo isso enquanto protegendo seu conteúdo.
- **Rede de fornecimento de conteúdo Azure (CDN)**  Depois que o seu fluxo fica ativo, que é entregue via a [Rede de entrega conteúdo do Windows Azure (CDN)](https://docs.microsoft.com/azure/cdn/). Azure Media Services fornece CDN integrado para streaming de pontos de extremidade. Isso permite que os fluxos sejam exibidas em todo o mundo com nenhum armazenamento em buffer.

### <a name="enterprise-content-delivery-network-ecdn"></a>Rede de entrega de conteúdo corporativo (eCDN)
O objetivo do eCDN é obter o conteúdo de vídeo da internet e distribuir o conteúdo em toda a empresa sem afetar o desempenho da rede. Você pode usar um dos seguintes eCDN parceiros certificados para otimizar sua rede para eventos ao vivo mantidos dentro da sua organização:
- [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](http://www.kollective.com)
- [Conheça](http://www.ramp.com)

### <a name="attendee-experience"></a>Experiência do participante 
A experiência do participante é o aspecto mais importante dos eventos ao vivo e é muito importante que os participantes podem participar de evento ao vivo sem a necessidade de quaisquer problemas. A experiência do participante usa o Media Player do Windows Azure e funciona em desktop, navegador e mobile (iOS, Android). O Office 365 fornece Yammer e equipes como dois hubs de colaboração e o nome do participante ao vivo experiência é integrada a essas ferramentas de colaboração. 

![As equipes de eventos ao vivo] (../media/teams-live-events-attendee.png "Experiência de captura de tela mostrando o nome do participante eventos ao vivo")

### <a name="related-topics"></a>Tópicos relacionados
- [Eventos ao vivo entre Microsoft 365 no Yammer, Teams da Microsoft e Microsoft Stream](https://docs.microsoft.com/stream/live-event-m365)
- [Eventos ao vivo no Microsoft Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Eventos ao vivo no Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Eventos ao vivo em Stream da Microsoft](https://docs.microsoft.com/stream/live-event-overview)

 
