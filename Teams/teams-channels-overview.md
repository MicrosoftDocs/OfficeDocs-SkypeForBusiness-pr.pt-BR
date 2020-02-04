---
title: Visão geral de equipes e canais no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Conheça as diferentes equipes, canais e aplicativos disponíveis para uma grande variedade de exigências, como finanças, planejamento de eventos, vendas e muito mais.
localization_priority: Normal
f1.keywords:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
ms.collection:
- M365-collaboration
ms.custom: okr_smb
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6e241deaf074fb7ccd6db9789539838c1027e40
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708147"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Visão geral de equipes e canais no Microsoft Teams

> [!NOTE]
> Analise as informações a seguir para entender como funciona o bate-papo, equipes, canais e aplicativos no Teams. Em seguida, acesse [Bate-papo, equipes, canais e aplicativos no Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) para ver uma lista de decisões importantes para a sua configuração do Teams.

Vamos começar pensando em como o Microsoft Teams permite que equipes individuais se auto-organizem e colaborem em vários cenários de negócios:

- As **equipes** são uma coleção de pessoas, conteúdo e ferramentas que envolvem diferentes projetos e resultados dentro de uma organização.

    - As equipes podem ser criadas para serem particulares e apenas para usuários convidados.
    - As equipes também podem ser criadas para serem públicas e abertas, permitindo que qualquer pessoa dentro da organização participe (até 5000 membros).
    
    As equipes são projetadas para reunir um grupo de pessoas que trabalham unidas para realizar tarefas. O Teams pode ser dinâmico para um trabalho baseado em um projeto (por exemplo, lançamento de um produto, criação de uma sala de guerra digital), assim como para trabalhos contínuos a fim de refletir a estrutura interna da empresa (por exemplo, localizações de departamentos e escritórios). Conversas, arquivos e notas nos canais de equipe são visíveis apenas para os membros da equipe.

- **Canais** são seções exclusivas dentro de uma equipe para manter as conversas organizadas por tópicos, projetos e disciplinas específicas — o que funcionar melhor para a sua equipe! Os arquivos que você compartilha em um canal (na guia Arquivos) são armazenados no SharePoint. Para saber mais, leia [Como o SharePoint Online e o OneDrive for Business interagem com o Teams](SharePoint-OneDrive-interact.md).

    - Os canais são locais onde as conversas acontecem e onde o trabalho realmente é feito. Os canais podem ser abertos para todos os membros da equipe ou, se você precisar de mais um público selecionado, eles poderão ser particulares. Os canais padrão são para as conversas que todos em uma equipe podem participar e os [canais privados](private-channels.md) limitam a comunicação a um subconjunto de pessoas de uma equipe.
    - Os canais são mais valiosos quando estendidos com aplicativos que incluem guias, conectores e bots que aumentam seu valor para os membros da equipe. Para saber mais, consulte [Aplicativos, bots e conectores no Teams](deploy-apps-microsoft-teams-landing-page.md).
    
Para obter ajuda sobre como usar equipes e canais, consulte [equipes e canais](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499).

