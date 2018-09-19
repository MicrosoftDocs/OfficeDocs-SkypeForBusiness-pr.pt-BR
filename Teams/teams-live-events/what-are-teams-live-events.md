---
title: Quais são as equipes live eventos?
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Saiba como Live eventos permitem aos usuários transmitir vídeo e conteúdo para grandes públicos on-line no Microsoft Teams, Yammer e Microsoft Stream.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b99bd690bf504645d2967dbab31c3f58fc50fd92
ms.sourcegitcommit: d21e7ef1d4e36f4aced606e11837c693e8fd6410
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "23999240"
---
# <a name="what-are-teams-live-events"></a>Quais são as equipes live eventos?
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="overview"></a>Visão geral
Eventos ao vivo no Microsoft 365 habilitar usuários para transmissão de vídeo e de conteúdo para audiências online grandes. Eventos ao vivo do Microsoft 365 trazem vídeo ao vivo streaming para um novo nível, encorajando conexão em todo o ciclo de vida de compromisso inteira com participantes antes, durante e após eventos ao vivo. Você pode criar um evento ao vivo, onde quer que seu público-alvo, equipe ou comunidades residam, usando o Microsoft Stream, Teams da Microsoft, ou do Yammer.  

Teams da Microsoft oferece a colaboração baseada em bate-papo, chamada, reuniões e com eventos ao vivo, portanto você pode expandir a audiência das suas reuniões. Eventos ao vivo de Teams da Microsoft é uma extensão de reuniões de equipes, permitindo que os usuários transmitir conteúdo de reunião e vídeo para um grande público on-line. Essas servem para comunicações de um-para-muitos onde o host do evento é líder interações e a participação de audiência é principalmente para exibir o conteúdo compartilhado por host. Os participantes podem assistir o evento ao vivo ou gravado no Yammer, equipes e/ou Microsoft Stream e podem interagir com os apresentadores usando moderado Q & uma ou uma conversa do Yammer. 

As equipes de eventos ao vivo são considerados a próxima versão do Skype transmissão de reunião e serão eventualmente substituem os recursos fornecidos na transmissão do Skype reunião. Durante a versão de demonstração pública do eventos ao vivo de equipes, podemos continuará dar suporte a transmissão do Skype reunião, sem interrupções no serviço para eventos novos ou futuros. No entanto, podemos incentivar você experimente equipes eventos ao vivo para aproveitar todos os recursos novos e interessantes, incluindo a tela de compartilhamento, a contagem de participantes e suporte para codificadores de software/hardware externo. 

Portanto, vamos começar. Primeiro, dê uma olhada no diagrama a seguir que mostra os componentes de nível altos envolvidas em eventos ao vivo do Microsoft 365 e como eles são conectados. 

![Eventos ao vivo de equipes](../media/teams-live-events.png)

## <a name="key-components"></a>Principais componentes
Assim, você pode ver na figura acima, existem quatro principais componentes que são usados com o Live eventos no Microsoft Teams.

### <a name="scheduling"></a>Agendamento
As equipes fornece a capacidade dos organizadores criar um evento com o nome do participante apropriado permissões, designar os membros da equipe de evento, selecione o método de produção e convidar participantes. Se o evento ao vivo foi criado de dentro de um grupo do Yammer, os participantes do evento ao vivo poderão usar uma conversa do Yammer para interagir com pessoas no evento. 

### <a name="production"></a>Produção
Os eventos ao vivo no Microsoft 365 oferecem suporte a uma variedade de cenários de produção, inclua um evento de início rápido usando webcams ou um evento do codificador externo com o equipamento de qualidade studio. A entrada de vídeo é a base dos eventos ao vivo e ele pode variar de uma webcam única para a produção de vídeo professional uma câmera multi. Você pode escolher essas opções, dependendo de suas necessidades de projeto e o orçamento. Há duas maneiras para produzir eventos:

- **Produção de início rápido**: O método de produção do início rápido permite aos usuários produzir seus eventos ao vivo usando reuniões de equipes. Essa opção é melhor e mais rápida opção se desejar usar os dispositivos de áudio e vídeos conectado ao PC ou está convidando apresentadores remotos de participação no evento. Essa opção permite que os usuários facilmente use seus webcams e compartilhar sua tela como entrada para o evento. 


