---
title: Visão geral de equipes e canais no Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: Conheça as diferentes equipes, canais e aplicativos disponíveis para uma grande variedade de exigências, como finanças, planejamento de eventos, vendas e muito mais.
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
- okr_smb
- intro-overview
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e5ff54577dcfd4e3845758a7ce943231cbd38d48
ms.sourcegitcommit: 50ae550b738424b35df1636590831e6c124ca0c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2022
ms.locfileid: "68576547"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Visão geral de equipes e canais no Microsoft Teams

Vamos começar pensando em como o Microsoft Teams permite que equipes individuais se auto-organizem e colaborem em vários cenários de negócios:

- As **equipes** são uma coleção de pessoas, conteúdo e ferramentas que envolvem diferentes projetos e resultados dentro de uma organização.

    - As equipes podem ser criadas para serem particulares e apenas para usuários convidados.
    - As equipes também podem ser criadas para serem públicas e abertas, permitindo que qualquer pessoa dentro da organização participe (até 10.000 membros).
    
    As equipes são projetadas para reunir um grupo de pessoas que trabalham unidas para realizar tarefas. O Teams pode ser dinâmico para o trabalho baseado em projetos (por exemplo, lançamento de um produto, criação de uma sala de envio digital), bem como contínuas, para refletir a estrutura interna da sua organização (por exemplo, departamentos e escritórios). Conversas, arquivos e notas nos canais de equipe são visíveis apenas para os membros da equipe.

- **Canais** são seções exclusivas dentro de uma equipe para manter as conversas organizadas por tópicos, projetos e disciplinas específicas — o que funcionar melhor para a sua equipe. Os arquivos que você compartilha em um canal (na guia Arquivos) são armazenados no SharePoint. Para saber mais, leia [Como o SharePoint Online e o OneDrive for Business interagem com o Teams](SharePoint-OneDrive-interact.md).

    - Os canais são locais onde as conversas acontecem e onde o trabalho realmente é feito. Os canais podem ser abertos para todos os membros da equipe (canais padrão), membros da equipe selecionados ([canais privados](private-channels.md)) ou pessoas selecionadas dentro e fora da equipe ([canais compartilhados](shared-channels.md)).
    - Os canais são mais valiosos quando estendidos com aplicativos que incluem guias, conectores e bots que aumentam seu valor para os membros da equipe. Para saber mais, confira Visão [geral dos aplicativos do Teams](deploy-apps-microsoft-teams-landing-page.md).
    
Para obter ajuda sobre como usar equipes e canais, confira [Equipes e canais](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499).

Consulte [Limites e especificações para Microsoft Teams](/microsoftteams/limits-specifications-teams) para obter informações sobre os limites associados ao uso do Microsoft Teams.

## <a name="membership-roles-and-settings"></a>Associação, funções e configurações

**Associação da equipe**

Quando o Teams é ativado para toda a organização, os proprietários de equipe podem convidar qualquer pessoa da organização com quem trabalhem para ingressar na equipe. O Teams torna mais fácil para os proprietários da equipe adicionar pessoas na organização com base em seus nomes. Dependendo das configurações da sua organização, pessoas de fora da sua organização podem ser adicionadas a suas equipes como convidados ou como participantes externos em canais compartilhados. Veja [Acesso de Convidado no Microsoft Teams](guest-access.md) para obter mais detalhes. 

Os proprietários da equipe também podem criar uma equipe baseado em um grupo existente do Microsoft 365. Todas as alterações feitas na associação a um grupo serão sincronizadas com o Teams automaticamente.

**Funções da equipe**

Existem duas funções principais no Teams: 

- **Proprietário da equipe** - a pessoa que cria a equipe. Os proprietários de equipe podem atribuir a função de coproprietário a qualquer membro a qualquer momento, tanto ao enviar o convite quanto após o ingresso do membro na equipe. Ter vários proprietários de equipes permite compartilhar as responsabilidades de gerenciamento configurações e associação de membros, incluindo convites.
- **Membros da equipe** - as pessoas que os proprietários convidam para ingressar na equipe.

Além disso, se a moderação estiver configurada, os proprietários e membros da equipe poderão ter recursos de moderador para um canal. Os moderadores podem iniciar novas postagens no canal e controlar se os membros da equipe podem responder às mensagens existentes do canal. Os proprietários da equipe podem atribuir moderadores em um canal. (Os proprietários da equipe têm recursos de moderador por padrão.) Os moderadores em um canal podem adicionar ou remover outros moderadores nesse canal. Para mais informações, consulte [Configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md).

