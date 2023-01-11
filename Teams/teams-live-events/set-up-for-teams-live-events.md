---
title: Configurar eventos ao vivo no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
description: Configure para eventos ao vivo no Teams, incluindo configurar sua rede, atribuir licenças, habilitar recursos de eventos ao vivo e agendamento e soluções de distribuição de vídeo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cf3d364ce01ea80892dc929102c96a7fab5a74bc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767582"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configurar eventos ao vivo no Microsoft Teams

Ao configurar para eventos ao vivo, há várias etapas que você deve seguir.

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>Etapa 1: configurar sua rede para eventos vivos no Teams

Os eventos ao vivo produzidos pelo Teams exigem que você [Prepare a rede da sua organização para o Teams](../prepare-network.md).  

## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças

Verifique se você tem atribuições de licença corretas para [quem pode criar e agendar eventos ao vivo](plan-for-teams-live-events.md#who-can-attend-create-and-schedule-live-events) e [quem pode assistir a eventos ao vivo](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Etapa 3: configurar políticas de eventos ao vivo

As políticas de eventos ao vivo são usadas para controlar quem em sua organização pode manter os eventos ao vivo e os recursos que estão disponíveis nos eventos criados por eles. Você pode usar a política padrão ou criar uma ou mais políticas personalizadas de eventos dinâmicos. Depois de criar uma política personalizada, você pode atribuí-la a um usuário ou grupo de usuários da organização.

> [!NOTE]
> Os usuários da sua organização receberão a política global (padrão em toda a organização), a menos que você crie e atribua uma política personalizada. Por padrão, na política global, o agendamento do evento ao vivo está habilitado para os usuários do Teams, as legendas em tempo real (transcrição) estão desabilitadas, todas as pessoas da organização podem participar de eventos ao vivo e a configuração de gravação está definida como sempre gravar.

### <a name="create-or-edit-a-live-events-policy"></a>Criar ou editar uma política de eventos ao vivo

<a name="bkcreatepolicy"> </a>

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse a guia Políticas de **gerenciamento de políticas** >  de **eventos do** **Meetings** >  Live.
2. Faça uma das seguintes opções:

    - Se você quiser editar a política padrão existente, escolha **Global (padrão para toda a organização)**.
    - Se você quiser criar uma nova política personalizada, escolha **+Adicionar**.
    - Se você quiser editar uma política personalizada, selecione-a e, em seguida, escolha **Editar**.

    Estas são as configurações que podem ser alteradas de acordo com as necessidades da sua organização.

    ![Captura de tela das configurações da política de eventos ao vivo.](../media/teams-live-events-policies-new.png "Captura de tela de configurações de política de eventos ao vivo no centro de administração do Microsoft Teams")

|Configuração  |Descrição  |
|---------|---------|
|**Título**     |Esse é o título da política exibida na página políticas de eventos ao vivo. Não pode ter mais de 64 caracteres ou caracteres especiais.          |
|**Descrição**    |Use isso para adicionar uma descrição amigável à política.         |
|**Agendamento de eventos ao vivo**     |Habilitar essa operação permite que os usuários da organização criem e agendem eventos ao vivo no Teams.     |
|**Transcrição para participantes** |Essa configuração só pode ser aplicada a eventos produzidos no Teams. Ativar esse recurso permite que os participantes de eventos ao vivo vejam legendas em tempo real durante o evento.         |
|**Quem pode ingressar eventos ao vivo agendados**    |Escolha uma destas opções.<br><br>**Todos** os usuários podem criar eventos ao vivo em que todos, incluindo as pessoas de fora da sua organização, podem participar. Essa configuração permite o tipo de permissão **pública** no Teams quando um usuário agenda um evento ao vivo.<br> **Todos na organização** os usuários podem criar eventos ao vivo nos quais as pessoas de sua organização, incluindo [usuários convidados](../add-guests.md) adicionados à sua organização, podem participar. Os usuários não podem criar eventos ao vivo com participação de usuários anônimos. Essa configuração permite o tipo de permissão **toda a organização** no Teams quando um usuário agenda um evento ao vivo.<br> **Usuários ou grupos específicos** podem criar eventos ao vivo em que somente usuários ou grupos específicos da sua organização podem participar. Os usuários não podem criar eventos ao vivo com a participação de todos em sua organização ou de usuários anônimos. Essa configuração permite o tipo de permissão **Pessoas e grupos** no Teams quando um usuário agenda um evento ao vivo.       |
|**Configuração de gravação**  <br>     | Essa configuração só pode ser aplicada a eventos produzidos no Teams. Escolha uma destas opções. <br><br> **Sempre Gravar** Eventos ao vivo criados por usuários sempre são gravados. Após o evento ser encerrado, os membros da equipe do eventos podem baixar a gravação, e os participantes podem assistir ao evento. <br> **Nunca gravar** eventos ao vivo criados pelos usuários nunca são gravados. <br>**O organizador pode gravar ou não** Usuários podem decidir se desejam gravar o evento ao vivo. Se ele for gravado, após o evento ser encerrado, os membros da equipe do eventos podem baixar a gravação, e os participantes podem assistir ao evento.

Você também pode fazer isso usando Windows PowerShell e, atualmente, os clientes GCC High e DoD devem usar esse método. Para saber mais, confira [usar o PowerShell para definir políticas de eventos ao vivo no Teams](set-teams-live-events-policies-using-powershell.md).

### <a name="assign-a-live-events-policy-to-users"></a>Atribuir uma política de eventos dinâmicos aos usuários

Se você criou uma política personalizada de eventos ao vivo, atribua-a aos usuários para que a política fique ativa. <br><br>[!INCLUDE [assign-policy](../includes/assign-policy.md)]

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Etapa 4: Configurar uma solução de distribuição de vídeo para eventos ao vivo no Teams.

A reprodução de vídeos ao vivo usa o protocolo de taxa de bits adaptável (ABR), mas é um fluxo de unicast, o que significa que todos os visualizadores estão obtendo seu próprio fluxo de vídeo da Internet. Para eventos ao vivo ou vídeos enviados para grande parte da sua organização, pode haver uma quantidade significativa de largura de banda de Internet consumida pelos visualizadores. Para organizações que desejam reduzir esse tráfego de Internet para eventos ao vivo, a Microsoft oferece uma solução de primeira parte, [o Microsoft eCDN](/ecdn) (rede de entrega de conteúdo empresarial). As soluções de eventos ao vivo também são integradas aos parceiros confiáveis de entrega de vídeo da Microsoft que oferecem SDNs (redes definidas por software) ou eCDNs. Essas plataformas SDN/eCDN permitem que as organizações otimizem a largura de banda de rede sem sacrificar experiências de exibição do usuário final. Essas soluções podem ajudar a habilitar uma distribuição de vídeo mais escalonável e eficiente em toda a sua rede corporativa.

- **Microsoft eCDN** O Microsoft eCDN é integrado ao Teams e também é compatível com Stream e Yammer. Ele emprega a tecnologia ponto a ponto em uma rede corporativa para descarregar a largura de banda da conexão WAN.

- **Compre e configure sua solução fora do Teams** Obtenha ajuda especializada com a capacidade de redimensionamento de vídeo aproveitando os parceiros de entrega de vídeo confiáveis da Microsoft. 

As seguintes soluções SDN/eCDN são pré-integradas e podem ser configuradas para serem usadas com o streaming do Teams:

- **O Hive Streaming** fornece uma solução simples e poderosa para a distribuição de vídeo empresarial ao vivo e sob demanda. Hive é uma solução baseada em software que não requer hardware ou largura de banda adicional e oferece uma maneira segura de permitir milhares de visualizadores de vídeo simultâneos, sem afetar a sua rede. Para os clientes que desejam compreender o impacto que o vídeo tem em suas redes antes de adquirir uma solução SDN/eCDN, o streaming do Hive também fornece uma solução de análise baseada em navegador para clientes da Microsoft. [Saiba mais](https://www.hivestreaming.com/partners/integration-partners/microsoft/).

- **O Kollective** é uma plataforma de distribuição baseada em nuvem e emparelhamento inteligente que aproveita sua infraestrutura de rede existente para fornecer conteúdo em muitas formas (vídeo de streaming ao vivo, vídeo sob demanda, atualizações de software, patches de segurança e muito mais) mais rápido, mais confiável e com menos largura de banda. Nossa plataforma segura é confiável pelas maiores instituições financeiras do mundo, sem nenhum hardware adicional, com configuração e a manutenção fáceis. [Saiba mais](https://kollective.com/microsoft-pilot/).

- **Ramp OmniCache** fornece a distribuição de rede de última geração e garante a entrega tranquila de conteúdo de vídeo em WANs globais, ajudando os produtores de eventos a otimizar a largura de banda da rede e dando suporte a difusões de eventos ao vivo e transmissões sob demanda. O suporte para o Ramp OmniCache de eventos ao vivo produzidos no Teams será lançado em breve. [Saiba mais](https://rampecdn.com).

- **Riverbed**, o padrão do setor na otimização de rede, está estendendo suas soluções de aceleração para o Microsoft Teams. Agora, os clientes do Microsoft 365 podem acelerar com confiança 365 tráfego, incluindo o Teams, juntamente com uma riqueza de outros serviços SaaS empresariais líderes para aumentar a produtividade da força de trabalho de qualquer lugar. A aceleração do Teams pode ser habilitada por meio de uma configuração sem esforço que vem com toda a garantia do suporte de classe mundial da Riverbed e do investimento contínuo.

> [!NOTE]
> Se você escolher uma solução SDN ou eCDN de terceiros, ela estará sujeita aos **termos de serviço e política de privacidade do provedor de terceiros** selecionados, que controlarão o uso da solução do provedor. O uso da solução do provedor não estará sujeito aos termos de licenciamento por volume da Microsoft ou a termos de serviços online. Caso não concorde com os **termos do provedor de terceiros**, não habilite a solução no Teams.

Depois de configurar a solução SDN ou eCDN, você estará pronto para configurar o provedor para eventos ao vivo no Teams.

## <a name="next-steps"></a>Próximas etapas

Vá para [Definir configurações de eventos ao vivo do Teams](configure-teams-live-events.md).

### <a name="related-topics"></a>Tópicos relacionados

- [O que são eventos ao vivo de Teams?](what-are-teams-live-events.md)
- [Planejar eventos ao vivo do Teams](plan-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo do Teams](configure-teams-live-events.md)
