---
title: Planejar eventos ao vivo no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
search.appverid: MET150
description: Neste artigo, você aprenderá sobre os fatores a serem considerados antes de configurar eventos ao vivo no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cde485a3cf290c105ae475e6f7733787ba6971a2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767602"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planejar eventos ao vivo no Microsoft Teams

Ao planejar eventos ao vivo do Teams para realizar grandes reuniões em sua organização, há vários fatores que você precisa considerar antes de iniciar a configuração.

> [!NOTE]
> For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.

## <a name="who-can-attend-create-and-schedule-live-events"></a>Quem pode participar, criar e agendar eventos ao vivo?

Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).

Os pré-requisitos a seguir são necessários para o usuário agendar um evento ao vivo do Teams.

Estas são as licenças que devem ser atribuídas para organizar, produzir ou apresentar um evento ao vivo no Teams:  

- **Para organizar:** Uma licença E1, E3, ou E5 da Microsoft ou do Office 365 Enterprise, **[ou]** uma licença A3 ou A5 da Microsoft ou do Office 365 Education.
- **To produce or present:** A Microsoft or Office 365 Enterprise E1, E3 or E5 license, **[or]** a Microsoft or Office 365 Education A1, A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.
- Uma licença do Microsoft Teams - esta licença está incluída nas licenças listadas no primeiro e segundo itens.

> [!NOTE]
> Neste momento, não há nenhum plano do Microsoft 365 Small Business, que possa ser usado para criar e realizar eventos ao vivo no Teams.

É importante saber que uma licença do Microsoft 365 ou do Office 365 é necessária para participar de um evento ao vivo como um usuário autenticado, mas esse requisito depende do método de produção utilizado:

- **Para eventos produzidos no Teams ou usando um codificador do Teams Powered**  O usuário deve receber uma licença do Teams.

> [!NOTE]
> Os eventos ao vivo do Teams agora estão disponíveis para organizações da GCC (Comunidade Governamental na Nuvem) dos Estados Unidos.

