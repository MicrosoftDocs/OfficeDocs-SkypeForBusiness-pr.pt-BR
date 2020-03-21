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
localization_priority: Normal
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Saiba mais sobre os fatores a serem considerados antes de configurar eventos ao vivo no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f0c141751a9b67a47640ba5210c3cb7aeeadbb2
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558561"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planejar eventos ao vivo no Microsoft Teams

Quando você planeja eventos ao vivo do Teams para realizar grandes reuniões em sua organização, há vários fatores que você precisa considerar antes de começar a configurá-los. 

## <a name="who-can-create-and-schedule-live-events"></a>Quem pode criar e agendar eventos ao vivo? 
Os pré-requisitos a seguir são necessários para o usuário agendar um evento ao vivo do Teams.

Estas são as licenças que devem ser atribuídas:  
- Uma licença do Office 365 Enterprise E1, E3 ou E5 ou uma licença do Office 365 A3 ou A5
- Uma licença do Microsoft Teams
- Uma licença do Microsoft Stream

> [!IMPORTANT]
> O usuário que cria e agenda um evento ao vivo deve ter uma caixa de correio do Exchange Online.

É importante saber que uma licença do Office 365 é necessária para participar de um evento ao vivo como um usuário autenticado, mas esse requisito depende do método de produção utilizado:

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

> [!IMPORTANT]
> Os usuários anônimos não autenticados não podem ser convidados como produtores ou apresentadores em eventos ao vivo do Teams. 
 
## <a name="who-can-watch-live-events"></a>Quem pode assistir a eventos ao vivo?

|**Visibilidade do participante**       |**Produção do Teams**  |**Produção de dispositivos ou aplicativos externos**  |
|------------------------------|-----------------|----------------------|
|Público (usuários anônimos)      |  Sim            |  Não                  |
|Usuários convidados                   |  Não<sup>1</sup> |  Não                  |
|Todos na empresa federada |  Não<sup>2</sup> |  Não                  |
|Todos na empresa           |  Sim            |  Sim                 |
|Grupos / Pessoas específicos(as)      |  Sim            |  Sim                 |

<sup>1</sup> Podem assistir a eventos ao vivo se o evento ao vivo estiver configurado usando a opção **Toda a organização**.<br>
<sup>2</sup> Podem somente assistir a eventos ao vivo como usuários anônimos.

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventos ao vivo do Teams e Transmissão de Reunião do Skype

A tabela a seguir destaca os principais recursos oferecidos em eventos ao vivo e como eles diferem da Transmissão de Reunião do Skype. 

|**Funcionalidade**   |**Transmissão de Reunião do Skype** |**Eventos produzidos no Teams** |**Eventos produzidos em dispositivos ou aplicativos externos** |
|---------|---------|---------|---------|
|Tamanho máximo da audiência |10.000 participantes |10.000 participantes<sup>1</sup> |10.000 participantes<sup>1</sup> |
|Duração máxima do evento ao vivo |4 horas |4 horas |4 horas |
|Número máximo de eventos ao vivo simultâneos por locatário do Office 365 |15  | 15  | 15  |
|Criação de evento ao vivo |   Portal de Transmissão de Reunião do Skype |Teams, Yammer via Teams | Teams, Yammer via Teams, Stream |
|Envolvimento do público – Yammer  |&#x2714; |&#x2714; (experiência integrada) |&#x2714; (experiência integrada) |
|Envolvimento do público – Perguntas e Respostas Moderadas  |&#x2714;  |&#x2714; |&#x2714; |
|Cliente do Producer no Windows |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; (Stream, Teams via Inserir Stream) |
|Cliente do Producer no Mac |X  | &#x2714; (Teams) |&#x2714; (Stream, Teams via Inserir Stream) |
|Contagem de participantes na IU do Producer |X  |&#x2714; (Teams) |&#x2714; (Stream, Teams via Inserir Stream) |
|Permitir vários apresentadores |&#x2714; (Skype for Business) |&#x2714; (Teams) |Não disponível  |
|Convidar um apresentador durante a reunião |&#x2714; (Skype for Business) |X |Não disponível |
|Ingresso do apresentador na Web e móvel |&#x2714; (Skype for Business)  |X |Não disponível |
|Apresentadores/participantes convidados e federados |&#x2714; (Skype for Business)  | (em breve) |Não disponível |
|Apresentador – acesso PSTN |X |&#x2714; (Teams) |Não disponível |
|Apresentar uma tela |X |&#x2714; (Teams) |Não disponível |
|Apresentar um PowerPoint (compartilhamento de PPT) |&#x2714; |X (mitigado via compartilhamento de tela) |Não disponível |
|Gravação de reuniões baseadas na nuvem |&#x2714; |&#x2714; |&#x2714; |
|Publicar automaticamente a gravação no Stream |X |X |&#x2714; |
|Legendas em tempo real |&#x2714; |&#x2714; |X |
|Legendas em gravações de eventos ao vivo |&#x2714; |&#x2714; |&#x2714; |
|Controles de DVR dos participantes (pausar, retroceder) |&#x2714; |&#x2714; |&#x2714; |
|Suporte a eCDN de parceiro |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |
|Relatório de participação posterior à transmissão para Produtores |&#x2714; |&#x2714; |X |
|Análise de opiniões do público – Votação ao vivo e sondagens  |&#x2714; (Microsoft Pulse) |X |X |

<sup>1</sup> Os limites que são definidos podem ser alterados.

## <a name="regional-availability"></a>Disponibilidade regional
Você pode usar os eventos ao vivo do Teams em várias regiões do mundo inteiro. As informações a seguir mostram a disponibilidade dos membros e participantes da equipe de eventos. 

> [!IMPORTANT]
> A região do evento é selecionada automaticamente dependendo do organizador e da organização do Office 365.

**Disponível nestas regiões**
- Américas
- Europa/África
- Pacífico Asiático
- Fique no Local Canadá, Índia, Austrália, Japão, Reino Unido

**Exclusões e considerações**
- **Fique nos Locais:** o Teams Fique nos Locais, tirando os que estão listados acima, não têm suporte no momento.
- **China:** membros da equipe de eventos e participantes não poderão usar os eventos ao vivo do Teams porque a CDN do Azure não é acessível na China. Uma solução alternativa é usar uma conexão VPN da empresa, que recebe o cliente conectado à CDN pela rede corporativa do cliente.

## <a name="next-steps"></a>Próximas etapas
Acesse [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Tópicos relacionados
- [O que são os eventos ao vivo do Teams?](what-are-teams-live-events.md)
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo do Teams](configure-teams-live-events.md)

