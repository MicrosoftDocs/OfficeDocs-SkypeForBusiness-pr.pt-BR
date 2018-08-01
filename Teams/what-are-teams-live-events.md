---
title: Quais são as equipes live eventos?
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviwer: tonysmit
description: Saiba como Live eventos permitem aos usuários transmitir vídeo e conteúdo para grandes públicos on-line no Microsoft Teams, Yammer e Microsoft Stream.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8050f105202063a0404de281100deaeca29584d
ms.sourcegitcommit: d802b3091f9dccc851093eed0e2acbc34d1e9d9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2018
ms.locfileid: "21653681"
---
# <a name="what-are-teams-live-events"></a>Quais são as equipes live eventos?
> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Saiba como live eventos permitem aos usuários transmitir vídeo e conteúdo para grandes públicos on-line no Microsoft Teams, Yammer e Microsoft Stream.  

## <a name="overview"></a>Visão geral
Eventos ao vivo no Microsoft 365 habilitar usuários para transmissão de vídeo e de conteúdo para audiências online grandes.  Eventos ao vivo do Microsoft 365 trazem vídeo ao vivo streaming para um novo nível, encorajando conexão em todo o ciclo de vida de compromisso inteira com participantes antes, durante e após eventos ao vivo. Você pode criar um evento ao vivo, onde quer que seu público-alvo, equipe ou comunidades residam, usando o Microsoft Stream, Microsoft Teams ou Yammer.  

Teams da Microsoft oferece a colaboração baseada em bate-papo, chamar, reuniões e com eventos ao vivo, você pode expandir a audiência das suas reuniões. Eventos ao vivo de Teams da Microsoft é uma extensão de reuniões de equipes, permitindo que os usuários transmitir conteúdo de reunião e vídeo para um grande público on-line. Essas servem para comunicações de um-para-muitos onde o host do evento é líder interações e a participação de audiência é principalmente para exibir o conteúdo compartilhado por host. Os participantes podem assistir o evento ao vivo ou gravado no Yammer, equipes e/ou Microsoft Stream e podem interagir com os apresentadores via moderado perguntas e respostas ou conversa do Yammer. 

As equipes de eventos ao vivo é considerada a próxima versão do Skype transmissão de reunião e será eventualmente substituem os recursos fornecidos na transmissão do Skype reunião. Para a versão de demonstração pública de eventos ao vivo, Microsoft continuará dar suporte a transmissão do Skype reunião, sem interrupções no serviço para eventos novos ou futuros. Recomendamos que você experimentar eventos ao vivo em equipes aproveitar os novos recursos, incluindo a tela de compartilhamento, a contagem de participantes e suporte para codificadores de software/hardware externo. 

## <a name="key-components"></a>Principais componentes
O diagrama a seguir mostra os componentes de nível altos envolvidos em eventos ao vivo do Microsoft 365. 

![Eventos ao vivo de equipes](media/teams-live-events.png)

### <a name="scheduling"></a>Agendamento
As equipes fornece a capacidade dos organizadores criar um evento com o nome do participante apropriado permissões, designar os membros da equipe de evento, selecionar produção método convidar participantes. Se o evento ao vivo foi criado de dentro de um grupo do Yammer, os participantes do evento ao vivo poderão usar uma conversa do Yammer para interagir com a equipe de evento. 

