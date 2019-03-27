---
title: Conferências e reuniões no Microsoft Teams
ms.reviewer: ''
description: Use esses recursos de implantação para ajudá-lo a implantar reuniões no Microsoft Teams.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/28/2019
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: afd7e15f759caafdc76dc2f20777f4d3ab66d672
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889765"
---
# <a name="meetings--conferencing-in-microsoft-teams"></a>Conferências e reuniões no Microsoft Teams

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Agora, você está pronto para adicionar a carga de trabalho de reuniões, que inclui [audioconferência](deploy-audio-conferencing-teams-landing-page.md), vídeos e compartilhamentos. Veja como. 


## <a name="meetings--conferencing-deployment-decisions"></a>Decisões de implantação de conferências e reuniões

O Teams oferece uma excelente experiência pronta para uso na organização. A maioria das organizações considera que as configurações padrão atendem às necessidades. Este artigo ajuda você a decidir se deseja alterar as configurações padrão, com base no perfil da organização e requisitos de negócios e, em seguida, orienta-o em cada alteração. Dividimos as configurações em dois grupos, começando com o conjunto principal de [alterações que você provavelmente realizará](#core-deployment-decisions). O segundo grupo inclui [configurações adicionais](#additional-deployment-decisions) que poderão ser configuradas com base nas necessidades da organização.

> [!Tip]
> Para saber mais sobre reuniões, assista ao vídeo [Introdução às reuniões no Microsoft Teams para profissionais de TI](https://aka.ms/teams-meetings-intro).


## <a name="meetings--conferencing-prerequisites"></a>Pré-requisitos de conferências e reuniões 

Antes de dimensionar a implantação de reuniões na organização, reserve um tempo para verificar e confirmar se o ambiente está pronto, a fim de fornecer a melhor experiência possível aos usuários. Examine as informações a seguir e faça as alterações necessárias no ambiente, quando for o caso.

Para ter à experiência ideal no Teams, é necessário implantar o Exchange Online e o SharePoint Online na organização, e ter um domínio verificado para o Office 365, por exemplo, *contoso.com*.

Para dimensionar reuniões na organização, você deve garantir que todos os usuários tenham acesso à Internet nos respectivos locais de trabalho para se conectar aos serviços do Office 365. Verifique se pelo menos as seguintes portas comuns estão abertas à Internet nos locais dos usuários:

- Portas TCP 80 e 443 de saída dos clientes que usarão o Teams
- Portas UDP 3478 a 3481 de saída dos clientes que usarão o Teams

Use a ferramenta [NetworkTestingCompanion](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2) para confirmar se os locais de rede estão prontos para o tráfego de voz e vídeo, que dará suporte à experiência de reuniões.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Minha rede está pronta para a implantação de reuniões do Teams? | Para verificar se a rede está pronta, confira:<ul><li>[Preparar a rede da organização para o Microsoft Teams](https://docs.microsoft.com/pt-BR/MicrosoftTeams/prepare-network)</li><li>[URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/pt-BR/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Estas são as configurações que a maioria das organizações deseja alterar (se as configurações padrão do Teams não atenderem às necessidades da organização).

### <a name="teams-administrators"></a>Administradores do Teams

O Teams fornece um conjunto personalizado de funções de administrador que pode ser usado para gerenciar o programa na organização. As funções fornecem vários recursos para administradores. 

| Pergunte a si mesmo | Ação |
|--------------|--------|
|A quem será atribuída a função de Administrador de Comunicações de Equipes?|Para saber mais sobre as funções de administrador do Teams, confira [Usar funções de administrador para gerenciar o Microsoft Teams](using-admin-roles.md).|
|A quem será atribuída função de Engenheiro de Suporte de Comunicações de Equipes?|Para atribuir funções de administrador, confira [Atribuir funções de administrador e não administrador aos usuários com o Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A quem será atribuída a função de Especialista de Suporte de Comunicações de Equipes?||
|||

### <a name="meetings-settings"></a>Configurações de reuniões 

As configurações de reuniões servem para controlar se usuários anônimos podem ingressar em reuniões do Teams e para configurar convites de reunião. Se quiser ativar o recurso QoS (Qualidade de Serviço), defina as portas com tráfego em tempo real. Essas configurações serão usadas para todas as reuniões do Teams que os usuários agendarem na organização. 

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Personalizarei as configurações inicias de reunião? |Para saber mais sobre configurações de reuniões, confira o [Tutorial de reuniões do Microsoft Teams](tutorial-meetings-in-teams.yml).|
|Implementarei o QoS?|Para saber mais sobre os conceitos do QoS, confira [Qualidade de Serviço no Microsoft Teams](qos-in-teams.md). cenários e implementação.|
|||

### <a name="meeting-policies"></a>Políticas de reunião

As políticas de reunião servem para controlar quais recursos estão disponíveis para os usuários, quando eles ingressam em reuniões do Teams. Você pode usar a política padrão ou criar uma ou mais políticas de reunião personalizadas para as pessoas que organizam reuniões na organização. Para saber mais, confira o [Tutorial de reuniões do Microsoft Teams](tutorial-meetings-in-teams.yml).

| Pergunte a si mesmo | Ação |
|--------------|--------|
|<ul><li>Personalizarei as políticas inicias de reunião?</li><li>Devo exigir várias políticas de reunião?</li><li>Como determinarei a quais grupos de usuários aplicar certas políticas de reunião?</li></ul>|<br>Leia [Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md).|
|||

### <a name="audio-conferencing"></a>Audioconferência

A audioconferência fornece às organizações pontos de entrada adicionais para as reuniões, sejam ad hoc ou agendadas, permitindo aos participantes ingressar em reuniões por meio de PSTN (Rede Telefônica Pública Comutada) com discagem por linha fixa tradicional, PBX (central privada de comutação telefônica) ou telefone celular. 

Quando estiver pronto para implementar a audioconferência, confira a orientação detalhada do tópico [Implementação de audioconferência](deploy-audio-conferencing-teams-landing-page.md).

### <a name="meeting-room-and-personal-devices"></a>Sala de Reunião e dispositivos pessoais

Para ter a experiência ideal no Teams, considere usar dispositivos, como sistemas de salas, telefones, headsets e câmeras. Para saber mais, confira [Dispositivos com Microsoft Teams para comunicações inteligentes](https://products.office.com/microsoft-teams/across-devices).

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Comprarei dispositivos pessoais para os usuários? |Leia [Gerenciar os dispositivos no Microsoft Teams](device-management.md). |
|Devo comprar e implantar dispositivos com sistema de salas para salas de conferência?|Leia [Soluções e dispositivos com sala de reunião](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="reporting"></a>Relatórios

Use relatórios de atividade para ver como os usuários da organização estão usando o Teams. Por exemplo, se alguns usuários ainda não estiverem usando o Teams, é provável que não saibam por onde começar ou não entendam como podem usá-lo para se tornarem mais produtivos e colaborativos. A organização pode usar os relatórios de atividades para decidir onde priorizar os esforços de treinamento e comunicação. 


| Pergunte a si mesmo | Ação |
|--------------|--------|
|Quem será responsável pelos relatórios?|Leia [Usar relatórios de atividades no Microsoft Teams](teams-activity-reports.md).  |
|Quem será responsável por monitorar o uso?|Leia [Monitorar o uso e os comentários no Microsoft Teams](get-started-with-teams-monitor-usage-and-feedback.md).|
|||

## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Convém alterar essas configurações, com base nas necessidades da organização e da configuração.

### <a name="bandwidth-planning"></a>Planejamento de largura de banda 

Com o planejamento de largura de banda, as organizações podem calcular a largura de banda necessária para dar suporte às reuniões nas redes de longa distância e aos links da Internet. Dessa forma, elas podem confirmar se a rede foi provisionada corretamente para fornecer suporte à expansão do serviço de reunião. 

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Devo planejar a largura de banda antes e durante a implementação de reuniões? |Para saber mais e obter links para ferramentas a fim de simplificar o processo de planejamento, confira [Preparação de rede](3-envision-evaluate-my-environment.md#network-readiness).|
|||

### <a name="meeting-recording-and-archiving"></a>Gravação e arquivamento de reunião

Os usuários podem gravar reuniões e chamadas de grupo para capturar atividades de áudio, vídeo e compartilhamento de tela. Há também uma opção para habilitar a transcrição automática nas gravações. Com isso, os usuários podem reproduzir gravações de reunião com legendas ocultas e procurar itens de discussão importantes na transcrição. A gravação ocorre na nuvem e é salva no Microsoft Stream, para que os usuários possam compartilhá-la com segurança na organização. Para localizar a gravação de uma reunião, vá para a conversa da reunião.

Para saber mais, confira [Gravação de reuniões na nuvem do Microsoft Teams](cloud-recording.md).

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Ativarei o serviço de transcrição de reunião?|Confira [Ativar ou desativar a transcrição de gravações](cloud-recording.md#turn-on-or-turn-off-recording-transcription)|
|||


### <a name="live-events-policies"></a>Políticas de eventos ao vivo

As políticas de eventos ao vivo do Microsoft Teams servem para gerenciar configurações de eventos para grupos de usuários. Use a política padrão ou crie políticas adicionais que podem ser atribuídas a usuários que realizam eventos ao vivo na organização. 

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Minha organização usará os eventos ao vivo do Microsoft Teams?| Para saber mais sobre planejamento e configuração de eventos ao vivo do Microsoft Teams, confira os artigos sobre [eventos ao vivo](teams-live-events/what-are-teams-live-events.md).|
|||

### <a name="conference-room-systems-rollout"></a>Implementação de sistemas de sala de conferência

As organizações que têm muitas salas de conferência talvez queiram adotar uma abordagem estruturada para inventariar as salas, identificar os dispositivos apropriados e, em seguida, implantá-las. 



| Pergunte a si mesmo | Ação |
|--------------|--------|
| O que preciso fazer para implementar sistemas de sala de conferência?|Confira os artigos sobre [Sistemas de Salas Skype versão 2](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="cloud-video-interop"></a>Interoperabilidade de vídeo em nuvem

A interoperabilidade de vídeo em nuvem viabiliza o ingresso de dispositivos de sala de reunião de terceiros em reuniões do Microsoft Teams. 

Além disso, você pode aproveitar as reuniões ao máximo usando a teleconferência em vídeo com colaboração em conteúdo. No entanto, a atualização de dispositivos e sistemas de sala de reunião é dispendiosa. A interoperabilidade de vídeo em nuvem do Teams funciona com sistemas de terceiros e fornece uma experiência nativa de reunião para todos os participantes, em salas de reunião ou nos clientes do Microsoft Teams. 

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Usarei uma solução de interoperabilidade de vídeo em nuvem como parte da implantação de meus sistemas de sala? | Leia [Interoperabilidade de vídeo em nuvem do Microsoft Teams](cloud-video-interop.md).|
|||


### <a name="personal-device-rollout"></a>Implementação de dispositivo pessoal

Quando planejar uma implementação abrangente de dispositivos pessoais para dar suporte às implantações de reuniões ou voz, pense na possibilidade de usar um processo de implementação de site a site, que ofereça uma qualidade constante.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Usarei uma abordagem de site a site para implementar reuniões? |  O [Manual de habilitação de sites para Microsoft Teams](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads) fornece uma ótima base, que você pode aplicar em suas próprias implantações. O guia se concentra em voz, mas os princípios gerais de distribuição de dispositivos, preparação de contas, adoção e treinamento se aplicam a grandes implantações de reunião. |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Resolver problemas de qualidade de chamadas e reuniões 

O Teams oferece duas maneiras de monitorar e solucionar problemas de qualidade da chamada: [Análise de Chamadas e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md). A Análise de Chamadas exibe informações detalhadas sobre dispositivos, redes e conectividade relacionados a chamadas e reuniões específicas para cada usuário. A Análise de Chamadas foi desenvolvida para ajudar administradores e agentes de assistência técnica a solucionar problemas de qualidade de chamadas com chamadas específicas, enquanto o Painel de Qualidade de Chamadas foi desenvolvido para ajudar administradores e engenheiros de rede a otimizar uma rede. O Painel de Qualidade de Chamadas desloca o foco de usuários específicos e analisa as informações agregadas de toda a organização do Teams. 

|Pergunte a si mesmo|Ação |
|------------|-------|
| Quem será responsável pelo monitoramento e a solução de problemas com a qualidade de chamadas? | Confira [Usar a Análise de Chamadas para solucionar problemas de baixa qualidade de chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md) para saber mais sobre os níveis de permissão necessários para solucionar problemas de qualidade de chamadas.|
|||

### <a name="operate-your-meetings-service"></a>Operar o serviço de reuniões

É importante entender a integridade geral do serviço do Teams para que você possa alertar proativamente as pessoas na organização sobre qualquer evento que afete o serviço. O artigo [Operar meu serviço](1-drive-value-operate-my-service.md) fornece orientação detalhada para as operações de serviço.

|Pergunte a si mesmo|Ação |
|------------|-------|
|Quem será o responsável por gerenciar o serviço de reuniões na organização? | Garanta que essa pessoa tenha as permissões de administrador necessárias para gerenciar o serviço de reuniões do Teams. Para saber mais sobre as funções de administrador do Teams, confira [Usar funções de administrador para gerenciar o Microsoft Teams](using-admin-roles.md).|
|||


## <a name="next-steps"></a>Próximas etapas
- [Promover a adoção](adopt-microsoft-teams-landing-page.md) de conferências e reuniões em toda a organização.
- [Adicionar audioconferência](deploy-audio-conferencing-teams-landing-page.md)
- [Implementar o Cloud Voice](cloud-voice-landing-page.md)
- Incluir os aplicativos em destaque, como o Planner, na implementação inicial do Teams. Adicionar outros [aplicativos, bots e conectores](deploy-apps-microsoft-teams-landing-page.md) ao promover a adoção do Teams.
