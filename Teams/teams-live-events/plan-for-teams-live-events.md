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
search.appverid: MET150
description: Neste artigo, você aprenderá sobre os fatores a serem considerados antes de configurar eventos ao vivo no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 424798b7f9acf1445510eb6a072631dda9501307
ms.sourcegitcommit: 27fae90d4429e81143ea285edab9dbc19bd3c0bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44854103"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planejar eventos ao vivo no Microsoft Teams

Quando você planeja eventos ao vivo do Teams para realizar grandes reuniões em sua organização, há vários fatores que você precisa considerar antes de começar a configurá-los.

## <a name="who-can-attend-create-and-schedule-live-events"></a>Quem pode participar, criar e agendar eventos ao vivo?

Todos podem participar de um evento ao vivo sem uma licença. Leia [Início rápido do administrador – Reuniões e eventos ao vivo](../quick-start-meetings-live-events.md).

Os pré-requisitos a seguir são necessários para o usuário agendar um evento ao vivo do Teams.

Estas são as licenças que devem ser atribuídas para produzir ou apresentar um evento ao vivo no Teamse:  

- Uma licença do Microsoft ou Office 365 Enterprise E1, E3 ou E5 ou uma licença do Office 365 para Educação A3 ou A5.
- Uma licença do Microsoft Teams. -isso está incluído nas licenças acima. 
- Uma licença do Microsoft Stream-será necessária se você estiver planejando compartilhar o conteúdo para um aplicativo ou dispositivo externo; Confira [licenciamento do Microsoft Stream](https://docs.microsoft.com/stream/license-overview). 

  Os usuários não precisarão de uma licença do Microsoft Stream atribuída se você quiser que somente registrem e baixem as gravações. Isso significará que as gravações não são armazenadas no Microsoft Stream, mas, em vez disso, são armazenadas no AMS (Azure Media Services) com um limite de 30 dias antes de serem excluídas. Não é algo neste ponto que um administrador pode controlar ou gerenciar o, incluindo a capacidade de excluí-lo.

> [!NOTE]
> Neste momento, não há nenhum plano do Microsoft 365 Small Business, que possa ser usado para criar e realizar eventos ao vivo no Teams.

É importante saber que uma licença do Microsoft 365 ou do Office 365 é necessária para participar de um evento ao vivo como um usuário autenticado, mas esse requisito depende do método de produção utilizado:

- **Para os eventos produzidos no Teams**  O usuário deve receber uma licença do Teams.
- **Para os eventos produzidos com um aplicativo ou dispositivo externo** O usuário deve receber uma licença do Stream.

> [!NOTE]
> Os eventos ao vivo do Teams agora estão disponíveis para organizações da GCC (Comunidade Governamental na Nuvem) dos Estados Unidos.

Para obter mais informações sobre licenciamento, confira [Licenciamento de complemento do Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

O usuário deverá ter:

- Agendamento de reunião particular no Teams habilitado (*O parâmetro TeamsMeetingPolicy -AllowPrivateMeetingScheduling = Verdadeiro*).
- Compartilhamento de vídeo habilitado em reuniões do Teams (*O parâmetro TeamsMeetingPolicy -AllowIPVideo = Verdadeiro*).
- Compartilhamento de tela habilitado em reuniões do Teams (*O parâmetro TeamsMeetingPolicy -ScreenSharingMode = EntireScreen*).
- Agendamento de eventos ao vivo do Teams habilitado (*O parâmetro TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling = Verdadeiro*).
- Permissões para criar eventos ao vivo no Stream (para produção de dispositivos ou aplicativos externos).
- Modo de coexistência configurado para agendar reuniões do Teams (*Ilhas, primeira reunião ou apenas o Teams*).

> [!IMPORTANT]
> Os usuários anônimos não autenticados não podem ser convidados como produtores ou apresentadores em eventos ao vivo do Teams.

Para um convidado apresentar em um evento ao vivo, faça o seguinte:

1. [Adicione o usuário como um convidado a uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Solicite que o usuário aceite o convite de convidado e participe da equipe.
3. [Agende o evento ao vivo e adicione o convidado ao seu grupo de eventos](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

Como prática recomendada, recomendamos que você crie um canal para produtores e apresentadores do evento ao vivo para que eles possam conversar e compartilhar informações antes do evento. Os convidados que não têm credenciais do Microsoft 365 não verão o calendário nas equipes. Para que seja mais fácil se juntar ao evento, os produtores podem postar o link de evento no canal. Os apresentadores podem abrir o Teams, ir para o canal e, em seguida, clicar no link para entrar no evento. 

## <a name="who-can-watch-live-events"></a>Quem pode assistir a eventos ao vivo

|**Visibilidade do participante**       |**Produção do Teams**  |**Produção de dispositivos ou aplicativos externos**  |
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
> Para ajudar os clientes a atender às necessidades de comunicação que mudam rapidamente, os eventos ao vivo do Microsoft 365 aumentarão temporariamente os limites padrão até 1º de julho de 2020, para eventos ao vivo hospedados no Teams. Os seguintes aumentos foram lançados no final de abril de 2020:
> - Limite de participantes: os eventos podem dar suporte a no máximo 20.000 participantes
> - Eventos simultâneos: 50 eventos podem ser hospedados simultaneamente em um locatário
> - Duração do evento: a duração do evento aumentou para 16 horas por transmissão

|**Funcionalidade**   |**Transmissão de Reunião do Skype** |**Eventos produzidos no Teams** |**Eventos produzidos em dispositivos ou aplicativos externos** |
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
|Suporte a eCDN de parceiro |&#x2714; (Kollective, Hive) |&#x2714; (Kollective, Hive) |&#x2714; (Hive, Kollective, Ramp) |
|Relatório de participação posterior à transmissão para Produtores |&#x2714; |&#x2714; |&#x274C; |
|Análise de opiniões do público – Votação ao vivo e sondagens  |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> Os limites que são definidos podem ser alterados. Verifique [Limites e especificações do Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> Você pode ter até 250 apresentadores e produtores em um evento ao vivo, mas apenas as últimas 10 pessoas que falaram são exibidas na lista.

## <a name="regional-availability"></a>Disponibilidade regional

Você pode usar os eventos ao vivo do Teams em várias regiões do mundo inteiro. As informações a seguir mostram a disponibilidade dos membros e participantes da equipe de eventos.

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
- **China:** membros da equipe de eventos e participantes não poderão usar os eventos ao vivo do Teams porque a CDN do Azure não é acessível na China. Uma solução alternativa é usar uma conexão VPN da empresa, que recebe o cliente conectado à CDN pela rede corporativa do cliente.

## <a name="next-steps"></a>Próximas etapas

Acesse [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Tópicos relacionados

- [O que são os eventos ao vivo do Teams?](what-are-teams-live-events.md)
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo do Teams](configure-teams-live-events.md)
