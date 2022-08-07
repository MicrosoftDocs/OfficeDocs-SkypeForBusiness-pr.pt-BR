---
title: Conferências e reuniões no Microsoft Teams
ms.reviewer: ''
description: Use esses recursos de implantação para ajudar a implementar reuniões e audioconferências no Microsoft Teams.
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
ms.subservice: meetings
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-get-started
ms.openlocfilehash: 84cc77409aecf5525a16ef73e3dfa7e0115f7566
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268566"
---
# <a name="meetings-and-conferencing-in-microsoft-teams"></a>Conferências e reuniões no Microsoft Teams

> [!NOTE]
> - Para obter uma visão geral sobre como fazer a transição para aprendizagem e recursos remotos para ajudá-lo a começar, confira nossa [**Home Page de aprendizagem remota**](https://www.microsoft.com/education/remote-learning).
> - Recursos para ajudar os professores e alunos com o aprendizado remoto estão disponíveis em [**Ensino e aprendizagem remota no Office 365 Education**](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4).

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Agora, você está pronto para adicionar a carga de trabalho de reuniões, que inclui [audioconferência](deploy-audio-conferencing-teams-landing-page.md), vídeos e compartilhamentos. Esse artigo o orientará durante a implementação de reuniões e conferências de áudio. Comece vendo nosso vídeo sobre reuniões, conferências e dispositivos do Teams (3:28 minutos):

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE46ZdQ]

