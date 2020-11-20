---
title: Planejar eventos ao vivo no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Priority
ms.collection:
- M365-collaboration
- m365initiative-meetings
- enabler-strategic
search.appverid: MET150
description: Neste artigo, você aprenderá sobre os fatores a serem considerados antes de configurar eventos ao vivo no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1be13bb3e92a7ccd927696061ba20d3e4513080
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130582"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planejar eventos ao vivo no Microsoft Teams

Ao planejar eventos ao vivo do Teams para realizar grandes reuniões em sua organização, há vários fatores que você precisa considerar antes de iniciar a configuração.

> [!Note]
> For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.

## <a name="who-can-attend-create-and-schedule-live-events"></a>Quem pode participar, criar e agendar eventos ao vivo?

Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).

Os pré-requisitos a seguir são necessários para o usuário agendar um evento ao vivo do Teams.

Estas são as licenças que devem ser atribuídas para produzir ou apresentar um evento ao vivo no Teamse:  

- A Microsoft or Office 365 Enterprise E1, E3, or E5 license or an Office 365 Education A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.
- Uma licença do Microsoft Teams - está incluída nas licenças listadas no primeiro marcador.
- Uma licença do Microsoft Stream-será necessária se você estiver planejando compartilhar o conteúdo para um aplicativo ou dispositivo externo; Confira [licenciamento do Microsoft Stream](https://docs.microsoft.com/stream/license-overview).

  Os usuários não precisarão de uma licença do Microsoft Stream atribuída se você quiser que apenas gravem e baixem as gravações. Isso significa que as gravações não são armazenadas no Microsoft Stream, mas sim no Serviços de Mídia do Microsoft Azure (SMA) com um limite de 180 dias antes de serem excluídas. Não é algo neste momento que um administrador pode controlar ou gerenciar para incluir a capacidade de excluí-lo.

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to OneDrive for Business and SharePoint for meeting recordings.

> [!NOTE]
> Neste momento, não há nenhum plano do Microsoft 365 Small Business, que possa ser usado para criar e realizar eventos ao vivo no Teams.

É importante saber que uma licença do Microsoft 365 ou do Office 365 é necessária para participar de um evento ao vivo como um usuário autenticado, mas esse requisito depende do método de produção utilizado:

- **Para os eventos produzidos no Teams**  O usuário deve receber uma licença do Teams.
- **Para os eventos produzidos com um aplicativo ou dispositivo externo** O usuário deve receber uma licença do Stream.

> [!NOTE]
> Os eventos ao vivo do Teams agora estão disponíveis para organizações da GCC (Comunidade Governamental na Nuvem) dos Estados Unidos.

Para obter mais informações sobre licenciamento, confira [Licenciamento de complemento do Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

O usuário deverá ter:

- Agendamento de reunião particular no Teams habilitado (*O parâmetro TeamsMeetingPolicy -AllowPrivateMeetingScheduling = Verdadeiro*).
- Compartilhamento de vídeo habilitado em reuniões do Teams (*O parâmetro TeamsMeetingPolicy -AllowIPVideo = Verdadeiro*).
- Compartilhamento de tela habilitado em reuniões do Teams (*O parâmetro TeamsMeetingPolicy -ScreenSharingMode = EntireScreen*).
- Agendamento de eventos ao vivo do Teams habilitado (*O parâmetro TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling = Verdadeiro*).
- Permissões para criar eventos ao vivo no Stream (para produção de dispositivos ou aplicativos externos).
- Modo de coexistência configurado para agendar reuniões do Teams (*Ilhas, primeira reunião ou apenas o Teams*).

> [!IMPORTANT]
> Os usuários anônimos não autenticados não podem ser convidados como produtores ou apresentadores em eventos ao vivo do Teams.

### <a name="guest-to-present"></a>[Convidado para apresentar](#guest-to-present)

Para um convidado apresentar em um evento ao vivo, faça o seguinte:

1. [Adicione o usuário como um convidado a uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Solicite que o usuário aceite o convite de convidado e participe da equipe.
3. [Agende o evento ao vivo e adicione o convidado ao seu grupo de eventos](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then click the link to join the event.

## <a name="who-can-watch-live-events"></a>Quem pode assistir a eventos ao vivo

| Visibilidade do participante | Produção do Teams | Produção de aplicativos ou dispositivos externos |
|------------------------------|-----------------|----------------------|
|Público (usuários anônimos)      |  Sim            |  Não                  |
|Usuários convidados                   |  Sim            |  Não                  |
|Todos na empresa de acesso externo (federação) |  Sim<sup>1</sup>|  Não                  |
|Todos na empresa           |  Sim            |  Sim                 |
|Grupos / Pessoas específicos(as)      |  Sim            |  Sim                 |

<sup>1</sup> Participantes de acesso externo (federação) só podem ser convidados através do Pessoas e Grupos <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventos ao vivo do Teams e Transmissão de Reunião do Skype

A tabela a seguir destaca os principais recursos oferecidos em eventos ao vivo e como eles diferem da Transmissão de Reunião do Skype.

> [!IMPORTANT]
> **O limite de eventos ao vivo do Microsoft 365 cresce**
>
> **Para ajudar a dar suporte aos nossos clientes, a partir de 1º de janeiro de 2021, estenderemos o limite temporário para que os eventos ao vivo sejam hospedados no Teams, Stream e no Yammer, incluindo**:
>
>- Até 20.000 participantes por evento
>- Até 50 eventos simultâneos por locatário do Teams
>- Até 16 horas por transmissão
>
> Além disso, eventos ao vivo com até 100.000 participantes podem ser planejados através do programa Microsoft 365 de assistência a eventos ao vivo. A equipe avaliará cada solicitação e trabalhará com você para determinar as opções que possam estar disponíveis. [Saiba mais](https://aka.ms/Stream/Blog/LiveEventOptions). **Depois de 1º de janeiro de 2021, os clientes que precisarem desses aumentos de limite serão obrigados a adquirir o [suplemento de Comunicações avançadas](../teams-add-on-licensing/advanced-communications.md).**

| Recursos | Transmissão de Reunião do Skype | Eventos produzidos no Teams | Eventos produzidos em aplicativos ou dispositivos externos |
|---------|---------|---------|---------|
|Tamanho máximo da audiência |10.000 participantes |10.000 participantes<sup>1</sup> |10.000 participantes<sup>1</sup> |
|Duração máxima do evento ao vivo |4 horas |4 horas |4 horas |
|Número máximo de apresentadores e produtores em um evento ao vivo |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Número máximo de eventos ao vivo simultâneos por organização do Microsoft 365 ou do Office 365 |15  | 15  | 15  |
|Criação de evento ao vivo |   Portal de Transmissão de Reunião do Skype |Teams, Yammer via Teams | Teams, Yammer via Teams, Stream |
|Envolvimento do público – Yammer  |&#x2714; |&#x2714; (experiência integrada) |&#x2714; (experiência integrada) |
|Envolvimento do público – Perguntas e Respostas Moderadas  |&#x2714;  |&#x2714; |&#x2714; |
|Cliente do Producer no Windows |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; (Stream, Teams via Inserir Stream) |
|Cliente do Producer no Mac |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream, Teams via Inserir Stream) |
|Contagem de participantes na IU do Producer |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream, Teams via Inserir Stream) |
|Permitir vários apresentadores |&#x2714; (Skype for Business) |&#x2714; (Teams) |Não disponível  |
|Convidar um apresentador durante a reunião |&#x2714; (Skype for Business) |&#x274C; |Não disponível |
|Ingresso do apresentador na Web e móvel |&#x2714; (Skype for Business)  |&#x274C; |Não disponível |
|Acesso externo (federação) e apresentadores/participantes convidados |&#x2714; (Skype for Business)  |  &#x2714; (Teams) |Não disponível |
|Apresentador – acesso PSTN |&#x274C; |&#x2714; (Teams) |Não disponível |
|Apresentar uma tela |&#x274C; |&#x2714; (Teams) |Não disponível |
|Compartilhar áudio do sistema no Windows (disponível apenas durante o compartilhamento de tela)|&#x274C; |&#x2714; (Teams) |&#x2714; |
|Apresentar um PowerPoint (compartilhamento de PPT) |&#x2714; |&#x274C; (mitigado por compartilhamento de tela) |Não disponível |
|Gravação de reuniões baseadas na nuvem |&#x2714; |&#x2714; |&#x2714; |
|Publicar automaticamente a gravação no Stream |&#x274C; |&#x274C; |&#x2714; |
|Legendas em tempo real |&#x2714; |&#x2714; |&#x274C; |
|Legendas em gravações de eventos ao vivo |&#x2714; |&#x2714; |&#x2714; |
|Controles de DVR dos participantes (pausar, retroceder) |&#x2714; |&#x2714; |&#x2714; |
|Suporte a eCDN de parceiro |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|Relatório de participação posterior à transmissão para Produtores |&#x2714; |&#x2714; |&#x274C; |
|Análise de opiniões do público – Votação ao vivo e sondagens  |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> Você pode ter até 250 apresentadores e produtores em um evento ao vivo, mas apenas as últimas 10 pessoas que falaram são exibidas na lista.

## <a name="regional-availability"></a>Disponibilidade regional

You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.

> [!IMPORTANT]
> A região do evento é selecionada automaticamente, dependendo do organizador e do local do locatário do Microsoft 365.

**Disponível nestes data centers regionais**

- América do Norte
- América Central
- América do Sul
- Pacífico Asiático
- Europa/África

**Local de dados para esses países/regiões (com suporte)**

- Austrália
- Canadá
- Índia
- Japão
- Reino Unido

**Não há suporte para esses países/regiões e nuvens**

- Alemanha
- França
- Noruega
- África do Sul
- Coreia do Sul
- Suíça
- EMIRADOS
- Nuvem Comunitária do Governo (GCC)-H
- Departamento de Defesa

**Exclusões e considerações**

- **Localização de dados:** Localizações de dados do Teams, fora das listadas acima, não são suportadas no momento.
- **China:** Event team members and attendees will not be able to use Teams live events because Azure CDN is not accessible in China. A workaround is to use a company VPN connection, which gets the client connected to CDN via the customer's corporate network.

## <a name="next-steps"></a>Próximas etapas

Acesse [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Tópicos relacionados

- [O que são os eventos ao vivo do Teams?](what-are-teams-live-events.md)
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo do Teams](configure-teams-live-events.md)