### <a name="production"></a>Produção
Os eventos ao vivo no Microsoft 365 oferecem suporte a uma variedade de cenários de produção, inclua um evento de início rápido usando webcams ou um evento do codificador externo com o equipamento de qualidade studio. A entrada de vídeo é a base dos eventos ao vivo e ele pode variar de uma webcam única para a produção de vídeo professional uma câmera multi. Os clientes podem escolher essas opções, dependendo de suas necessidades de projeto e o orçamento. 
- **Início rápido**: O método de inicialização rápida permite aos usuários produzir seus eventos ao vivo usando reuniões de equipes. Esta é a melhor opção se você deseja usar o áudio e vídeos dispositivos conectado ao PC e/ou estão convidando apresentadores remotos / de participação no evento que os participantes. Essa opção permite que os usuários facilmente use seus webcams e compartilhar sua tela como entrada na transmissão. 
- **Codificador externo**: codificadores externos permitir que usuários produzir seus eventos ao vivo diretamente a partir de um hardware externo ou baseada em software codificador com Microsoft Stream. Esta é a melhor opção se você já tiver equipamento de qualidade studio (por exemplo, misturadores de mídia) quais streaming de suporte para um serviço RTMP. Essa opção é geralmente usada nos eventos de grande escala, como executivos corredores da cidade – onde um único fluxo de um mixer de mídia é difundido para a audiência. 

### <a name="streaming-platform"></a>Plataforma de fluxo contínuo
Isso é composto das seguintes partes:

#### <a name="azure-media-services"></a>Azure Media Services
[Azure Media Services](https://docs.microsoft.com/en-us/azure/media-services/previous/) oferece qualidade de transmissão serviços de fluxo de vídeos para alcançar maiores audiências em dispositivos móveis mais populares de hoje. Media Services aprimora a acessibilidade, distribuição e escalabilidade e torna fácil e econômico para transmitir conteúdo aos públicos-locais e em todo o mundo — tudo isso enquanto protegendo seu conteúdo.

#### <a name="azure-content-delivery-network-cdn"></a>Rede de fornecimento de conteúdo Azure (CDN)
Depois que o seu fluxo fica ativo, que é entregue via a [Rede de entrega conteúdo do Windows Azure (CDN)](https://docs.microsoft.com/en-us/azure/cdn/). Azure Media Services fornece CDN integrado para pontos de extremidade streaming. Isso permite que seus fluxos sejam exibidas em todo o mundo com nenhum armazenamento em buffer. 

### <a name="enterprise-content-delivery-network-ecdn"></a>Rede de entrega de conteúdo corporativo (eCDN) 
O objetivo do eCDN é obter o conteúdo de vídeo da internet e distribuir o conteúdo em toda a empresa sem afetar o desempenho da rede. Você pode usar os seguintes parceiros certificados para otimizar sua rede para eventos ao vivo: 
- Hive
- Kollective
- Conheça (em breve ao início rápido)

### <a name="attendee-experience"></a>Experiência do participante
A experiência do participante é o aspecto mais importante dos eventos ao vivo e é muito importante que os participantes podem participar de evento ao vivo sem problemas. A experiência do participante usa o Media Player do Windows Azure e funciona em desktop, navegador e mobile (iOS, Android). O Office 365 fornece Yammer e equipes como dois hubs de colaboração e o nome do participante ao vivo experiência é integrada a essas ferramentas de colaboração. Os eventos ao vivo do codificador externo com base também podem ser acessados pelos participantes no portal do Microsoft Stream.

## <a name="prerequisites"></a>Pré-requisitos

### <a name="who-can-create-live-events"></a>Quem pode criar eventos ao vivo
Os seguintes pré-requisitos são necessários para o usuário agendar um evento ao vivo no período de tempo de visualização:  
- O usuário tem uma licença do Office 365 Enterprise E3 ou E5. 
- Usuário está habilitado for Microsoft Teams, Skype para Business Online e Microsoft Stream.
- Usuário está habilitado para o agendamento de reuniões privadas em equipes (TeamsMeetingPolicy-AllowPrivateMeetingScheduling está definido como True).
- Usuário está habilitado para o agendamento de evento ao vivo em equipes (TeamsMeetingBroadcastPolicy-AllowBroadcastScheduling está definido como True).
- Usuário tem permissões para criar eventos ao vivo no Microsoft Stream (para produção codificador externo).

> [!NOTE]
> O Office 365 convidados, usuários federados e anônimos não podem ser convidados como produtores ou apresentadores em equipes de eventos ao vivo. 
 
### <a name="who-can-watch-live-event"></a>Quem pode assistir ao evento ao vivo
Analise a tabela abaixo para ver quem pode participar de um evento ao vivo. 

|**Visibilidade do participante**           |**Início rápido** |**Codificador externo**  |
|------------------------------|-------------|------------------|
|Público (usuários anônimos)      |  Sim        |  Não              |
|Os usuários convidados *                   |  Não         |  Não              |
|Todos na empresa federada * |  Não         |  Não              |
|Todas as pessoas da empresa           |  Sim        |  Sim             |
|Específicas agrupa / de pessoas      |  Sim        |  Sim             |
* Usuários convidados e federados podem ingressar como participantes anônimos evento ao vivo.

Uma licença do Office 365 é necessária para participar de um evento ao vivo, como um usuário autenticado, dependendo do método de produção.

- **Produção de início para a rápida**: O usuário deve ser um usuário de equipes.
- **Produção de codificador para externo**: O usuário deve ser um usuário Stream.
 
## <a name="capabilities"></a>Recursos
A tabela a seguir destaca os principais recursos oferecidos em eventos ao vivo e como eles diferem da transmissão do Skype reunião. 

|Recurso   |Transmissão de Reunião do Skype |Eventos ao vivo de equipes (início rápido) |Eventos ao vivo de equipes (codificador externo) |
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
|Parceiro eCDN suporte |& #x 2714; (Hive, Kollective, conheça) |& #x 2714; (em breve) |& #x 2714; (Hive, Kollective, conheça) |
|Relatório de pós-transmissão de presença para produtores |& #x 2714; |& #x 2714; (em breve) |X |
|Análise de sentimento público-alvo – Live votação & votações |& #x 2714; (Microsoft pulso) |X |X |

* Os limites são durante a visualização e está sujeita a alterações 

## <a name="planning--setup"></a>Planejamento e instalação
Este artigo explica como você pode configurar usuários com eventos ao vivo de equipes em sua organização.

1. Verifique a [disponibilidade regional para equipes live eventos](#configure-live-events) para entender as regiões eventos ao vivo estão atualmente disponíveis no.
2. Se você ainda não tiver feito isso, configure [Skype para Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online?redirectSourcePath=%252fen-us%252farticle%252fset-up-skype-for-business-online-40296968-e779-4259-980b-c2de1c044c6e) para a sua organização.
3. Se você tiver participantes ingressando a partir da rede corporativa, considere a possibilidade de inclusão e [Configurar um provedor de eCDN - recomendadas pela Microsoft](#set-up-ecdn-provider-for-teams-live-events) para otimizar sua largura de banda de rede. 
4. Certifique-se de que você tenha atribuições de licença correta para [quem pode criar eventos ao vivo](#who-can-create-live-events) e [quem pode Assista eventos ao vivo](#who-can-watch-live-event). 
5. [Habilite o agendamento de evento ao vivo](#enable-live-event-scheduling-for-the-user) para os usuários que deve ser capaz de criar eventos ao vivo na sua empresa. Isso é necessário para o início rápido & a eventos externos codificador. 
6. Para eventos externos codificador, [habilitar usuários para a criação de eventos ao vivo no Portal de administração do Microsoft Stream](#enable-microsoft-stream-for-users-in-the-organization).  

### <a name="regional-availability-for-teams-live-events"></a>Disponibilidade regional para equipes de eventos ao vivo
Você pode usar eventos ao vivo de equipes em várias regiões. As informações a seguir mostram a disponibilidade para participantes e os membros da equipe de evento. A região para o evento será selecionada automaticamente dependendo do organizador e inquilino do Office 365.

#### <a name="regions-available"></a>Regiões disponíveis
- Américas
- Europa/África
- Ásia Pacífico

#### <a name="exclusions"></a>Exclusões
- Vá variáveis locais
  - Reino Unido, Índia e outros locais de ir de equipes da Microsoft não são suportados no momento.
- Vá Local - Canadá 
  - No modo de visualização, os clientes podem criar eventos mas seus dados serão hospedados na região da América do Norte.
- China
  - Membros da equipe de evento e os participantes não poderão usar eventos ao vivo de equipes, porque o Windows Azure CDN não está acessível na China. Uma solução alternativa é usar uma conexão VPN, que obtém o cliente conectado CDN via rede corporativa do cliente da empresa.

### <a name="set-up-your-network-for-live-events-in-microsoft-teams"></a>Configurar sua rede para live eventos no Microsoft Teams
Os eventos de início rápido ao vivo exigem que você preparar [a rede da sua organização para equipes da Microsoft](https://docs.microsoft.com/en-us/microsoftteams/prepare-network).  

Para o início rápido e eventos ao vivo do codificador externo 

### <a name="set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Configurar o provedor de eCDN para live eventos no Microsoft Teams 
Reprodução de vídeos do evento ao vivo usa a taxa de bits adaptável streaming (ABR), mas é um fluxo de unicast, que significa que cada visualizador está recebendo o seu próprio fluxo de vídeo da internet. Para eventos ao vivo ou vídeos enviados para grandes partes da sua organização, pode haver uma quantidade significativa de largura de banda de internet consumida por visualizadores.  Para organizações que desejam reduzir esse tráfego da internet para eventos ao vivo, eventos ao vivo soluções integradas da Microsoft confiam definidos de parceiros de entrega de vídeo oferecem software redes (SDNs) ou redes de fornecimento de conteúdo corporativo (eCDNs). Esses SDN eCDN plataformas permitem que as organizações a otimizar a largura de banda de rede sem prejudicar o usuário final experiências de exibição. Nossos parceiros podem ajudar a habilitar uma distribuição mais flexível e eficiente de vídeo em sua rede corporativa.

#### <a name="purchase--setup-your-solution-outside-of-microsoft-teams"></a>Comprar & sua solução fora do Microsoft Teams de instalação
Obtenha ajuda especializada com o dimensionamento de entrega de vídeo aproveitando parceiros de entrega confiável de vídeo da Microsoft.  Para poder habilitar um provedor de entrega de vídeo ser usado com o Microsoft Teams, você deve adquirir e a solução SDN/eCDN externamente e separada da Microsoft Teams de instalação.

As seguintes soluções SDN/eCDN previamente são integradas e podem ser configurado para ser usado com o Microsoft Stream. Consulte as informações dos provedores abaixo:

Streaming de hive fornece uma solução de simple e eficiente para distribuição de vídeo da empresa ao vivo e sob demanda. Hive é uma solução baseada em software que não exige nenhum hardware adicional ou a largura de banda e fornece uma maneira segura para habilitar milhares de visualizadores de vídeos simultâneos sem afetar a sua rede. Para clientes que desejem para entender que o vídeo do impacto está tendo em sua rede antes da compra de uma solução SDN/eCDN, Hive Streaming também fornece uma solução de análise baseada em navegador para os clientes da Microsoft. [Saiba mais](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
Inteligente, baseada na nuvem aos distribuição plataforma do Kollective aproveita a infra-estrutura de rede existente para entregar conteúdo, em vários formulários, (live streaming de vídeo, vídeo sob demanda, atualizações de software, patches de segurança, etc.) mais rápido e mais confiável e com menos largura de banda. Nossa plataforma segura é confiável por maiores instituições financeiras de todo o mundo e sem hardware adicional, são fáceis de instalação e manutenção. [Saiba mais](http://www.kollective.com)
 
Conheça OmniCache fornece a distribuição de rede de última geração e garante a perfeita fornecimento de conteúdo de vídeo entre WANs globais, ajudando produtores de evento otimizar a largura de banda de rede e suporte de transmissões de evento ao vivo bem-sucedida e streaming sob demanda. O suporte para OmniCache conheça para eventos ao vivo do início rápido estarão disponíveis em breve.  [Saiba mais](http://www.ramp.com) 
 
[!NOTE] Sua solução eCDN escolhida está sujeito selecionado de [termos do provedor de terceiros 3º da política de privacidade e de serviço](), que orientará sua utilização da solução do provedor eCDN. O uso da solução do provedor eCDN não estará sujeito a termos de licenciamento de volume do Microsoft ou termos de serviços Online. Se não concordar com os [termos do provedor de terceiros 3º](), não habilite a solução de eCDN no Teams da Microsoft. 

#### <a name="configure-ecdn-for-quick-start-live-events"></a>Configurar eCDN para eventos de "Quick start" ao vivo 
Você pode configurar o provedor de eCDN para eventos ao vivo no Microsoft Teams via PowerShell. Observação: apenas um provedor de eCDN único pode ser configurado para o locatário a qualquer momento. 

**Configurar Hive eCDN provedor** 

Você pode usar o cmdlet [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) do PowerShell para configurar o provedor de eCDN. 
1. Obter a URL do modelo de licença ID e a API do seu contato Hive. 
2. Execute o seguinte cmdlet do PowerShell
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```

**Configurar Kollective eCDN provedor** 

Você pode usar o cmdlet [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) do PowerShell para configurar o provedor de eCDN. 
1. Obter o token de API e a URL do modelo de API do seu contato Kollective. 
2. Execute o seguinte cmdlet do PowerShell
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```

**Configurar conheça eCDN provedor**

#### <a name="configure-ecdn-for-external-encoder-live-events"></a>Configurar eCDN para eventos de "Codificador externo" ao vivo 
Se você planeja criar eventos ao vivo que usam codificadores externos, você precisará [configurar seu provedor de eCDN com Microsoft Stream](https://docs.microsoft.com/stream/network-caching) também. Se você planeja criar "Quick start" eventos ao vivo por meio de Teams da Microsoft ou Yammer, você precisará configurar seu provedor SDN/eCDN sejam integrados ao Microsoft Teams também.

### <a name="enable-live-event-scheduling-for-the-user"></a>Habilite o agendamento de evento ao vivo para o usuário
O agendamento de evento ao vivo é habilitado por padrão para um usuário de equipes.  

Use a configuração AllowBroadcastScheduling no TeamsMeetingBroadcastPolicy no PowerShell equipes para controlar se o usuário pode criar eventos ao vivo em equipes ou não. Saiba mais sobre como gerenciar TeamsMeetingBroadcastPolicy com o Office 365 PowerShell [aqui](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 A menos que você atribuiu uma política personalizada para os usuários, os usuários obtêm a política Global, que tem a gravação habilitada por padrão. 

 Para um usuário fallback Política Global, use o seguinte cmdlet para remover uma atribuição de política específicas de um usuário.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Para alterar o valor de AllowBroadcastScheduling na Política Global, use o seguinte cmdlet:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastScheduling $false
```
#### <a name="scenarios"></a>Cenários
**Desejo que todos os usuários da minha empresa, possam criar eventos ao vivo.**
1. Confirme CsTeamsMeetingBroadcastPolicy Global tem AllowBroadcastScheduling = True.
2. Confirmar todos os usuários têm o Global OR CsTeamsMeetingBroadcastPolicy uma das políticas CsTeamsMeetingBroadcastPolicy com AllowBroadcastScheduling = True.

**Desejo que a maioria dos meus usuários possam criar eventos ao vivo, mas eu quiser desabilitar seletivamente usuários específicos que não é permitido.**
1. Confirme CsTeamsMeetingBroadcastPolicy Global tem AllowBroadcastScheduling = True.
2. Confirmar a maioria dos usuários têm o Global OR CsTeamsMeetingBroadcastPolicy uma das políticas CsTeamsMeetingBroadcastPolicy com AllowBroadcastScheduling = True.
3. Confirmar todos os outros usuários receberam uma das políticas CsTeamsMeetingBroadcastPolicy com AllowBroadcastScheduling = False.

**Deseja que o agendamento de evento ao vivo a ser desabilitado de 100%.**
1. Confirme CsTeamsMeetingBroadcastPolicy Global tem AllowBroadcastScheduling = False.
2. Confirmar todos os usuários que tiverem sido concedidos a Global CsTeamsMeetingBroadcastPolicy OR uma das políticas CsTeamsMeetingBroadcastPolicy com AllowBroadcastScheduling = False.

**Eu quero eventos ao vivo para ser desabilitados para a maioria dos usuários, mas ativar seletivamente a usuários específicos para eventos ao vivo.** 
1. Confirme CsTeamsMeetingBroadcastPolicy Global tem AllowBroadcastScheduling = False.
2. Confirme que a maioria dos usuários que tiverem sido concedidas a Global CsTeamsMeetingBroadcastPolicy OR uma das políticas CsTeamsMeetingBroadcastPolicy com AllowBroadcastScheduling = False.
3. Confirmar todos os outros usuários receberam uma das políticas CsTeamsMeetingBroadcastPolicy com AllowBroadcastScheduling = True.

### <a name="enable-creation-of-external-encoder-based-live-events-for-users"></a>Habilitar a criação baseada em codificador live eventos externos para usuários

#### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Habilitar o Microsoft Stream para os usuários da organização
Microsoft Stream está disponível como parte das assinaturas do Office 365 elegíveis ou como um serviço autônomo. Para obter mais detalhes, consulte [Visão geral do licenciamento de Stream](https://docs.microsoft.com/en-us/stream/license-overview) . Observação Microsoft Stream não está incluído nos planos Business Essentials ou Business Premium.  

Saiba mais sobre como você pode [Atribuir licenças aos usuários no Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que os usuários podem acessar o Microsoft Stream. Certifique-se de que Microsoft Stream não é bloqueado para os usuários conforme definido [neste](https://docs.microsoft.com/en-us/stream/disable-user-organization)artigo.

#### <a name="ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Certifique-se de que os usuários têm permissão de criação de evento ao vivo em Stream da Microsoft
Por padrão, todos na empresa podem criar conteúdo em Stream, depois que o Stream está habilitado e uma licença está atribuída ao usuário. Administrador do Microsoft Stream pode [restringir funcionários para a criação de conteúdo](https://docs.microsoft.com/en-us/stream/restrict-uploaders) no fluxo. Os usuários que estão nesta lista restritos não poderão gravar reuniões.

#### <a name="ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Certifique-se de tem consentiu organizadores a diretiva de empresa definida pelo administrador do fluxo de evento ao vivo
Se um administrador do Microsoft Stream [definir uma política de diretrizes da empresa](https://docs.microsoft.com/en-us/stream/company-policy-and-consent) e requer funcionários aceitar essa política antes de salvar conteúdo, em seguida, os usuários devem fazer isso antes de criar um evento ao vivo (com a produção de codificador externa) no Microsoft Teams. Antes da distribuição o recurso de eventos ao vivo na organização, certifique-se de tem consentiu usuários que criarão esses eventos ao vivo a política. 

## <a name="configure-live-events"></a>Configurar eventos ao vivo

### <a name="set-up-event-support-link-coming-soon"></a>Configurar o link de suporte de evento (em breve)
Este é o link que será exibido para os participantes do evento ao vivo. 

PowerShell

No Windows PowerShell, execute o seguinte cmdlet:
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

PowerShell

Use o BroadcastAttendeeVisibility em TeamsMeetingBroadcastPolicy no PowerShell de configuração para controlar se os usuários podem agendar a transmissão de eventos que podem ser observados por participantes anônimos. Saiba mais sobre como gerenciar TeamsMeetingBroadcastPolicy com o Office 365 PowerShell aqui.  

A menos que você atribuiu uma política personalizada para os usuários, os usuários obtêm a política Global, que tem o padrão definido como EveryoneInCompany. 
 
No Windows PowerShell, execute o seguinte cmdlet para permitir que usuários criem eventos anônimos na política global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>Configurar opções de gravação
> [!NOTE]
> Essa opção é aplicável a eventos que usam o método de produção do início rápido somente.

Isso permite que administradores controlar se os eventos ao vivo sempre são registrados, nunca registrada ou o organizador de evento pode optar por registrar o evento ou não.  

|**Valores**  |**Comportamento**  |
|---------|---------|
|Sempre habilitada |Os eventos ao vivo organizados pelo usuário sempre são registrados. Usuário não tem uma opção para substituir. Se o evento ao vivo é registrado, os membros da equipe de evento são capazes de fazer o download de gravação após o evento e os participantes podem assistir o evento após o evento está sobre. |
|AlwaysDisabled |Os eventos ao vivo organizados pelo usuário nunca são registrados. Usuário não tem uma opção para substituir. Se o evento ao vivo é registrado, nenhum registro é criado para os membros da equipe de evento e os participantes não podem assistir o evento após ele está sobre. |
|UserOverride |Usuário poderá decidir se o evento ao vivo é registrado para um arquivo de gravação que pode ser criado para os membros da equipe de evento e os participantes podem Assista o evento após o evento está sobre. |

PowerShell

Use a configuração BroadcastRecordingMode no TeamsMeetingBroadcastPolicy no PowerShell ao controle opções dos eventos ao vivo criados pelo organizador evento ao vivo de gravação.

No Windows PowerShell, execute o seguinte cmdlet para atualizar o modo de gravação na política global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Configurar a transcrição em tempo real e uma tradução em eventos ao vivo de equipes (em breve)
> [!NOTE]
> Essa opção é aplicável a eventos que usam o método de produção do início rápido somente.

Isso permite que os organizadores de evento ao vivo Ativar legendas em tempo real e uma tradução para os participantes do evento ao vivo. 

PowerShell

Use a configuração AllowBroadcastTranscription no TeamsMeetingBroadcastPolicy no PowerShell para controlar se os participantes do evento ao vivo poderão ver a transcrição e uma tradução. Saiba mais sobre como gerenciar TeamsMeetingBroadcastPolicy com o Office 365 PowerShell aqui.  

A menos que você atribuiu uma política personalizada para os usuários, os usuários obtêm a política Global, que tem transcrição & tradução desabilitado por padrão.

No Windows PowerShell, execute o seguinte cmdlet para ativar a transcrição e uma tradução em para os participantes do evento na política global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="self-service-administration-tools"></a>Ferramentas de administração de autoatendimento 
Embora a Microsoft diretamente controla todos os centros de dados Online do Office 365 e é responsável pelo desempenho geral do sistema, ele pode controlar apenas uma parte dos elementos que são combinados para fornecer a experiência total para usuários do Office 365. Organizações sozinhos são responsáveis por conexões de rede para os data centers, rede de longa distância (WAN), do cliente e do cliente redes locais (LANs). Além disso, eles estarão responsável por dispositivos de usuário e sua configuração.Eles também são responsável por manter o licenciamento necessários por usuário para qualquer recurso desejado, incluindo, mas não limitado a, a capacidade de gerenciar esses recursos, para desde que o usuário precisar de acesso ao recurso.

Os clientes podem usar as seguintes ferramentas para gerenciar uma variedade de tarefas relacionadas do equipes eventos ao vivo.
- [Centro de administração do Microsoft Office 365](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft Teams e Skype para Business Online admin center](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- Centro de administração do Microsoft Stream
- [Windows PowerShell remoto](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?
- Quando se trata de Windows PowerShell, ele é tudo sobre o gerenciamento de usuários e quais os usuários poderão ou não podem para fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)


### <a name="related-topics"></a>Tópicos relacionados: 

- [Eventos ao vivo entre Microsoft 365 no Yammer, Teams da Microsoft e Microsoft Stream](https://docs.microsoft.com/stream/live-event-m365)
- [Eventos ao vivo no Microsoft Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Eventos ao vivo no Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Eventos ao vivo em Stream da Microsoft](https://review.docs.microsoft.com/stream/live-event-overview)