Para saber mais sobre a experiência de reuniões para seus usuários, confira [Reuniões e chamadas](https://support.office.com/article/meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

*Novidades em abril de 2020*: Os organizadores de reuniões podem finalizar uma reunião para todos os participantes da reunião do Teams, clicando em **Encerrar reunião** nos controles de reunião dentro dela.  

*Novidades de novembro de 2019*: Agora você pode [usar o Assistente do Teams (visualização) para ajudá-lo na implantação do Microsoft Teams](use-advisor-teams-roll-out.md). O Assistente do Teams (visualização) o orienta na implementação do Microsoft Teams, incluindo reuniões e conferências. Ele avalia o ambiente do Office 365 e identifica as configurações mais comuns que talvez seja necessário atualizar ou modificar antes de poder implantar o Teams com êxito.

 > [!NOTE]
 > Para saber mais sobre reuniões e conferências do Teams em diferentes plataformas, confira [recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="meetings-and-conferencing-deployment-decisions"></a>Decisões de implantação de conferências e reuniões

O Teams oferece uma excelente experiência pronta para uso na organização. A maioria das organizações considera que as configurações padrão atendem às necessidades. Este artigo ajuda você a decidir se deseja alterar as configurações padrão, com base no perfil da organização e requisitos de negócios e, em seguida, orienta-o em cada alteração. Dividimos as configurações em dois grupos, começando com o conjunto principal de [alterações que você provavelmente realizará](#core-deployment-decisions). O segundo grupo inclui [configurações adicionais](#additional-deployment-decisions) que poderão ser configuradas com base nas necessidades da organização.

> [!TIP]
> Assista à sessão a seguir para saber mais sobre reuniões: [Introdução às Reuniões no Microsoft Teams para Profissionais de TI](https://aka.ms/teams-meetings-intro).


## <a name="meetings-and-conferencing-prerequisites"></a>Pré-requisitos de conferências e reuniões

Antes de dimensionar a implantação de reuniões na organização, reserve um tempo para verificar e confirmar se o ambiente está pronto, a fim de fornecer a melhor experiência possível aos usuários. Examine as informações a seguir e faça as alterações necessárias no ambiente, quando for o caso.

Para ter à experiência ideal no Teams, é necessário implantar o Exchange Online e o SharePoint Online na organização, e ter um domínio verificado para o Office 365, por exemplo, *contoso.com*.

Para dimensionar reuniões na organização, você deve garantir que todos os usuários tenham acesso à Internet nos respectivos locais de trabalho para se conectar aos serviços do Office 365. Verifique se pelo menos as seguintes portas comuns estão abertas à Internet nos locais dos usuários:

- Portas TCP 80 e 443 de saída dos clientes que usarão o Teams
- Portas UDP 3478 a 3481 de saída dos clientes que usarão o Teams

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Minha rede está pronta para a implantação de reuniões do Teams? | Para verificar se a rede está pronta, confira:<ul><li>[Preparar a rede da organização para o Microsoft Teams](./prepare-network.md)</li><li>[URLs e intervalos de endereços IP](./office-365-urls-ip-address-ranges.md)</li></ul> |

## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Estas são as configurações que a maioria das organizações deseja alterar (se as configurações padrão do Teams não atenderem às necessidades da organização).

### <a name="teams-administrators"></a>Administradores do Teams

O Teams fornece um conjunto de funções de administrador personalizado que pode ser usado para administrar o Teams para sua organização. As funções fornecem vários recursos aos administradores.

| Pergunte-se | Ação |
|--------------|--------|
|A quem será atribuída a função de Administrador de Comunicações de Equipes?|Para saber mais sobre as funções de administrador do Teams, confira [Usar funções de administrador para gerenciar o Microsoft Teams](using-admin-roles.md).|
|A quem será atribuída função de Engenheiro de Suporte de Comunicações de Equipes?|Para atribuir funções de administrador, confira [Atribuir funções de administrador e não administrador aos usuários com o Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A quem será atribuída a função de Especialista de Suporte de Comunicações do Teams?||

### <a name="meetings-settings"></a>Configurações de reuniões

As configurações de reuniões servem para controlar se usuários anônimos podem ingressar em reuniões do Teams e para configurar convites de reunião. Se quiser ativar o recurso QoS (Qualidade de Serviço), defina as portas com tráfego em tempo real. Essas configurações serão usadas para todas as reuniões do Teams que os usuários agendarem na organização.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Personalizarei as configurações inicias de reunião? |Para saber mais sobre configurações de reuniões, confira o [Tutorial de reuniões do Microsoft Teams](tutorial-meetings-in-teams.yml).|
|Implementarei o QoS?|Para saber mais sobre os conceitos do QoS, confira [Qualidade de Serviço no Microsoft Teams](qos-in-teams.md). cenários e implementação.|

### <a name="meeting-policies"></a>Políticas de reunião

As políticas de reunião servem para controlar quais recursos estão disponíveis para os usuários, quando eles ingressam em reuniões do Teams. Você pode usar a política padrão ou criar uma ou mais políticas de reunião personalizadas para as pessoas que organizam reuniões na organização. Para saber mais, consulte o tutorial [Reuniões no Microsoft Teams](tutorial-meetings-in-teams.yml).

| Pergunte a si mesmo | Ação |
|--------------|--------|
|<ul><li>Personalizarei as políticas inicias de reunião?</li><li>Devo exigir várias políticas de reunião?</li><li>Como determinarei a quais grupos de usuários aplicar certas políticas de reunião?</li></ul>|<br>Leia [Gerenciar políticas de reunião no Teams](meeting-policies-overview.md).|

### <a name="audio-conferencing"></a>Audioconferência

A audioconferência fornece às organizações pontos de entrada adicionais para as reuniões, sejam ad hoc ou agendadas, permitindo aos participantes ingressar em reuniões por meio de PSTN (Rede Telefônica Pública Comutada) com discagem por linha fixa tradicional, PBX (central privada de comutação telefônica) ou telefone celular.

Quando estiver pronto para implementar a audioconferência, confira a orientação detalhada do tópico [Implementação de audioconferência](deploy-audio-conferencing-teams-landing-page.md).

### <a name="meeting-room-and-personal-devices"></a>Sala de Reunião e dispositivos pessoais

Para ter a experiência ideal no Teams, considere usar dispositivos, como sistemas de salas, telefones, headsets e câmeras. Para saber mais, confira [Dispositivos com Microsoft Teams para comunicações inteligentes](https://products.office.com/microsoft-teams/across-devices).

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Comprarei dispositivos pessoais para os usuários? |Leia [Gerenciar os dispositivos no Microsoft Teams](devices/device-management.md). |
|Devo comprar e implantar dispositivos com sistema de salas para salas de conferência?|Leia [Soluções e dispositivos com sala de reunião](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).|

### <a name="reporting"></a>Relatórios

Use relatórios de atividade para ver como os usuários da organização estão usando o Teams. Por exemplo, se alguns usuários ainda não estiverem usando o Teams, é provável que não saibam por onde começar ou não entendam como podem usá-lo para se tornarem mais produtivos e colaborativos. Sua organização pode usar os relatórios de atividades para decidir onde priorizar os esforços de treinamento e comunicação.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Quem será responsável pelos relatórios?|Leia [Usar relatórios de atividades no Microsoft Teams](teams-activity-reports.md).  |
|Quem será responsável por monitorar o uso?|Leia [Monitorar o uso e os comentários no Microsoft Teams](get-started-with-teams-monitor-usage-and-feedback.md).|

## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Convém alterar essas configurações, com base nas necessidades da organização e da configuração.

### <a name="bandwidth-planning"></a>Planejamento de largura de banda

Com o planejamento de largura de banda, as organizações podem calcular a largura de banda necessária para dar suporte às reuniões nas redes de longa distância e aos links da Internet. Dessa forma, elas podem confirmar se a rede foi provisionada corretamente para fornecer suporte à expansão do serviço de reunião.

> [!IMPORTANT]
> O Teams não permite que os usuários agendem reuniões ou eventos ao vivo quando estiverem offline ou executando com largura de banda limitada.

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Devo planejar a largura de banda antes e durante a implementação de reuniões? |Para saber mais e obter links para ferramentas a fim de simplificar o processo de planejamento, confira [Preparação de rede](3-envision-evaluate-my-environment.md#network-readiness).|

### <a name="meeting-recording-and-archiving"></a>Gravação e arquivamento de reunião

Os usuários podem gravar reuniões e chamadas de grupo para capturar atividades de áudio, vídeo e compartilhamento de tela. Há também uma opção para habilitar a transcrição automática nas gravações. Com isso, os usuários podem reproduzir gravações de reunião com legendas ocultas e procurar itens de discussão importantes na transcrição. A gravação ocorre na nuvem e é salva no Microsoft Stream, para que os usuários possam compartilhá-la com segurança na organização. Para localizar a gravação de uma reunião, vá para a conversa da reunião.

>[!Note]
> A mudança do Microsoft Stream para o [OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião](tmr-meeting-recording-change.md) será uma abordagem em fases. No lançamento você poderá optar por aceitar essa experiência, em novembro você terá que recusar se quiser continuar usando o Stream e, no início de 2021, exigiremos que todos os clientes usem o OneDrive for Business e o Microsoft Office SharePoint Online para novas gravações de reunião.

Para saber mais, confira [Gravação de reuniões na nuvem do Microsoft Teams](cloud-recording.md).

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Ativarei o serviço de transcrição de reunião?|Confira [Ativar ou desativar a transcrição de gravações](meetings-policies-recording-and-transcription.md#allow-transcription)|

### <a name="live-events-policies"></a>Políticas de eventos ao vivo

As políticas de eventos ao vivo do Microsoft Teams servem para gerenciar configurações de eventos para grupos de usuários. Use a política padrão ou crie políticas adicionais que podem ser atribuídas a usuários que realizam eventos ao vivo na organização.

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Minha organização usará os eventos ao vivo do Microsoft Teams?| Para saber mais sobre planejamento e configuração de eventos ao vivo do Microsoft Teams, confira os artigos sobre [eventos ao vivo](teams-live-events/what-are-teams-live-events.md).|

### <a name="conference-room-systems-rollout"></a>Implementação de sistemas de sala de conferência

As organizações que têm muitas salas de conferência talvez queiram adotar uma abordagem estruturada para inventariar as salas, identificar os dispositivos apropriados e, em seguida, implantá-las. 

| Pergunte a si mesmo | Ação |
|--------------|--------|
| O que preciso fazer para implementar sistemas de sala de conferência?|Confira os artigos [Planejar Salas do Microsoft Teams salas](/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).|

### <a name="cloud-video-interop"></a>Interoperabilidade de vídeo em nuvem

A interoperabilidade de vídeo em nuvem viabiliza o ingresso de dispositivos de sala de reunião de terceiros em reuniões do Microsoft Teams.

Além disso, você pode aproveitar as reuniões ao máximo usando a teleconferência em vídeo com colaboração em conteúdo. No entanto, a atualização de dispositivos e sistemas de sala de reunião é dispendiosa. A interoperabilidade de vídeo em nuvem do Teams funciona com sistemas de terceiros e fornece uma experiência nativa de reunião para todos os participantes, em salas de reunião ou nos clientes do Microsoft Teams.

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Usarei uma solução de interoperabilidade de vídeo em nuvem como parte da implantação de meus sistemas de sala? | Leia [Interoperabilidade de vídeo em nuvem do Microsoft Teams](cloud-video-interop.md).|

### <a name="personal-device-rollout"></a>Implementação de dispositivo pessoal

Quando planejar uma implementação abrangente de dispositivos pessoais para dar suporte às implantações de reuniões ou voz, pense na possibilidade de usar um processo de implementação de site a site, que ofereça uma qualidade constante.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Usarei uma abordagem de site a site para implementar reuniões? |  O [Manual de habilitação de sites para Microsoft Teams](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads) fornece uma ótima base, que você pode aplicar em suas próprias implantações. O guia se concentra em voz, mas os princípios gerais de distribuição de dispositivos, preparação de contas, adoção e treinamento se aplicam a grandes implantações de reunião. |

### <a name="troubleshoot-meeting-and-call-quality"></a>Resolver problemas de qualidade de chamadas e reuniões

O Teams oferece duas maneiras de monitorar e solucionar problemas de qualidade da chamada: [Análise de Chamadas e Painel de Qualidade de Chamadas](monitor-call-quality-qos.md). A Análise de Chamadas exibe informações detalhadas sobre dispositivos, redes e conectividade relacionados a chamadas e reuniões específicas para cada usuário. A Análise de Chamadas foi desenvolvida para ajudar administradores e agentes de assistência técnica a solucionar problemas de qualidade de chamadas com chamadas específicas, enquanto o Painel de Qualidade de Chamadas foi desenvolvido para ajudar administradores e engenheiros de rede a otimizar uma rede. O Painel de Qualidade de Chamadas desloca o foco de usuários específicos e analisa as informações agregadas de toda a organização do Teams.

|Pergunte a si mesmo|Ação |
|------------|-------|
| Quem será responsável pelo monitoramento e a solução de problemas com a qualidade de chamadas? | Confira [Usar a Análise de Chamadas para solucionar problemas de baixa qualidade de chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md) para saber mais sobre os níveis de permissão necessários para solucionar problemas de qualidade de chamadas.|

### <a name="operate-your-meetings-service"></a>Operar o serviço de reuniões

É importante entender a integridade geral do serviço do Teams para que você possa alertar proativamente as pessoas na organização sobre qualquer evento que afete o serviço. O artigo [Operar meu serviço](1-drive-value-operate-my-service.md) fornece orientação detalhada para as operações de serviço.

|Pergunte a si mesmo|Ação |
|------------|-------|
|Quem será o responsável por gerenciar o serviço de reuniões na organização? | Garanta que essa pessoa tenha as permissões de administrador necessárias para gerenciar o serviço de reuniões do Teams. Para saber mais sobre as funções de administrador do Teams, confira [Usar funções de administrador para gerenciar o Microsoft Teams](using-admin-roles.md).|

## <a name="next-steps"></a>Próximas etapas
- [Promover a adoção](adopt-microsoft-teams-landing-page.md) de conferências e reuniões em toda a organização.
- [Adicionar audioconferência](deploy-audio-conferencing-teams-landing-page.md)
- [Implementar o Cloud Voice](cloud-voice-landing-page.md)
- Inclua os aplicativos em destaque — como o Planner — no seu lançamento inicial do Teams. Adicione outros [aplicativos, bots e conectores](deploy-apps-microsoft-teams-landing-page.md) à medida que você impulsiona a adoção do Teams.