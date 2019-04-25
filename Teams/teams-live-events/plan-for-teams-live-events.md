---
title: Planejar eventos ao vivo no Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Saiba mais sobre os fatores a serem considerados antes de configurar o live eventos no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 427a0dc26ef3c5b9901ddbe9cefe1288c905ccbb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223372"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planejar eventos ao vivo no Microsoft Teams

Quando você estiver planejando eventos ao vivo de equipes para armazenar grandes reuniões em sua organização, há vários fatores que você precisa considerar antes de começar a defini-la sempre para cima. 

## <a name="who-can-create-and-schedule-live-events"></a>Quem pode criar e agendar eventos ao vivo? 
Os seguintes pré-requisitos são necessários para o usuário agendar um evento de equipes ao vivo.

Aqui estão as licenças que devem ser atribuídas:  
- Uma licença do Office 365 Enterprise E1, E3 ou E5 ou uma licença do Office 365 A3 ou A5. 
- Uma licença Teams da Microsoft e Microsoft Stream.

É importante saber o que uma licença do Office 365 é necessário para participar de um evento ao vivo como um usuário autenticado, mas isso depende do método de produção usado:

- **Produção para a rápida de iniciar**  O usuário deve ser atribuído a uma licença do Microsoft Teams.
- **Produção de codificador para externo** O usuário deve ser atribuído a uma licença do Microsoft Stream.

