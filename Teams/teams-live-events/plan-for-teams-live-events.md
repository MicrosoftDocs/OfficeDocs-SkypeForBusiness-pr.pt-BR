---
title: Planejar eventos ao vivo no Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
localization_priority: Normal
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Saiba mais sobre os fatores a serem considerados antes de configurar eventos dinâmicos no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 736d6b8f2000f94806077e8f1739b28be248b136
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570174"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planejar eventos ao vivo no Microsoft Teams

Quando você está planejando que os eventos do teams Live contenham reuniões grandes em sua organização, há vários fatores que você precisa considerar antes de começar a configurá-los. 

## <a name="who-can-create-and-schedule-live-events"></a>Quem pode criar e agendar eventos dinâmicos? 
Os pré-requisitos a seguir são necessários para que o usuário agende um evento ao vivo do teams.

Aqui estão as licenças que devem ser atribuídas:  
- Uma licença do Office 365 Enterprise E1, E3 ou E5 ou uma licença do Office 365 a3 ou a5
- Uma licença do Microsoft Teams
- Uma licença do Microsoft Stream

> [!IMPORTANT]
> O usuário que cria e agenda um evento ao vivo deve ter uma caixa de correio do Exchange Online.

É importante saber que uma licença do Office 365 é necessária para participar de um evento ao vivo como um usuário autenticado, mas esse requisito depende do método de produção usado:

- **Para eventos produzidos no Teams**  Deve ser atribuída uma licença do teams ao usuário.
- **Para eventos produzidos com um aplicativo ou dispositivo externo** Deve ser atribuída uma licença de fluxo para o usuário.

> [!NOTE]
> Os eventos ao vivo do teams agora estão disponíveis para organizações da comunidade de nuvens (GCC) do governo dos EUA.