> [!NOTE]
> Quando você adiciona um proprietário de equipe, eles também são adicionados como um membro, exceto quando a equipe é criada no Centro de administração do Teams ou quando uma equipe é adicionada a um grupo novo ou existente do Microsoft 365.

**Configurações da equipe** 

Team owners can manage team-wide settings directly in Teams. Settings include the ability to add a team picture, set permissions across team members for creating standard, private, and shared channels, adding tabs and connectors, @mentioning the entire team or channel, and the usage of GIFs, stickers, and memes.

Se você for um administrador do Teams no Microsoft 365, terá acesso às configurações de todo o sistema no Centro de administração do Teams. Essas configurações podem impactar as opções e padrões que os proprietários de equipe veem nas configurações de equipe. Por exemplo, você pode ativar um canal padrão, "Geral", para anúncios, discussões e recursos em toda a equipe, que será exibido em todas as equipes.

Por padrão, todos os usuários têm permissão para criar uma equipe. Para modificar isso, consulte [Atribuir funções e permissões no Teams](assign-roles-permissions.md).

Uma atividade importante de planejamento inicial para envolver os usuários com o Teams é ajudar as pessoas a pensarem e compreenderem como o Teams pode aprimorar a colaboração no seu dia a dia. Converse com as pessoas e ajude-as a selecionar cenários de negócios em que elas estejam colaborando atualmente de maneira fragmentada. Reúna-os em um canal com as guias relevantes que os ajudarão a realizar seu trabalho. Um dos casos de uso mais eficientes do Microsoft Teams é em qualquer processo multiorganizacional.

> [!NOTE]
> Quando você cria uma nova equipe ou um canal privado ou compartilhado no Microsoft Teams, um site de equipe no Microsoft Office SharePoint Online é criado automaticamente. Para editar a descrição ou classificação do site para este site de equipe, acesse as [configurações do canal correspondente no Microsoft Teams](https://support.microsoft.com/office/bf39798f-90d2-44fb-a750-55fa05a56f1d).
>
> Saiba mais sobre como gerenciar [Sites de equipes conectadas do Microsoft Teams](/SharePoint/teams-connected-sites).

Este vídeo mostra as etapas para exibir e gerenciar a associação de equipe de um usuário.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53x1L?autoplay=false]

## <a name="channel-feature-comparison"></a>Comparação de recursos do canal

A tabela a seguir mostra uma comparação de recursos do Microsoft Teams para cada tipo de canal.

|Recursos|Canal padrão|Canal privado|Canal compartilhado|
|:-------|:---------------|:--------------|:-------------|
|As pessoas podem ser adicionadas ao canal sem adicioná-las à equipe.|Não|Não|Sim|
|A associação ao canal pode ser limitada a um subconjunto da equipe.|Não|Sim|Sim|
|O canal pode ser compartilhado diretamente com outras equipes.|Não|Não|Sim|
|O canal pode ser compartilhado diretamente com sua equipe pai.|Não disponível|Não|Sim|
|Os convidados podem participar do canal.|Sim|Sim|Não|
|Participantes externos (Conexão Direta B2B) podem participar do canal.|Não|Não|Sim|
|Moderação|Sim|Não|Não|
|Salas para sessão de grupo|Sim|Não|Não|
|Copiar link para o canal|Sim|Não|Não|
|Cada canal tem um site SharePoint dedicado.|Não|Sim|Sim|
|Reuniões agendadas|Sim|Não|Sim|
|Planner|Sim|Não|Não|
|Bots, conectores e extensões de mensagens|Sim|Não|Não|
|Com suporte em equipes de classe|Sim|Sim|Não|
|Marcas|Sim|Não|Não|
|Análise|Sim|Sim|Não|

## <a name="org-wide-teams"></a>Equipes de toda a organização

Se sua organização não tiver mais de 10.000 usuários, você pode criar uma equipe em toda a organização. Equipes que abrangem toda a organização fornecem uma maneira automática para que todos em uma organização façam parte de uma única equipe para colaboração. Para obter mais informações, incluindo práticas recomendadas para criar e gerenciar uma equipe de toda a organização, consulte [Criar uma equipe de toda a organização no Microsoft Teams](create-an-org-wide-team.md).

## <a name="next-steps"></a>Próximas etapas

Leia [Chat, equipes, canais e aplicativos no Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) para ver uma lista de decisões importantes para a distribuição do seu Teams.
