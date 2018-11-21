---
title: Configurar eventos ao vivo no Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Conheça as etapas para configurar ao vivo de eventos em equipes, incluindo Otimize sua rede, como atribuir licenças, usando diretivas para habilitar os recursos de evento ao vivo e agendamento para usuários e configurando um provedor de distribuição de terceiros.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fe13722bfc8b5aa7a9f57d0dfd39c67146e6c31
ms.sourcegitcommit: ff0c4bef4d4cbc71d51fce941aff63739a0016e9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2018
ms.locfileid: "26626266"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configurar eventos ao vivo no Microsoft Teams

> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Quando você estiver configurando para eventos ao vivo, há diversas etapas que devem ser executadas:

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Etapa 1: Configurar sua rede para live eventos no Microsoft Teams
Eventos de início rápido ao vivo exigem que você preparar [a rede da sua organização para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
Certifique-se de que você tenha atribuições de licença correta para [quem pode criar e agendar eventos ao vivo](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events) e [quem pode Assista eventos ao vivo](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Etapa 3: Configurar políticas de eventos ao vivo
Eventos ao vivo, elas são usadas para controlar quem na sua organização pode conter eventos ao vivo e os recursos que estão disponíveis nos eventos que eles criam. Você pode usar a política padrão ou, em seguida, criar um ou mais personalizada live políticas de eventos. Depois de criar uma política personalizada, atribuí-lo a um usuário ou grupos de usuários em sua organização.

> [!NOTE]
> Usuários em sua organização receberá a política global, a menos que você criar e atribuir uma política personalizada. Por padrão na política global, agendamento de evento ao vivo está habilitada para usuários de equipes, transcrições estiver desativada, todos na organização podem ingressar em eventos ao vivo e a configuração de gravação estiver definida para registrar sempre. 

### <a name="create-or-edit-a-live-events-policy"></a>Criar ou editar uma política de eventos ao vivo

**![as equipes de logotipo-30x30.png](../media/teams-logo-30x30.png) usando o Microsoft Teams & Skype para centro de administração de negócios**

1. No painel de navegação esquerdo, vá para **reuniões** > **políticas de eventos ao vivo**. 
2. Siga um destes procedimentos:
- Se você deseja editar a política padrão existente, escolha **Global (padrão de toda a organização)**. 
- Se você quiser criar uma nova política personalizada, selecione **nova política**. 
- Se você deseja editar uma política personalizada, selecione a política e escolha **Editar**. 

    Aqui estão as configurações que podem ser alteradas para atender às necessidades da sua organização.

    ![Captura de tela de configurações de diretiva de eventos do live] (../media/teams-live-events-policies.png "Captura de tela do live configurações de política de eventos no Microsoft equipes & Skype para centro de administração de negócios") 

|Configuração  |Descrição  |
|---------|---------|
|**Nome**     |Este é o nome da política que aparece na página de políticas de eventos ao vivo. Ele não pode ter mais de 64 caracteres ou ter quaisquer caracteres especiais.          |
|**Descrição**    |Use esta opção para adicionar uma descrição amigável para a política.         |
|**Permitir o agendamento**     |Ativando Isso permite que os usuários em sua organização criar e agendar eventos ao vivo em equipes. É importante saber que, se desejar que os usuários agendem eventos ao vivo do codificador externo, há etapas adicionais que você deve fazer. Para saber mais, consulte [habilitar usuários agendar a eventos externos codificador](#enable-users-to-schedule-external-encoder-events).     |
|**Permitir transcrição para participantes** (em breve) |Essa configuração só pode ser aplicada aos eventos de início rápido. Ativem Isso permite que os participantes do evento ao vivo ver as legendas em tempo real e uma tradução durante o evento.         |
|**Quem pode ingressar eventos ao vivo agendados**    |Escolha uma das opções a seguir.<br> <br> **Todos** Os usuários podem criar eventos ao vivo que todos, incluindo pessoas fora da sua organização, podem participar. <br> **Todas as pessoas na organização** Os usuários podem criar eventos ao vivo que apenas as pessoas da sua organização podem participar. Os usuários não podem criar live eventos que são assistidos por usuários anônimos. <br> **Usuários ou grupos específicos** Os usuários podem criar eventos ao vivo que apenas usuários específicos ou grupos em sua organização podem participar. Os usuários não podem criar live eventos que são assistidos por todos os usuários em sua organização ou por usuários anônimos.        |
|**Configuração de gravação**  <br>     | Essa configuração só pode ser aplicada aos eventos de início rápido. Escolha uma das opções a seguir. <br><br> **Registre sempre** Eventos ao vivo criados por usuários sempre são registrados. Após o evento via, membros da equipe de evento podem baixar a gravação e os participantes podem Assista o evento. <br> **Nunca registrar** Eventos ao vivo criados por usuários nunca são registrados. <br>**Organizador pode registrar ou não** Os usuários podem decidir se deseja gravar o evento ao vivo. Se ele está gravado, depois que o evento está sobre, membros da equipe de evento podem baixar a gravação e participantes possam assistir o evento.      

Você também pode fazer isso usando o Windows PowerShell. Para obter mais informações, consulte [Usar o PowerShell para definir políticas de eventos ao vivo em equipes](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Atribuir uma política de eventos ao vivo aos usuários 

Se você criou uma política personalizada de eventos ao vivo, atribuí-lo aos usuários para a política estejam ativos. 

![as equipes de logotipo-30x30.png](../media/teams-logo-30x30.png) Usando o Microsoft Teams & Skype para centro de administração de negócios

1. No painel de navegação esquerdo, vá para **usuários**e, em seguida, selecione o usuário.
2. Ao lado de **políticas atribuído**, escolha **Editar**. 
3. Selecione a política de eventos ao vivo que você deseja atribuir e, em seguida, escolha **Salvar**. 

### <a name="enable-users-to-schedule-external-encoder-events"></a>Habilitar os usuários agendem eventos externos codificador

Para os usuários agendem eventos codificador externo, você deve também faça o seguinte:

1. Habilite o Microsoft Stream para usuários em sua organização. Microsoft Stream está disponível como parte das assinaturas do Office 365 elegíveis ou como um serviço autônomo. Microsoft Stream não está incluído nos planos Business Essentials ou Business Premium. Para obter mais detalhes, consulte [Visão geral do licenciamento de Stream](https://docs.microsoft.com/stream/license-overview) .

      Saiba mais sobre como você pode [Atribuir licenças aos usuários no Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que os usuários podem acessar o Microsoft Stream. Certifique-se de que Microsoft Stream não é bloqueado para os usuários conforme definido [neste](https://docs.microsoft.com/stream/disable-user-organization)artigo.

2. Certifique-se de que os usuários têm permissão de criação de evento ao vivo em Microsoft Stream. Por padrão, os administradores podem criar codificador externa a eventos ao vivo. Administrador do Microsoft Stream pode [Permitir que usuários adicionais para criação de evento ao vivo](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) no fluxo.  

3. Verifique se o evento ao vivo organizadores tem consentiu a diretiva de empresa definida pelo administrador do Stream. Se um administrador do Microsoft Stream [definir uma política de diretrizes da empresa](https://docs.microsoft.com/stream/company-policy-and-consent) e requer funcionários aceitar essa política antes de salvar conteúdo, em seguida, os usuários devem fazer isso antes de criar um evento ao vivo (com a produção de codificador externo) em equipes. Antes de você distribuir o recurso de eventos ao vivo na organização, certifique-se de tem consentiu usuários que criarão esses eventos ao vivo a política. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Etapa 4: Configurar uma solução de distribuição de vídeo para eventos ao vivo em equipes
Reprodução de vídeos do evento ao vivo usa a taxa de bits adaptável streaming (ABR), mas é um fluxo de unicast, que significa que cada visualizador está recebendo o seu próprio fluxo de vídeo da internet. Para eventos ao vivo ou vídeos enviados para grandes partes da sua organização, pode haver uma quantidade significativa de largura de banda de internet consumida por visualizadores. Para organizações que desejam reduzir esse tráfego da internet para eventos ao vivo, eventos ao vivo soluções integradas da Microsoft confiam definidos de parceiros de entrega de vídeo oferecem software redes (SDNs) ou redes de fornecimento de conteúdo corporativo (eCDNs). Essas plataformas SDN/eCDN permitem que as organizações otimizar a largura de banda de rede sem prejudicar o usuário final experiências de exibição. Nossos parceiros podem ajudar a habilitar uma distribuição mais flexível e eficiente de vídeo em sua rede corporativa.

**Compra e configurar sua solução fora de equipes** Obtenha ajuda especializada com o dimensionamento de entrega de vídeo aproveitando parceiros de entrega confiável de vídeo da Microsoft. Para poder habilitar um provedor de entrega de vídeo ser usado com equipes, você deve adquirir e configurar a solução SDN/eCDN externamente e separada das equipes.

As seguintes soluções SDN/eCDN previamente são integradas e podem ser configuradas para ser usado com o Microsoft Stream.

- **Hive Streaming** fornece uma solução simple e eficiente para distribuição de vídeo da empresa ao vivo e sob demanda. Hive é uma solução baseada em software que não exige nenhum hardware adicional ou a largura de banda e fornece uma maneira segura para habilitar milhares de visualizadores de vídeos simultâneos sem afetar a sua rede. Para clientes que desejem para entender que o vídeo do impacto está tendo em sua rede antes da compra de uma solução SDN/eCDN, Hive Streaming também fornece uma solução de análise baseada em navegador para os clientes da Microsoft. [Saiba mais](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** é uma baseada na nuvem inteligente aos distribuição plataforma, que aproveita a infra-estrutura de rede existente para entregar conteúdo, em vários formulários, (live streaming de vídeo, vídeo sob demanda, atualizações de software, patches de segurança, etc.) com mais rapidamente e confiável e com menos largura de banda. Nossa plataforma segura é confiável por maiores instituições financeiras de todo o mundo e sem hardware adicional, são fáceis de instalação e manutenção. [Saiba mais](http://www.kollective.com).
 
- **Conheça OmniCache** fornece a distribuição de rede de última geração e garante perfeito fornecimento de conteúdo de vídeo entre WANs globais, ajudando produtores de evento otimizar a largura de banda de rede e suporte difusões bem-sucedida evento ao vivo e sob demanda Streaming. O suporte para OmniCache conheça para eventos ao vivo do início rápido estarão disponíveis em breve.  [Saiba mais](http://www.ramp.com). 
 
> [!NOTE] 
> Sua solução SDN ou eCDN escolhida está sujeito selecionado de **termos do provedor de terceiros 3º da política de privacidade e de serviço**, quais rege o uso da solução do provedor. O uso da solução do provedor não estará sujeito a termos de licenciamento de volume do Microsoft ou termos de serviços Online. Se não concordar com os **termos do provedor de terceiros 3º**, não habilite a solução em equipes. 

Depois de configurar a solução SDN ou eCDN, você está pronto para configurar o provedor para eventos ao vivo em equipes. 

## <a name="next-steps"></a>Próximos passos
Vá para [Configure live em equipes nas configurações dos eventos](configure-teams-live-events.md).

### <a name="related-topics"></a>Tópicos relacionados
- [Quais são as equipes live eventos?](what-are-teams-live-events.md)
- [Planejamento de eventos ao vivo de equipes](plan-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo em equipes](configure-teams-live-events.md)