Para obter mais informações sobre licenciamento, confira [Licenciamento de complemento do Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

O usuário deverá ter:

- Agendamento de reunião particular no Teams habilitado (*O parâmetro TeamsMeetingPolicy -AllowPrivateMeetingScheduling = Verdadeiro*).
- Compartilhamento de vídeo habilitado em reuniões do Teams (*O parâmetro TeamsMeetingPolicy -AllowIPVideo = Verdadeiro*).
- Compartilhamento de tela habilitado em reuniões do Teams (*O parâmetro TeamsMeetingPolicy -ScreenSharingMode = EntireScreen*).
- Agendamento de eventos ao vivo do Teams habilitado (*O parâmetro TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling = Verdadeiro*).
- Modo de coexistência configurado para agendar reuniões do Teams (*Ilhas, primeira reunião ou apenas o Teams*).

> [!IMPORTANT]
> Os usuários anônimos não autenticados não podem ser convidados como produtores ou apresentadores em eventos ao vivo do Teams.

### <a name="guest-to-present"></a>[Convidado para apresentar](#guest-to-present)

Para um convidado apresentar em um evento ao vivo, execute as seguintes tarefas:

1. [Adicione o usuário como um convidado a uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Solicite que o usuário aceite o convite de convidado e participe da equipe.
3. [Agende o evento ao vivo e adicione o convidado ao seu grupo de eventos](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then select the link to join the event.

## <a name="who-can-watch-live-events"></a>Quem pode assistir a eventos ao vivo

| Visibilidade do participante | Produção do Teams | Produção de aplicativos ou dispositivos externos | Codificador do Teams Powered
|------------------------------|-----------------|----------------------|----------------|
|Público (usuários anônimos)      |  Sim            |  Não                  | Sim
|Usuários convidados                   |  Sim<sup>1</sup>            |  Não                  |  Sim            |
|Todos na empresa de acesso externo (federação) |  Sim<sup>1</sup>|  Não                  | Sim            |
|Todos na empresa           |  Sim            |  Sim                 | Sim                |
|Grupos / Pessoas específicos(as)      |  Sim            |  Sim                 | Sim                |

<sup>1</sup> Só podem ser convidados através de Pessoas e Grupos <br>

## <a name="teams-live-events"></a>Eventos ao vivo do Teams

A tabela a seguir destaca os principais recursos e recursos oferecidos em eventos ao vivo

> [!IMPORTANT]
> **O limite de eventos ao vivo do Microsoft 365 cresce**
>
> **Para continuar dando suporte às necessidades de nossos clientes, estenderemos os aumentos temporários de limite para eventos ao vivo até 30 de junho de 2023, incluindo:**
>
>- Suporte a eventos para até 20.000 participantes
>- 50 eventos podem ser hospedados simultaneamente em um locatário
>- Duração do evento de 16 horas por transmissão
>
> Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 live events assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

| Recursos | Eventos produzidos no Teams | Eventos produzidos em aplicativos ou dispositivos externos |
|---------|---------|---------|
|Tamanho máximo da audiência |10.000 participantes<sup>1</sup> |10.000 participantes<sup>1</sup> |
|Duração máxima do evento ao vivo |4 horas |4 horas |
|Número máximo de apresentadores e produtores em um evento ao vivo |10 <sup>2</sup> |10 <sup>2</sup> |
|Número máximo de eventos ao vivo simultâneos por organização do Microsoft 365 ou do Office 365 | 15  | 15  |
|Criação de evento ao vivo |Teams, Yammer via Teams | Teams, Yammer via Teams, Stream |
|Envolvimento do público – Yammer  |&#x2714; (experiência integrada) |&#x2714; (experiência integrada) |
|Envolvimento do público – Perguntas e Respostas Moderadas  |&#x2714; |&#x2714; |
|Cliente do Producer no Windows |&#x2714; (Teams) |&#x2714; (Stream, Teams via Inserir Stream) |
|Cliente do Producer no Mac |&#x2714; (Teams) |&#x2714; (Stream, Teams via Inserir Stream) |
|Contagem de participantes na IU do Producer |&#x2714; (Teams) |&#x2714; (Stream, Teams via Inserir Stream) |
|Permitir vários apresentadores |&#x2714; (Teams) |Não disponível  |
|Convidar um apresentador durante a reunião |&#x274C; |Não disponível |
|Ingresso do apresentador na Web e móvel |&#x274C; |Não disponível |
|Acesso externo (federação) e apresentadores/participantes convidados |&#x2714; (Teams) |Não disponível |
|Apresentador – acesso PSTN |&#x2714; (Teams) |Não disponível |
|Apresentar uma tela |&#x2714; (Teams) |Não disponível |
|Compartilhar áudio do sistema no Windows (disponível apenas durante o compartilhamento de tela)|&#x2714; (Teams) |&#x2714; |
|Apresentar um PowerPoint (compartilhamento de PPT) |&#x274C; (mitigado por compartilhamento de tela) |Não disponível |
|Gravação de reuniões baseadas na nuvem |&#x2714; |&#x2714; |
|Publicar automaticamente a gravação no Stream |&#x274C; |&#x2714; |
|Legendas em tempo real |&#x2714; |&#x274C; |
|Legendas em gravações de eventos ao vivo |&#x2714; |&#x2714; |
|Controles de DVR dos participantes (pausar, retroceder) |&#x2714; |&#x2714; |
|Microsoft eCDN |&#x2714; |&#x2714; |
|Suporte a eCDN de parceiro |&#x2714; (Kollective, Hive, Ramp, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|Relatório de participação posterior à transmissão para Produtores |&#x2714; |&#x274C; |
|Análise de opiniões do público – Votação ao vivo e sondagens  |&#x274C; |&#x274C; |

<sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> Você pode ter até 100 apresentadores e produtores em um evento ao vivo, mas apenas as últimas 10 pessoas que falaram são exibidas na lista.

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
- Brasil
- Canadá
- França
- Alemanha
- Índia
- Japão
- Noruega
- Singapura
- África do Sul
- Coreia do Sul
- Suíça
- EMIRADOS
- Reino Unido

**Exclusões e considerações**

- **Localização de dados:** Os locais de dados das equipes, fora dos listados acima, não são suportados no momento.

## <a name="next-steps"></a>Próximas etapas

Acesse [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Tópicos relacionados

- [O que são eventos ao vivo de Teams?](what-are-teams-live-events.md)
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo do Teams](configure-teams-live-events.md)