Para obter mais informações sobre licenciamento, consulte [Licenciamento de complemento de equipes da Microsoft](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

O usuário deverá ter:
- Agendamento de reuniões privadas em equipes habilitadas (*- AllowPrivateMeetingScheduling TeamsMeetingPolicy o parâmetro = True*).
- Compartilhamento de vídeo ativado em reuniões de equipes (*- AllowIPVideo TeamsMeetingPolicy o parâmetro = True*).
- Compartilhamento de tela habilitado em reuniões de equipes (*- ScreenSharingMode TeamsMeetingPolicy o parâmetro = EntireScreen*).
- Live evento agenda em equipes habilitadas (*- AllowBroadcastScheduling TeamsMeetingBroadcastPolicy o parâmetro = True*).
- Permissões para criar eventos ao vivo no Microsoft Stream (para produção codificador externo).

> [!IMPORTANT]
> O Office 365 convidados, usuários federados e anônimos não podem ser convidados como produtores ou apresentadores em equipes de eventos ao vivo. Convidado Office 365 e os usuários federados podem apenas assista eventos ao vivo anonimamente. 
 
## <a name="who-can-watch-live-events"></a>Quem pode assistir eventos ao vivo?

|**Visibilidade do participante**       |**Início rápido**  |**Codificador externo**  |
|------------------------------|-----------------|----------------------|
|Público (usuários anônimos)      |  Sim            |  Não                  |
|Usuários convidados                   |  Nenhum<sup>1</sup> |  Não                  |
|Todos na empresa federada |  Nenhum<sup>1</sup> |  Não                  |
|Todas as pessoas da empresa           |  Sim             |  Sim                 |
|Específicas agrupa / de pessoas      |  Sim             |  Sim                 |

<sup>1</sup> somente pode assistir eventos ao vivo como usuários anônimos.

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventos ao vivo de equipes e transmissão de reunião do Skype
A tabela a seguir destaca os principais recursos e capacidades oferecidas em eventos ao vivo e como eles diferem da transmissão do Skype reunião. 

|**Recurso**   |**Transmissão de Reunião do Skype** |**Eventos produzidos no Microsoft Teams** |**Eventos produzido no dispositivo ou aplicativo externo** |
|---------|---------|---------|---------|
|Tamanho máximo de audiência |10.000 participantes |10.000 participantes * |10.000 participantes * |
|Duração máxima de evento ao vivo |4 horas |4 horas |4 horas |
|Criação de evento ao vivo |   Portal de transmissão de reunião do Skype |As equipes, Yammer via equipes | As equipes, Yammer via fluxo, equipes |
|Compromisso de público-alvo – o Yammer |& #x 2714; |& #x 2714; (experiência integrada) |& #x 2714; (experiência integrada) |
|Compromisso de público-alvo – Q moderados & uma |& #x 2714;  |& #x 2714; |& #x 2714; |
|Cliente de produtor no Windows |& #x 2714; (Skype para negócios) |& #x 2714; (As equipes) |& #x 2714; (Stream, equipes via fluxo incorporar) |
|Cliente de produtor no Mac |X  | & #x 2714; (As equipes) |& #x 2714; (Stream, equipes via fluxo incorporar) |
|Contagem de participantes na interface do usuário do produtor |X  |& #x 2714; (As equipes) |& #x 2714; (Stream, equipes via fluxo incorporar) |
|Permite que vários apresentadores |& #x 2714; (Skype para negócios) |& #x 2714; (As equipes) |N/D  |
|Convidar um apresentador durante a reunião |& #x 2714; (Skype para negócios) |X |N/D |
|Apresentador de ingresso na Web e dispositivos móveis |& #x 2714; (Skype para negócios)  |X |N/D |
|Os apresentadores de convidado & federados/participantes |& #x 2714; (Skype para negócios)  | (em breve) |N/D |
|Apresentador – acesso à PSTN |X |& #x 2714; (As equipes) |N/D |
|Apresentar uma tela |X |& #x 2714; (As equipes) |N/D |
|Apresentar um PowerPoint (compartilhamento de PPT) |& #x 2714; |X (minimizado via compartilhamento de tela) |N/D |
|Gravação de reunião com base na nuvem |& #x 2714; |& #x 2714; |& #x 2714; |
|Auto Publish gravação fluxo da Microsoft |X |X |& #x 2714; |
|Conversão e legendas de Tempo Real |& #x 2714; |& #x 2714; (em breve) |X |
|Legendas em gravações de evento ao vivo |& #x 2714; |& #x 2714; (em breve) |& #x 2714; |
|Controles DVR ATTENDEE (pausar, retroceder) |& #x 2714; |& #x 2714; |& #x 2714; |
|Parceiro eCDN suporte |& #x 2714; (Hive, Kollective, conheça) |& #x 2714; (Hive, Kollective, conheça) |& #x 2714; (Hive, Kollective, conheça) |
|Relatório de pós-transmissão de presença para produtores |& #x 2714; |& #x 2714; |X |
|Audiência sentimento análise – votações de & votação ao vivo |& #x 2714; (Microsoft pulso) |X |X |

> [!IMPORTANT]
> Os limites definidos podem ser alterados.

## <a name="regional-availability"></a>Disponibilidade regional
Você pode usar eventos ao vivo de equipes em vários regiões no mundo inteiro. As informações a seguir mostram a disponibilidade para participantes e os membros da equipe de evento. 

> [!IMPORTANT]
> A região para o evento será selecionada automaticamente dependendo do organizador e a organização do Office 365.

**Disponível nessas regiões**
- Américas
- Europa/África
- Ásia Pacífico
- Vá Canadá Local

**Exclusões e considerações**
- **Ir locais:** Reino Unido, Índia, Austrália, Japão e outros locais de ir de equipes da Microsoft não são suportados no momento.
- **China:** Membros da equipe de evento e os participantes não poderão usar eventos ao vivo de equipes, porque o Windows Azure CDN não está acessível na China. Uma solução alternativa é usar uma conexão VPN, que obtém o cliente conectado CDN via rede corporativa do cliente da empresa.

## <a name="next-steps"></a>Próximas etapas
Vá para [Configurar o para equipes de eventos ao vivo](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Tópicos relacionados
- [O que são os eventos ao vivo do Teams?](what-are-teams-live-events.md)
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo em equipes](configure-teams-live-events.md)

