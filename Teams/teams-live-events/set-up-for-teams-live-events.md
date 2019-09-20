---
title: Configurar eventos ao vivo no Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Aprenda as etapas para configurar o Live para eventos no Teams, incluindo a preparação da rede, a atribuição de licenças, o uso de políticas para habilitar recursos de eventos dinâmicos e agendamento para usuários e a configuração de um provedor de distribuição de terceiros.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 973e079cda665005dac55e466d444b09ecddb7da
ms.sourcegitcommit: a6e44256c024fc3953cfd6a511ee024c4c7b8408
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047066"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configurar eventos ao vivo no Microsoft Teams

Quando você está configurando para eventos ao vivo, há várias etapas que devem ser tomadas.

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>Etapa 1: configurar sua rede para eventos dinâmicos no Microsoft Teams
Eventos dinâmicos produzidos em equipes exigem que você [Prepare a rede da sua organização para o Teams](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
Verifique se você tem atribuições de licença corretas para [quem pode criar e agendar eventos dinâmicos](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events) e [quem pode assistir a eventos ao vivo](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Etapa 3: configurar políticas de eventos dinâmicos
Políticas de eventos dinâmicos são usadas para controlar quem em sua organização pode manter eventos dinâmicos e os recursos que estão disponíveis nos eventos que eles criam. Você pode usar a política padrão ou criar uma ou mais políticas personalizadas de eventos dinâmicos. Depois de criar uma política personalizada, atribua-a a um usuário ou grupos de usuários em sua organização.

> [!NOTE]
> Os usuários em sua organização receberão a política global, a menos que você crie e atribua uma política personalizada. Por padrão, na política global, o agendamento de eventos dinâmicos está habilitado para usuários do Teams, legendas ao vivo e legendas (transcrição) desativada, todos na organização podem participar de eventos dinâmicos e a configuração de gravação é definida como sempre gravar. 

### <a name="create-or-edit-a-live-events-policy"></a>Criar ou editar uma política de eventos dinâmicos
<a name="bkcreatepolicy"> </a>

**![Um ícone mostrando o logotipo](../media/teams-logo-30x30.png) do Microsoft Teams usando o centro de administração do Microsoft Teams**

1. No painel de navegação esquerdo, vá para**políticas de eventos dinâmicos**de **reuniões** > . 
2. Siga um destes procedimentos:
- Se você quiser editar a política padrão existente, escolha **global (padrão para toda a organização)**. 
- Se você quiser criar uma nova política personalizada, escolha **nova política**. 
- Se você quiser editar uma política personalizada, selecione a política e, em seguida, escolha **Editar**. 

    Aqui estão as configurações que você pode alterar de acordo com as necessidades da sua organização.

    ![Captura de tela de configurações de política de eventos dinâmicos](../media/teams-live-events-policies.png "captura de tela das configurações de política de eventos dinâmicos no centro de administração do Microsoft Teams") 

|Configuração  |Descrição  |
|---------|---------|
|**Título**     |Esse é o título da política exibida na página políticas de eventos dinâmicos. Não pode ter mais de 64 caracteres ou ter caracteres especiais.          |
|**Descrição**    |Use isso para adicionar uma descrição amigável à política.         |
|**Permitir agendamento**     |Ativar isso permite que os usuários em sua organização criem e agendem eventos dinâmicos no Teams. É importante saber que, se você quiser que os usuários agendem um evento ao vivo produzido com um aplicativo ou dispositivo externo, há etapas adicionais que você deve fazer. Para saber mais, confira [habilitar usuários para agendar eventos que foram produzidos com um aplicativo ou dispositivo externo](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).     |
|**Permitir transcrição para participantes** |Essa configuração só pode ser aplicada a eventos produzidos no Teams. Ativar isso permite que os participantes de eventos dinâmicos vejam legendas e legendas ao vivo durante o evento.         |
|**Quem pode participar de eventos dinâmicos programados**    |Escolha uma das opções a seguir.<br><br>**Todas as pessoas** Os usuários podem criar eventos dinâmicos que todos, incluindo pessoas de fora da sua organização, podem participar. Essa configuração habilita o tipo de permissão **pública** no Teams quando um usuário agenda um evento ao vivo.<br> **Todos na organização** Os usuários podem criar eventos dinâmicos que as pessoas em sua organização, incluindo [os usuários convidados](../add-guests.md) adicionados à sua organização, podem participar. Os usuários não podem criar eventos dinâmicos que participem de usuários anônimos. Essa configuração habilita o tipo de permissão de **toda a organização** no Teams quando um usuário agenda um evento ao vivo.<br> **Usuários ou grupos específicos** Os usuários podem criar eventos dinâmicos que apenas usuários ou grupos específicos em sua organização podem participar. Os usuários não podem criar eventos dinâmicos que participem de todos em sua organização ou de usuários anônimos. Essa configuração habilita o tipo de permissão **pessoas e grupos** no Teams quando um usuário agenda um evento ao vivo.       |
|**Configuração de gravação**  <br>     | Essa configuração só pode ser aplicada a eventos produzidos no Teams. Escolha uma das opções a seguir. <br><br> **Sempre gravar** Os eventos dinâmicos criados por usuários são sempre gravados. Após o evento terminar, os membros da equipe de eventos podem baixar a gravação e os participantes podem assistir ao evento. <br> **Nunca gravar** Os eventos dinâmicos criados pelos usuários nunca são gravados. <br>**Organizador pode gravar ou não** Os usuários podem decidir se desejam registrar o evento ao vivo. Se for gravada, depois que o evento terminar, os membros da equipe de eventos poderão baixar a gravação e os participantes poderão assistir ao evento.      

Você também pode fazer isso usando o Windows PowerShell. Para obter mais informações, consulte [usar o PowerShell para definir políticas de eventos dinâmicos no Microsoft Teams](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Atribuir uma política de eventos ao vivo aos usuários 

Se você criou uma política personalizada de eventos dinâmicos, atribua-a a usuários para que a política seja ativada. 

![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) Usar o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá para **usuários**e selecione o usuário.
2. Ao lado de **políticas atribuídas**, escolha **Editar**. 
3. Selecione a política de eventos dinâmicos que você deseja atribuir e, em seguida, escolha **salvar**. 

Você também pode atribuir uma política de eventos ao vivo a um ou mais usuários da seguinte maneira:

![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) Usar o centro de administração do Microsoft Teams

1. Vá para **** > **políticas de eventos ao vivo**de reuniões.
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **gerenciar usuários**.
4. No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e, em seguida, selecione **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar usuários, selecione **salvar**.
 

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>Permitir que os usuários agendem eventos que foram produzidos com um aplicativo ou dispositivo externo

Para que os usuários agendem eventos produzidos com um aplicativo ou dispositivo externo, você também deve fazer o seguinte:

1. Habilite o Microsoft Stream para os usuários em sua organização. Stream está disponível como parte de assinaturas elegíveis do Office 365 ou como um serviço autônomo. O Stream não está incluído nos planos do Business Essentials ou Business Premium. Consulte [visão geral de licenciamento de fluxo](https://docs.microsoft.com/stream/license-overview) para obter mais detalhes.

      Saiba mais sobre como você pode [atribuir licenças a usuários no Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que os usuários possam acessar o Stream. Certifique-se de que o fluxo não está bloqueado para os usuários, conforme definido neste [artigo](https://docs.microsoft.com/stream/disable-user-organization).

2. Garanta que os usuários tenham permissão de criação de eventos ao vivo no Stream. Por padrão, os administradores podem criar eventos com um aplicativo ou dispositivo externo. O administrador de fluxo pode [habilitar usuários adicionais para a criação de eventos dinâmicos](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) em Stream.  

3. Garanta que os organizadores de eventos dinâmicos contenham a política da empresa definida pelo administrador de fluxo. Se um administrador de fluxo [configurou uma política de diretrizes da empresa](https://docs.microsoft.com/stream/company-policy-and-consent) e requer que os funcionários aceitem essa política antes de salvar o conteúdo, os usuários devem fazer isso antes de criar um evento ao vivo (com um aplicativo ou dispositivo externo) no Teams. Antes de distribuir o recurso eventos dinâmicos na organização, certifique-se de que os usuários que vão criar esses eventos ao vivo tenham sido consentos na política. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Etapa 4: configurar uma solução de distribuição de vídeo para eventos dinâmicos no Microsoft Teams
A reprodução de vídeos de eventos dinâmicos usa o ABR (streaming de taxa de bits adaptável), mas é um fluxo de difusão ponto a ponto, o que significa que cada visualizador está obtendo o próprio fluxo de vídeo da Internet. Para eventos dinâmicos ou vídeos enviados para grandes partes da sua organização, pode haver uma quantidade significativa de largura de banda de Internet consumida pelos visualizadores. Para as organizações que desejam reduzir esse tráfego de Internet para eventos dinâmicos, as soluções de eventos dinâmicos são integradas aos parceiros de entrega de vídeo confiáveis da Microsoft (SDNs) ou a redes de fornecimento de conteúdo corporativo (eCDNs). Essas plataformas SDN/eCDN permitem que as organizações otimizem a largura de banda da rede sem sacrificar as experiências de exibição do usuário final. Nossos parceiros podem ajudar a permitir uma distribuição de vídeo mais dimensionável e eficiente em toda a sua rede corporativa.

**Comprar e configurar sua solução fora do teams** Obtenha ajuda especializada com o dimensionamento da entrega de vídeo aproveitando os parceiros de entrega de vídeo confiáveis da Microsoft. Antes de permitir que um provedor de distribuição de vídeo seja usado com o Microsoft Teams, você deve comprar e configurar a solução SDN/eCDN fora e separadamente do teams.

As seguintes soluções do SDN/eCDN são pré-testadas e podem ser configuradas para serem usadas com o Stream.

- O **streaming de Hive** oferece uma solução simples e potente para distribuição de vídeo empresarial ao vivo e sob demanda. Hive é uma solução baseada em software que não requer hardware ou largura de banda adicional e fornece uma maneira segura de permitir milhares de visualizadores de vídeo simultâneos, sem afetar a sua rede. Para os clientes que desejam entender o vídeo de impacto está em sua rede antes de comprar uma solução SDN/eCDN, o streaming de Hive também oferece uma solução de análise baseada em navegador para clientes da Microsoft. [Saiba mais](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- O **Kollective** é uma plataforma de distribuição de emparelhamento inteligente baseada em nuvem que aproveita sua infraestrutura de rede existente para fornecer conteúdo, em muitos formatos (vídeo ao vivo, vídeo sob demanda, atualizações de software, patches de segurança, etc.) mais rápido e mais confiabilidade e com menos largura de banda. Nossa plataforma segura é confiável para as maiores instituições financeiras do mundo, sem necessidade de hardware, configuração e manutenção adicionais. [Saiba mais](https://kollective.com/microsoft-pilot/).
 
- A **rampa OmniCache** oferece distribuição de rede de última geração e garante a entrega transparente do conteúdo de vídeo em WANs globais, ajudando os produtores de eventos a otimizar a largura de banda da rede e dar suporte a difusões de eventos dinâmicos e sob demanda bem-sucedidas Stream. O suporte para a Ramp OmniCache para eventos dinâmicos produzidos em Teams será disponibilizado em breve. [Saiba mais](http://www.ramp.com). 
 
> [!NOTE] 
> Sua solução SDN ou eCDN está sujeita aos **termos de serviço e à política de privacidade do provedor de terceiros**selecionado, que governam o uso da solução do provedor. Seu uso da solução do provedor não estará sujeito aos termos de licenciamento por volume da Microsoft ou a termos de serviços online. Se você não concordar com os **termos do provedor de terceiros**, não habilite a solução no Microsoft Teams. 

Depois de configurar a solução SDN ou eCDN, você estará pronto para configurar o provedor para eventos dinâmicos no Teams. 

## <a name="next-steps"></a>Próximas etapas
Vá para [definir configurações de eventos ao vivo no Teams](configure-teams-live-events.md).

### <a name="related-topics"></a>Tópicos relacionados
- [O que são os eventos ao vivo do Teams?](what-are-teams-live-events.md)
- [Planejar eventos ao vivo do Teams](plan-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo no Teams](configure-teams-live-events.md)