Para obter mais informações sobre licenciamento, consulte [Licenciamento de Complementos do Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

O usuário deve ter:
- Agendamento de reunião particular no Microsoft Teams habilitado (*o parâmetro TeamsMeetingPolicy-AllowPrivateMeetingScheduling = verdadeiro*).
- Compartilhamento de vídeo habilitado em reuniões do Microsoft Teams (*o parâmetro TeamsMeetingPolicy-AllowIPVideo = true*).
- Compartilhamento de tela habilitado em reuniões do Teams (*o parâmetro TeamsMeetingPolicy-ScreenSharingMode = EntireScreen*).
- Agendamento de eventos dinâmicos habilitados no Microsoft Teams (*o parâmetro TeamsMeetingBroadcastPolicy-AllowBroadcastScheduling = true*).
- Permissões para criar eventos ao vivo em fluxo (para aplicativo externo ou produção de dispositivo).

> [!IMPORTANT]
> Os usuários convidados do Office 365, federados e anônimos não podem ser convidados como produtores ou apresentadores nos eventos ao vivo do teams. Os convidados do Office 365 e os usuários federados podem apenas assistir a eventos ao vivo anonimamente. 
 
## <a name="who-can-watch-live-events"></a>Quem pode assistir a eventos dinâmicos?

|**Visibilidade do participante**       |**Produção de equipes**  |**Produção de dispositivo ou aplicativo externo**  |
|------------------------------|-----------------|----------------------|
|Público (usuários anônimos)      |  Sim            |  Não                  |
|Usuários convidados                   |  Sem<sup>1</sup> |  Não                  |
|Todos na empresa federada |  Sem<sup>2</sup> |  Não                  |
|Todos na empresa           |  Sim            |  Sim                 |
|Grupos/pessoas específicos      |  Sim            |  Sim                 |

<sup>1</sup> pode assistir a eventos ao vivo se o evento ao vivo estiver configurado usando a opção de **toda a organização** .<br>
<sup>2</sup> só pode assistir a eventos dinâmicos como usuários anônimos.

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventos ao vivo do Teams e transmissão de reunião do Skype

A tabela a seguir destaca os principais recursos e recursos oferecidos em eventos dinâmicos e como eles diferem da transmissão de reunião do Skype. 

|**Potencial**   |**Transmissão de Reunião do Skype** |**Eventos produzidos no Teams** |**Eventos produzidos em um aplicativo externo ou dispositivo** |
|---------|---------|---------|---------|
|Tamanho máximo da audiência |10.000 participantes |10.000 participantes<sup>1</sup> |10.000 participantes<sup>1</sup> |
|Duração máxima do evento ao vivo |4 horas |4 horas |4 horas |
|Número máximo de eventos simultâneos ao vivo por locatário do Office 365 |15  | 15  | 15  |
|Criação de eventos ao vivo |   Portal de transmissão de reunião do Skype |Teams, Yammer via Teams | Teams, Yammer via Teams, Stream |
|Envolvimento do público-Yammer |&#x2714; |&#x2714; (experiência integrada) |&#x2714; (experiência integrada) |
|Envolvimento do público-um p moderado & A |&#x2714;  |&#x2714; |&#x2714; |
|Cliente do produtor no Windows |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; (fluxo, equipes via Stream embed) |
|Cliente do produtor no Mac |X  | &#x2714; (Teams) |&#x2714; (fluxo, equipes via Stream embed) |
|Contagem de participantes na interface do usuário do Producer |X  |&#x2714; (Teams) |&#x2714; (fluxo, equipes via Stream embed) |
|Permite vários apresentadores |&#x2714; (Skype for Business) |&#x2714; (Teams) |N/D  |
|Convidar um apresentador durante a reunião |&#x2714; (Skype for Business) |X |N/D |
|Junção do apresentador na Web e no celular |&#x2714; (Skype for Business)  |X |N/D |
|Apresentadores/participantes de convidados & agrupados |&#x2714; (Skype for Business)  | (disponível em breve) |N/D |
|Apresentador – acesso PSTN |X |&#x2714; (Teams) |N/D |
|Apresentar uma tela |X |&#x2714; (Teams) |N/D |
|Apresentar um PowerPoint (compartilhamento do PPT) |&#x2714; |X (minimizado via compartilhamento de tela) |N/D |
|Gravação de reunião baseada na nuvem |&#x2714; |&#x2714; |&#x2714; |
|Publicação automática de gravação em fluxo |X |X |&#x2714; |
|Legendas e legendas ao vivo |&#x2714; |&#x2714; |X |
|Legendas em gravações de eventos dinâmicos |&#x2714; |&#x2714; |&#x2714; |
|Controles de DVR de participantes (pausa, retrocesso) |&#x2714; |&#x2714; |&#x2714; |
|Suporte a eCDN de parceiros |&#x2714; (Hive, Kollective, rampa) |&#x2714; (Hive, Kollective, rampa) |&#x2714; (Hive, Kollective, rampa) |
|Relatório de presença pós-transmissão para produtores |&#x2714; |&#x2714; |X |
|Análise de opiniões de audiência – votação ao vivo & sondagens |&#x2714; (Microsoft Pulse) |X |X |

<sup>1</sup> os limites definidos podem ser alterados.

## <a name="regional-availability"></a>Disponibilidade regional
Você pode usar os eventos ao vivo do teams em várias regiões do mundo todo. As informações a seguir mostram a disponibilidade para participantes e membros da equipe do evento. 

> [!IMPORTANT]
> A região do evento é selecionada automaticamente, dependendo do organizador e da organização do Office 365.

**Disponível nessas regiões**
- Américas
- Europa/África
- Pacífico Asiático
- Vá para o Canadá, Índia, Austrália, Japão, Reino Unido

**Exclusões e considerações**
- **Ir para locais:** O Teams go locais, fora dos itens listados acima, não têm suporte no momento.
- **China:** Os membros da equipe de eventos e os participantes não poderão usar os eventos dinâmicos do Teams, pois a CDN do Azure não está acessível na China. Uma solução alternativa é usar uma conexão VPN da empresa, que obtém o cliente conectado à CDN por meio da rede corporativa do cliente.

## <a name="next-steps"></a>Próximas etapas
Vá para [configurar os eventos ao vivo do teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Tópicos relacionados
- [O que são os eventos ao vivo do Teams?](what-are-teams-live-events.md)
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo no Teams](configure-teams-live-events.md)