Veja este pequeno vídeo para saber mais sobre as práticas recomendadas para criar equipes e canais.

   > [!VIDEO https://www.youtube.com/embed/WkAVgNKn0hs]

<a name="membership-roles-and-settings"></a>Associação, funções e configurações
------------------------------

**Associação da equipe**

Quando o Microsoft Teams é ativado para toda a organização, os proprietários da equipe designada podem convidar qualquer funcionário com quem trabalham para ingressar na equipe. O Microsoft Teams torna fácil para os proprietários de equipe adicionarem pessoas na empresa baseado nos seus nomes. Dependendo das configurações usadas pela empresa, convidados que são membros da equipe, mas não pertencem à empresa também podem sem adicionados às suas equipes. Veja [Acesso de Convidado no Microsoft Teams](guest-access.md) para obter mais detalhes. 

Os proprietários de equipe também podem criar uma equipe baseado em um grupo do Office 365 existente. Quaisquer alterações feitas no grupo serão sincronizadas com o Microsoft Teams automaticamente. Criar uma equipe baseada em um grupo do Office 365 existente, não apenas simplifica o processo de convidar e gerenciar os membros, mas também sincronizar os arquivos de grupo dentro do Microsoft Teams.

**Funções da equipe**

Existem duas funções principais no Microsoft Teams: 

- **Proprietário da equipe** - a pessoa que cria a equipe. Os proprietários de equipe podem tornar qualquer membro da sua equipe um coproprietário quando é feito o convite para a equipe ou a qualquer momento após ele ter entrado na equipe. Ter vários proprietários de equipes permite compartilhar as responsabilidades de gerenciamento configurações e associação de membros, incluindo convites.
- **Membros da equipe** - as pessoas que os proprietários convidam para ingressar na equipe.

Além disso, se a moderação estiver configurada, os proprietários e membros da equipe poderão ter recursos de moderador para um canal. Os moderadores podem iniciar novas postagens no canal e controlar se os membros da equipe podem responder às mensagens existentes do canal. Os proprietários da equipe podem atribuir moderadores em um canal. (Os proprietários da equipe têm recursos de moderador por padrão.) Os moderadores em um canal podem adicionar ou remover outros moderadores nesse canal. Para mais informações, consulte [Configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md).

**Configurações da equipe** 

Os proprietários da equipe podem gerenciar as configurações de toda a equipe diretamente no Microsoft Teams. As configurações incluem a capacidade de adicionar uma imagem de equipe, definir permissões entre os membros da equipe para criar canais padrão e [privados](private-channels.md), adicionar guias e conectores, @mentioning toda a equipe ou canal e o uso de gifs, adesivos e memes.

Reserve três minutos para conferir este vídeo de guia para proprietários de equipe:

   > [!VIDEO https://www.youtube.com/embed/7XcDSuw6NR4]

Se você for um administrador do Microsoft Teams no Office 365, terá acesso às configurações de todo o sistema no centro de administração do Microsoft Teams. Essas configurações podem impactar as opções e padrões que os proprietários de equipe veem nas configurações de equipe. Por exemplo, você pode ativar um canal padrão, "Geral", para anúncios, discussões e recursos em toda a equipe, que será exibido em todas as equipes.

Por padrão, todos os usuários têm permissões para criar uma equipe no Microsoft Teams (para modificar isso, consulte [Atribuir funções e permissões no Teams)](assign-roles-permissions.md). Os usuários de um grupo existente do Office 365 também podem aprimorar suas permissões com a funcionalidade do Teams.

Uma atividade importante de planejamento inicial para envolver os usuários com o Microsoft Teams é ajudar as pessoas a pensarem sobre e entenderem como o Teams pode aprimorar a colaboração no dia a dia. Converse com as pessoas e ajude-as a selecionar cenários de negócios em que elas estejam colaborando atualmente de maneira fragmentada. Reúna-os em um canal com as guias relevantes que os ajudarão a realizar seu trabalho. Um dos casos de uso mais eficientes do Microsoft Teams é em qualquer processo multiorganizacional. 

<a name="example-teams"></a>Exemplo do Teams
--------------

Abaixo estão alguns exemplos funcionais de como os diferentes tipos de usuários podem abordar a criação de equipes, canais e aplicativos (guias/conectores/bots). Isso pode ser útil para ajudar a iniciar uma conversa sobre o Microsoft Teams com sua comunidade de usuários. Ao pensar em como implementar o Microsoft Teams em sua organização, lembre-se de fornecer orientações sobre como estruturar suas equipes; no entanto, os usuários têm controle de como eles podem se auto-organizar. São apenas exemplos para ajudar as equipes a começar a pensar nas possibilidades.

O Microsoft Teams é ótimo para dividir silos organizacionais e promover equipes multifuncionais. Por isso, incentive seus usuários a pensarem em equipes funcionais, e não em limites organizacionais.

|Tipos de equipe  |Canais potenciais  |Aplicativos (Guias ![Um ícone representando uma pasta com uma guia](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/Conectores ![Um ícone representando blocos de conexão](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/Bots ![Um ícone representando um pequeno robô](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|Vendas     |Reunião anual de vendas<br></br> Avaliação trimestral de negócios<br></br> Avaliação mensal do pipeline de vendas<br></br> Conjunto de estratégias de vendas |Power BI<br></br>Trello<br></br>CRM<br></br>Resumir bot         |
|Relações Públicas     |Notas de imprensa<br></br>Novidades e atualizações<br></br>Verificação de fatos         |RSS Feed<br></br>Twitter         |
|Planejamento de eventos     |Marketing<br></br>Logística e cronograma<br></br>Local<br></br>Orçamento         |Twitter<br></br>Facebook<br></br>Planner<br></br>PDF         |
|Marketing/Go to Market   |Pesquisa de Mercado<br></br>Pilares de mensagem<br></br>Plano de comunicação<br></br>Lista de materiais de marketing        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|Operações técnicas    |Gerenciamento de incidentes<br></br>Planejamento de sprint<br></br>Itens de Trabalho<br></br>Infraestrutura e operações         |Serviços de equipe<br></br>Jira<br></br>AzureBot         |
|Equipe de produto      |Estratégia<br></br>Marketing<br></br>Vendas<br></br>Operações<br></br>Informações<br></br>Serviços e suporte         |Power BI<br></br>Serviços de equipe         |
|Finanças    |Ano fiscal atual<br></br>Planejamento do ano fiscal<br></br>Previsão<br></br>Contas a receber<br></br>Contas a pagar         |Power BI<br></br>Google Analytics         |
|Logística     |Operações de armazém<br></br>Manutenção de veículos<br></br>Escala de serviços dos motoristas         |Serviço de clima e tempo<br></br>Viagens/problemas de trânsito rodoviário<br></br>Planner<br></br>Tubot<br></br>UPS Bot         |
|RH     |Gerenciamento de talentos<br></br>Recrutamento<br></br>Planejamento de avaliações de desempenho<br></br>Moral         |Ferramentas de RH<br></br>Sites de publicação de trabalhos externos<br></br>Growbot         |
|Multiorganizacional <br></br>Equipe virtual |Estratégia<br></br>Desenvolvimento da força de trabalho<br></br>Competir e pesquisar         |Power BI<br></br>Microsoft Stream         |

É possível criar equipes alinhadas com a estrutura organizacional. Isso é melhor usado para líderes que desejam elevar a moral, fazer análises específicas da equipe, esclarecer os processos de integração dos funcionários, discutir planos de força de trabalho e aumentar a visibilidade em uma força de trabalho diversificada.  

![Diagrama de hierarquia de equipes e canais organizados no Microsoft Teams.](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>Equipes de toda a organização

Se sua organização não tiver mais de 5.000 usuários, você poderá criar uma equipe de toda a organização. Equipes que abrangem toda a organização fornecem uma maneira automática para que todos em uma organização façam parte de uma única equipe para colaboração. Para obter mais informações, incluindo práticas recomendadas para criar e gerenciar uma equipe de toda a organização, consulte [Criar uma equipe de toda a organização no Microsoft Teams](create-an-org-wide-team.md).