- **Produção codificador externo**: codificadores externos permitir que usuários produzir seus eventos ao vivo diretamente de um hardware externo ou um codificador baseada em software com a [Microsoft Stream](https://stream.microsoft.com). Esta é a melhor opção se você já tiver equipamento de qualidade studio (por exemplo, misturadores de mídia) quais streaming de suporte para um serviço (RTMP Real-Time Messaging Protocol). Esse tipo de produção é geralmente usado nos eventos de grande escala, como executivos corredores da cidade – onde um único fluxo de um mixer de mídia é transmitido para a audiência. 

### <a name="streaming-platform"></a>Plataforma de fluxo contínuo
A plataforma de fluxo contínuo de evento ao vivo é composta das seguintes partes:

- **Azure Media Services** [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) oferece qualidade de transmissão serviços de fluxo de vídeos para alcançar maiores audiências em dispositivos móveis mais populares de hoje.   Media Services aprimora a acessibilidade, distribuição e escalabilidade e torna fácil e econômico para transmitir conteúdo aos públicos-locais ou em todo o mundo — tudo isso enquanto protegendo seu conteúdo.
- **Rede de fornecimento de conteúdo Azure (CDN)**  Depois que o seu fluxo fica ativo, que é entregue via a [Rede de entrega conteúdo do Windows Azure (CDN)](https://docs.microsoft.com/azure/cdn/). Azure Media Services fornece CDN integrado para streaming de pontos de extremidade. Isso permite que os fluxos sejam exibidas em todo o mundo com nenhum armazenamento em buffer.

### <a name="enterprise-content-delivery-network-ecdn"></a>Rede de entrega de conteúdo corporativo (eCDN)
O objetivo do eCDN é obter o conteúdo de vídeo da internet e distribuir o conteúdo em toda a empresa sem afetar o desempenho da rede. Você pode usar um dos seguintes eCDN parceiros certificados para otimizar sua rede para eventos ao vivo mantidos dentro da sua organização:
    - Hive
    - Kollective
    - Conheça

### <a name="attendee-experience"></a>Experiência do participante 
A experiência do participante é o aspecto mais importante dos eventos ao vivo e é muito importante que os participantes podem participar de evento ao vivo sem a necessidade de quaisquer problemas. A experiência do participante usa o Media Player do Windows Azure e funciona em desktop, navegador e mobile (iOS, Android). O Office 365 fornece Yammer e equipes como dois hubs de colaboração e o nome do participante ao vivo experiência é integrada a essas ferramentas de colaboração. 

## <a name="planning-for-live-events"></a>Planejamento de eventos ao vivo
Quando você estiver planejando eventos ao vivo de equipes para armazenar grandes reuniões em seu organizaiton, há vários fatores que você precisa considerar antes de começar a defini-la sempre para cima. 

### <a name="who-can-create-and-schedule-live-events"></a>Quem pode criar e agendar eventos ao vivo? 
Os seguintes pré-requisitos são necessários para o usuário agendar um evento de equipes ao vivo.

Aqui estão as licenças que devem ser atribuídas:  
- Uma licença do Office 365 Enterprise E1, E3 ou E5 ou uma licença do Office 365 A3 ou A5. 
- Uma Teams da Microsoft, Skype para os negócios e a licença do Microsoft Stream.

É importante saber o que uma licença do Office 365 é necessário para participar de um evento ao vivo como um usuário autenticado, mas isso depende do método de produção usado:

- **Produção para a rápida de iniciar**  O usuário deve ser atribuído a uma licença do Microsoft Teams.
- **Produção de codificador para externo** O usuário deve ser atribuído a uma licença do Microsoft Stream.

Para obter mais informações sobre licenciamento, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).

O usuário deverá ter:
- Agendamento de reuniões privadas em equipes habilitadas (*- AllowPrivateMeetingScheduling TeamsMeetingPolicy o parâmetro = True*).
- Live evento agenda em equipes habilitadas (*- AllowBroadcastScheduling TeamsMeetingBroadcastPolicy o parâmetro = True*).
- Permissões para criar eventos ao vivo no Microsoft Stream (para [produção codificador externo](#production)).

> [!IMPORTANT]
> O Office 365 convidados, usuários federados e anônimos não podem ser convidados como produtores ou apresentadores em equipes de eventos ao vivo. No entanto, o convidado e os usuários federados podem ingressar como participantes anônimos evento ao vivo. 
 
### <a name="who-can-watch-live-events"></a>Quem pode assistir eventos ao vivo?

|**Visibilidade do participante**           |**Início rápido** |**Codificador externo**  |
|------------------------------|-------------|------------------|
|Público (usuários anônimos)      |  Sim        |  Não              |
|Usuários convidados                   |  Não         |  Não              |
|Todos na empresa federada |  Não         |  Não              |
|Todas as pessoas da empresa           |  Sim        |  Sim             |
|Específicas agrupa / de pessoas      |  Sim        |  Sim             |
 
### <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventos ao vivo de equipes e transmissão de reunião do Skype
A tabela a seguir destaca os principais recursos e capacidades oferecidas em eventos ao vivo e como eles diferem da transmissão do Skype reunião. 

|**Recurso**   |**Transmissão de Reunião do Skype** |**Eventos ao vivo de equipes (início rápido)** |**Eventos ao vivo de equipes (codificador externo)** |
|---------|---------|---------|---------|
|Tamanho máximo de audiência |10.000 participantes |10.000 participantes * |10.000 participantes * |
|Criação de evento ao vivo |   Portal de transmissão de reunião do Skype |As equipes, Yammer via equipes | As equipes, Yammer via fluxo, equipes |
|Compromisso de público-alvo – o Yammer |& #x 2714; |& #x 2714; (experiência integrada) |& #x 2714; (experiência integrada) |
|Compromisso de público-alvo – moderados perguntas e respostas |& #x 2714;  |& #x 2714; |& #x 2714; |
|Cliente de produtor no Windows |& #x 2714; (Skype para negócios) |& #x 2714; (As equipes) |& #x 2714; (Stream, equipes via fluxo incorporar) |
|Cliente de produtor no Mac |X  | & #x 2714; (As equipes) |& #x 2714; (Stream, equipes via fluxo incorporar) |
|Contagem de participantes na interface do usuário do produtor |X  |& #x 2714; (As equipes) |& #x 2714; (Stream, equipes via fluxo incorporar) |
|Permite que vários apresentadores |& #x 2714; (Skype para negócios) |& #x 2714; (As equipes) |N/D  |
Convidar um apresentador durante a reunião |& #x 2714; (Skype para negócios) |X |N/D |
|Apresentador de ingresso na Web e dispositivos móveis |& #x 2714; (Skype para negócios)  |X |N/D |
|Apresentador – acesso à PSTN |X |& #x 2714; (As equipes) |N/D |
|Apresentar uma tela |X |& #x 2714; (As equipes) |N/D |
|Apresentar um PowerPoint (compartilhamento de PPT) |& #x 2714; |X (minimizado via compartilhamento de tela) |N/D |
|Gravação de reunião com base na nuvem |& #x 2714; |& #x 2714; |& #x 2714; |
|Auto Publish gravação fluxo da Microsoft |X |X |& #x 2714; |
|Conversão e legendas de Tempo Real |& #x 2714; |& #x 2714; (em breve) |X |
|Legendas em gravações de evento ao vivo |& #x 2714; |& #x 2714; (em breve) |& #x 2714; |
|Controles DVR ATTENDEE (pausar, retroceder) |& #x 2714; |& #x 2714; |& #x 2714; |
|Parceiro eCDN suporte |& #x 2714; (Hive, Kollective, conheça) |& #x 2714; (Hive, Kollective) |& #x 2714; (Hive, Kollective, conheça) |
|Relatório de pós-transmissão de presença para produtores |& #x 2714; |& #x 2714; (versão de recurso) |X |
|Análise de sentimento público-alvo – Live votação & votações |& #x 2714; (Microsoft pulso) |X |X |

> [!IMPORTANT]
> Os limites definidos podem ser alterados.

### <a name="regional-availability"></a>Disponibilidade regional
Você pode usar eventos ao vivo de equipes em vários regiões no mundo inteiro. As informações a seguir mostram a disponibilidade para participantes e os membros da equipe de evento. 

> [!IMPORTANT]
> A região para o evento será selecionada automaticamente dependendo do organizador e a organização do Office 365.

**Disponível nessas regiões**
- Américas
- Europa/África
- Ásia Pacífico
- Vá Canadá Local

**Exclusões e considerações**
- **Ir locais:** Reino Unitied (Reino Unido), Índia e outros locais de ir de equipes da Microsoft não são suportados no momento.
- **China:** Membros da equipe de evento e os participantes não poderão usar eventos ao vivo de equipes, porque o Windows Azure CDN não está acessível na China. Uma solução alternativa é usar uma conexão VPN, que obtém o cliente conectado CDN via rede corporativa do cliente da empresa.

## <a name="setting-up-for-live-events"></a>Configurando para eventos ao vivo
Quando você estiver configurando para eventos ao vivo, há diversas etapas que devem ser executadas:

### <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Etapa 1: Configurar sua rede para live eventos no Microsoft Teams
Os eventos de início rápido ao vivo exigem que você preparar [a rede da sua organização para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).  

### <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
Verifique se você tem as atribuições de licença correta para [quem pode criar e agendar eventos ao vivo?](#who-can-create-and-schedule-live-events) e [quem pode assistir eventos ao vivo?](#who-can-watch-live-events).

### <a name="step-3-enable-live-event-scheduling-for-users"></a>Etapa 3: Habilitar o agendamento de evento ao vivo para usuários
Evento ao vivo agendamento é habilitado por padrão para os usuários de equipes, mas se você estiver buscando os usuários agendem eventos externos codificador há etapas adicionais que você deve fazer.

#### <a name="for-quick-start-events"></a>Eventos de início rápido
Use a configuração *AllowBroadcastScheduling* no **TeamsMeetingBroadcastPolicy** no PowerShell equipes para controlar se o usuário pode criar eventos ao vivo em equipes ou não. Saiba mais sobre como gerenciar TeamsMeetingBroadcastPolicy [aqui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Se você ainda não atribuída uma política personalizada atribuída aos usuários, os usuários receberá a política *Global* , que tem a gravação habilitada por padrão.

Verifique se o parâmetro *AllowBroadcastScheduling* estiver definido como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Atribua o usuário para a política *Global* , execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

##### <a name="user-scenarios"></a>Cenários de usuário
**Você deseja todos os usuários da sua empresa, possam criar eventos ao vivo.**

Se os usuários são atribuídos a política *Glocal* , execute e confirme que *AllowBroadcastScheduling* * estiver definida como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Se os usuários recebem uma política que não seja a política *Global* , execute o seguinte e verificar se a opção *-AllowBroadcastScheduling* está definida como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**Você desejar que o evento ao vivo planejamento ser desabilitado de 100% em sua organização.**

Desabilitar o agendamento de transmissão, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Atribua a todos os usuários em sua organização para a política *Global* , execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Você deseja que um grande número de usuários possam criar eventos ao vivo, mas deseja impedir que um conjunto de usuários criá-los.**

Atribuir a política *Global* usando o **Grant-CsTeamsMeetingBroadcastPolicy** para alguns dos usuários (que você deseja enabled), mas primeiro execute o seguinte e verificar se *AllowBroadcastScheduling* está definida como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Atribua um ou mais usuários à política *Global* , execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Crie e atribua uma diretiva para desabilitar o agendamento usando o cmdlet **Grant-CsTeamsMeetingBroadcastPolicy** para os outros usuários (serem desabilitadas). 

Criar a nova diretiva com ele desabilitada, execute:
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
Desabilitar o agendamento, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
Atribua usuários a essa diretiva, execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**Você deseja eventos ao vivo devem ser desabilitados para um grande número de usuários, mas deseja permitir que um conjunto de usuários para criá-los.**

Desabilitar o agendamento de transmissão, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Em seguida, atribua esses usuários para a política *Global* , execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Criar e atribuir uma política para habilitar o agendamento, execute:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Habilite o agendamento, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Atribua usuários a essa diretiva, execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

#### <a name="for-external-encoder-events"></a>Para eventos externos codificador
Você deve fazer o seguinte procedimento para habilitar o agendamento de evento ao vivo para os usuários.

##### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>Etapa 1: Habilitar o Microsoft Stream para usuários em sua organização * *
Microsoft Stream está disponível como parte das assinaturas do Office 365 elegíveis ou como um serviço autônomo. Para obter mais detalhes, consulte [Visão geral do licenciamento de Stream](https://docs.microsoft.com/stream/license-overview) .

> ! [Nota] Microsoft Stream não está incluído nos planos Business Essentials ou Business Premium.  

Saiba mais sobre como você pode [Atribuir licenças aos usuários no Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que os usuários podem acessar o Microsoft Stream. Certifique-se de que Microsoft Stream não é bloqueado para os usuários conforme definido [neste](https://docs.microsoft.com/stream/disable-user-organization)artigo.

##### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Etapa 2: Verifique se os usuários têm permissão de criação de evento ao vivo na Microsoft Stream * *
Por padrão, os administradores podem criar codificador externa a eventos ao vivo. Administrador do Microsoft Stream pode [Permitir que usuários adicionais para criação de evento ao vivo](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) no fluxo.  

##### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Etapa 3: Verifique se o evento ao vivo organizadores tem consentiu a política da empresa definida pelo fluxo admin * *
Se um administrador do Microsoft Stream [definir uma política de diretrizes da empresa](https://docs.microsoft.com/stream/company-policy-and-consent) e requer funcionários aceitar essa política antes de salvar conteúdo, em seguida, os usuários devem fazer isso antes de criar um evento ao vivo (com a produção de codificador externa) no Microsoft Teams. Antes da distribuição o recurso de eventos ao vivo na organização, certifique-se de tem consentiu usuários que criarão esses eventos ao vivo a política. 

### <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Etapa 4: Configurar o provedor de eCDN para live eventos no Microsoft Teams 
Reprodução de vídeos do evento ao vivo usa a taxa de bits adaptável streaming (ABR), mas é um fluxo de unicast, que significa que cada visualizador está recebendo o seu próprio fluxo de vídeo da internet. Para eventos ao vivo ou vídeos enviados para grandes partes da sua organização, pode haver uma quantidade significativa de largura de banda de internet consumida por visualizadores. Para organizações que desejam reduzir esse tráfego da internet para eventos ao vivo, eventos ao vivo soluções integradas da Microsoft confiam definidos de parceiros de entrega de vídeo oferecem software redes (SDNs) ou redes de fornecimento de conteúdo corporativo (eCDNs). Esses SDN eCDN plataformas permitem que as organizações a otimizar a largura de banda de rede sem prejudicar o usuário final experiências de exibição. Nossos parceiros podem ajudar a habilitar uma distribuição mais flexível e eficiente de vídeo em sua rede corporativa.

**Compra & instalação sua solução fora do Microsoft Teams** Obtenha ajuda especializada com o dimensionamento de entrega de vídeo aproveitando parceiros de entrega confiável de vídeo da Microsoft. Para poder habilitar um provedor de entrega de vídeo ser usado com o Microsoft Teams, você deve adquirir e a solução SDN/eCDN externamente e separada da Microsoft Teams de instalação.

As seguintes soluções SDN/eCDN previamente são integradas e podem ser configurado para ser usado com o Microsoft Stream.

- **Hive Streaming** fornece uma solução simple e eficiente para distribuição de vídeo da empresa ao vivo e sob demanda. Hive é uma solução baseada em software que não exige nenhum hardware adicional ou a largura de banda e fornece uma maneira segura para habilitar milhares de visualizadores de vídeos simultâneos sem afetar a sua rede. Para clientes que desejem para entender que o vídeo do impacto está tendo em sua rede antes da compra de uma solução SDN/eCDN, Hive Streaming também fornece uma solução de análise baseada em navegador para os clientes da Microsoft. [Saiba mais](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
- **Kollective** é uma baseada na nuvem inteligente aos distribuição plataforma, que aproveita a infra-estrutura de rede existente para entregar conteúdo, em vários formulários, (live streaming de vídeo, vídeo sob demanda, atualizações de software, patches de segurança, etc.) com mais rapidamente e confiável e com menos largura de banda. Nossa plataforma segura é confiável por maiores instituições financeiras de todo o mundo e sem hardware adicional, são fáceis de instalação e manutenção. [Saiba mais](http://www.kollective.com)
 
- **Conheça OmniCache** fornece a distribuição de rede de última geração e garante perfeito fornecimento de conteúdo de vídeo entre WANs globais, ajudando produtores de evento otimizar a largura de banda de rede e suporte difusões bem-sucedida evento ao vivo e sob demanda Streaming. O suporte para OmniCache conheça para eventos ao vivo do início rápido estarão disponíveis em breve.  [Saiba mais](http://www.ramp.com) 
 
> [!NOTE] 
> Sua solução eCDN escolhida está sujeito selecionado de **termos do provedor de terceiros 3º da política de privacidade e de serviço**, quais rege o uso da solução do provedor eCDN. O uso da solução do provedor eCDN não estará sujeito a termos de licenciamento de volume do Microsoft ou termos de serviços Online. Se não concordar com os **termos do provedor de terceiros 3º**, não habilite a solução de eCDN no Teams da Microsoft. 

**Configurar um eCDN para "Quick start" eventos ao vivo** Você pode configurar o provedor de eCDN para eventos ao vivo no Teams da Microsoft usando o PowerShell. 

> [!NOTE] 
> Um provedor de eCDN único pode ser configurado para sua organização. 

***Hive*** Você pode usar o cmdlet [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) do PowerShell para configurar o provedor de eCDN. Primeiro, obtenha a URL do modelo ID e a API de licença de seu contato Hive, em seguida, execute o seguinte:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective*** Você pode usar o cmdlet [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) do PowerShell para configurar o provedor de eCDN. Primeiro obter o token de API e a URL do modelo de API do seu contato Kollective, depois, execute o seguinte:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Configurar um eCDN para eventos de "Codificador externo" ao vivo** 

Se você planeja criar eventos ao vivo que usam codificadores externos, você precisará [configurar seu provedor de eCDN com Microsoft Stream](https://docs.microsoft.com/stream/network-caching) também. 

## <a name="configure-live-events"></a>Configurar eventos ao vivo

### <a name="set-up-event-support-link"></a>Configurar o link de suporte do evento
Este é o link que será exibido para os participantes do evento ao vivo. 

No Windows PowerShell, execute o seguinte:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
### <a name="configure-attendee-visibility-options"></a>Configurar opções de visibilidade do participante
Isso permite que os organizadores de evento ao vivo criar eventos com visibilidade attendee apropriado.

|**Valores**  |**Comportamento**  |
|---------|---------|
|Todos     |O usuário tem uma opção para criar eventos ao vivo com a visibilidade de participante a seguir: público, todos na empresa e pessoas específicas. |
|EveryoneInCompany     |O usuário tem uma opção para criar eventos ao vivo com a visibilidade de participante a seguir: todos na empresa e pessoas específicas. O usuário não pode criar eventos ao vivo que podem ser assistidos por usuários anônimos.|
|InvitedUsers |O usuário só pode criar eventos que são limitados a pessoas específicas, como inseridas pelo organizador evento ao vivo. O usuário não pode criar eventos ao vivo com público e todos na autenticação de empresa. |

Use o BroadcastAttendeeVisibility em TeamsMeetingBroadcastPolicy no PowerShell de configuração para controlar se os usuários podem agendar a transmissão de eventos que podem ser observados por participantes anônimos. 

A menos que você atribuiu uma política personalizada para os usuários, os usuários obtêm a política Global, que tem o padrão definido como EveryoneInCompany. 
 
No Windows PowerShell, execute o seguinte procedimento para permitir que usuários criem eventos anônimos na política global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>Configurar opções de gravação
> [!NOTE]
> Essa opção é aplicável a eventos que usam apenas o método de produção de início rápido.

Isso permite que administradores controlar se os eventos ao vivo sempre são registrados, nunca registrados, ou se o organizador de evento pode optar por registrar o evento ou não.  

|**Valores**  |**Comportamento**  |
|---------|---------|
|Sempre habilitada |Os eventos ao vivo organizados pelo usuário sempre são registrados. O usuário não tem uma opção para substituir. Se o evento ao vivo é registrado, os membros da equipe de evento são capazes de fazer o download de gravação após o evento e os participantes podem assistir o evento após o evento está sobre. |
|AlwaysDisabled |Os eventos ao vivo organizados pelo usuário nunca são registrados. O usuário não tem uma opção para substituir. Se o evento ao vivo é registrado, nenhum registro é criado para os membros da equipe de evento e os participantes não podem assistir o evento após ele está sobre. |
|UserOverride |Usuário poderá decidir se o evento ao vivo é registrado para que um arquivo de gravação que pode ser criado para os membros da equipe de evento, e os participantes podem assistir o evento após o evento está sobre. |

Use a configuração *BroadcastRecordingMode* no **TeamsMeetingBroadcastPolicy** no PowerShell ao controle opções dos eventos ao vivo criados pelo organizador evento ao vivo de gravação.

No Windows PowerShell, execute o seguinte cmdlet para atualizar o modo de gravação na política global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Configurar a transcrição em tempo real e uma tradução em eventos ao vivo de equipes (em breve)
> [!NOTE]
> Essa opção é aplicável a eventos que usam apenas o método de produção de início rápido.

Isso permite que os organizadores de evento ao vivo Ativar legendas em tempo real e uma tradução para os participantes do evento ao vivo. 

Use a configuração *AllowBroadcastTranscription* no **TeamsMeetingBroadcastPolicy** no PowerShell para controlar se os participantes do evento ao vivo poderão ver a transcrição e uma tradução. Saiba mais sobre como gerenciar **TeamsMeetingBroadcastPolicy** com o Office 365 PowerShell aqui.  

A menos que você atribuiu uma política personalizada para os usuários, os usuários obtêm a política Global, que tem a transcrição e uma tradução desabilitado por padrão.

No Windows PowerShell, execute o seguinte cmdlet para ativar a transcrição e uma tradução em para os participantes do evento na política global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
### <a name="administrative-tools"></a>Ferramentas administrativas 
Embora a Microsoft diretamente controla todos os centros de dados Online do Office 365 e é responsável pelo desempenho geral do sistema, ele pode controlar apenas uma parte dos elementos que são combinados para fornecer a experiência total para usuários do Office 365. Organizações sozinhos são responsáveis por conexões de rede para os data centers, rede de longa distância (WAN), do cliente e do cliente redes locais (LANs). Além disso, eles estarão responsável por dispositivos de usuário e sua configuração.Eles também são responsável por manter o licenciamento necessários por usuário para qualquer recurso desejado, incluindo, mas não limitado a, a capacidade de gerenciar esses recursos, para desde que o usuário precisar de acesso ao recurso.

Os clientes podem usar as seguintes ferramentas para gerenciar uma variedade de tarefas relacionadas do equipes eventos ao vivo.
- [Centro de administração do Microsoft Office 365](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft Teams e Skype para Business Online admin center](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Centro de administração do Microsoft Stream](https://stream.microsoft.com)
- [Windows PowerShell remoto](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?
Quando se trata de Windows PowerShell, ele é tudo sobre o gerenciamento de usuários e quais os usuários poderão ou não podem para fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e Skype para negócios Online usando um único ponto de administração que pode simplificar o seu trabalho diário quando você tem várias tarefas fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
 - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
 - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

### <a name="related-topics"></a>Tópicos relacionados: 
- [Eventos ao vivo entre Microsoft 365 no Yammer, Teams da Microsoft e Microsoft Stream](https://docs.microsoft.com/stream/live-event-m365)
- [Eventos ao vivo no Microsoft Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Eventos ao vivo no Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Eventos ao vivo em Stream da Microsoft](https://docs.microsoft.com/stream/live-event-overview)
