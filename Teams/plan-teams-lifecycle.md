---
title: Planejar o gerenciamento de ciclo de vida no Teams ‒ Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Saiba como planejar a implementação dos recursos de gerenciamento de ciclo de vida no Teams.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d4c8d99dcc3e1c96e5fbfce942b9def6d0db952
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754772"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Planejar o gerenciamento de ciclo de vida no Teams

O Teams fornece um conjunto avançado de ferramentas para implementar processos de gerenciamento de ciclo de vida de colaboração para sua organização. Este artigo orienta os profissionais de TI por meio das perguntas certas para determinar seus requisitos de gerenciamento de ciclo de vida e as ferramentas a serem usadas para atendê-los. 

É importante planejar o gerenciamento de ciclo de vida, pois isso significa que você cria um plano para realizar o trabalho com eficiência. A maioria dos projetos consiste em início, meio e fim. Isso também se aplica às equipes, mas elas podem ser criadas e usadas de várias maneiras. Por isso, nem sempre é óbvio em qual estágio do ciclo de vida elas estão. Ter um plano para o gerenciamento do ciclo de vida ajudará você a acompanhar os projetos de sua organização enquanto eles percorrem esses estágios.

> [!Tip]
> Assista à seguinte sessão para saber mais sobre o ciclo de vida no Microsoft Teams: [Governança, gerenciamento e ciclo de vida no Microsoft Teams](https://aka.ms/teams-governance)


## <a name="lifecycle-concepts"></a>Conceitos de ciclo de vida

Os conceitos e as definições a seguir afetam as decisões que você toma para o gerenciamento de ciclo de vida.

**Microsoft Teams**

A _team_ is a collection of people, content, and tools that facilitate collaboration. A team defines who its members are, and the permissions and policies that apply to those members. Teams are built on Office 365 Groups, and changes to Office 365 group membership sync to the team. Like other Office 365 Groups, Teams come auto-provisioned with an Exchange mailbox, a SharePoint site, a OneNote notebook, and other assets within Office 365. [Learn more about Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

**Canais**

Channels are the collaboration spaces within a team where the actual work is done. Each channel represents a different topic or workstream within the overall team. For each channel, a folder is automatically created on the SharePoint site to store all files shared to that channel, making it easy for users to find and work on the documents they care about. Channels can also be extended with apps that are relevant to the particular workstream—for example, you can add a Power BI dashboard to a channel to track the success of one aspect of your project.

**Tipos de acesso de equipe**

Determinam quem pode ingressar na equipe:

-   _Private_ teams are restricted to team members approved by the team owner(s). This is a typical setting for project teams and virtual teams in a large organization.
-   _Public_ teams are open for anyone in the organization to join directly. This is useful for collaboration on topics of general interest to people in different departments working on different projects. This is a good default setting for smaller organizations.

**Tipos de usuários de equipes e funções administrativas** 

Os tipos de usuários da equipe determinam o grau de controle que cada membro da equipe tem:

-   _Team creator_ has permissions to create a group or team in the directory. The admin can constrain this user type to a subset of admins or users. For more information, see [Manage who can create Office 365 Groups](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618). 
-   _Team owner_ manages membership and settings for the team. There can be as many as 10 team owners per team.
-   Um _membro da equipe_ é um membro de sua organização que participa de uma equipe.
-   _Guest_ is a user who’s external to your organization. Anyone with an email address can be invited as a guest if your organization has enabled [guest access](guest-access.md).

> [!Note]
> Saiba mais sobre os recursos de proprietário de equipe e de membro de equipe no artigo [Atribuir função e permissões no Microsoft Teams](assign-roles-permissions.md).

Teams admin roles determine what capabilities each admin role holder has. These are described in the following table.

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%">Função&nbsp;&nbsp;</th>
    <th width="25%">Descrição</th>
    <th width="60%">Pode realizar as tarefas a seguir, usando as ferramentas indicadas</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2">Administrador de Serviço de Equipes</td>
    <td valign="top">Gerenciar o serviço de Equipes e criar e gerenciar Grupos do Office 365</td>
    <td valign="top">Gerenciar reuniões, inclusive políticas de reunião, configurações e pontes de conferência<sup>1</sup><br><br>Gerenciar voz, inclusive políticas de chamada, inventário e atribuição de números de telefone, filas de chamadas e atendedores automáticos<sup>1</sup><br><br>Gerenciar mensagens, inclusive políticas de mensagens<sup>1</sup><br><br>Gerenciar todas as configurações de toda a organização, inclusive federação, atualização do Teams e configurações de cliente do Teams<sup>1</sup><br><br>Gerenciar as equipes na organização e as configurações associadas, inclusive associação<sup>2</sup><br><br>Exibir a página de perfil do usuário e solucionar problemas de qualidade de chamada do usuário usando o conjunto de ferramentas avançado de solução de problemas<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Administrador de Comunicações de Equipes</td>
<td valign="top">Gerenciar recursos de chamadas e reuniões no serviço Microsoft Teams</td>
<td valign="top">Gerenciar reuniões, inclusive políticas de reunião, configurações e pontes de conferência<sup>1</sup><br><br>Gerenciar voz, inclusive políticas de chamada, inventário e atribuição de números de telefone, filas de chamadas e atendedores automáticos<sup>1</sup><br><br>Exibir a página de perfil do usuário e solucionar problemas de qualidade de chamadas do usuário usando o conjunto de ferramentas avançado de solução de problemas<sup>1</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Especialista em Comunicações de Equipes</td>
<td valign="top">Solucionar problemas de comunicação no Teams usando ferramentas básicas</td>
<td valign="top">Access to the user profile page for troubleshooting calls in Call Analytics. Can only view user information for the specific user being searched for.<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Engenheiro de Suporte de Comunicações de Equipes</td>
<td valign="top">Solucionar problemas de comunicação no Teams usando ferramentas avançadas</td>
<td valign="top">Access to the user profile page for troubleshooting calls in Call Analytics. Can view the full call record information.<sup>3</sup></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3"><a href="https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">PowerShell - módulo do Skype for Business</a> ou <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Centro de administração do Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">PowerShell - módulo do Microsoft Teams</a> ou <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Centro de administração do Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3"><a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Centro de administração do Microsoft Teams</a> apenas</td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a>Decisões de TI a serem tomadas antes de começar

Before you roll Teams out to your organization, implement any governance policies that your organization has decided it requires. These can include items like naming conventions, expiration policies, retention policies, and more. Generally speaking, it’s much easier to implement these requirements prior to scaling your deployment across your organization.

Para obter mais informações, confira [Planejar a governança no Teams](plan-teams-governance.md).

## <a name="teams-lifecycle-stages"></a>Etapas do ciclo de vida de equipes

Generally speaking, a team has a purpose that’s aligned with a project or accomplishing a goal. Even if a team was formed based on a shared interest, the team membership will probably change over time and the discussion might grow stale—only to surface again in a slightly different way in a different team.

Cada equipe tem um começo, quando ela é criada e os canais são configurados; um meio, quando a equipe é usada e a colaboração ocorre para corresponder ao ritmo do fluxo de trabalho; e, às vezes, um fim, quando a equipe conclui seu propósito e chega ao fim da vida útil. 

Para obter mais informações, confira [Gerenciar equipes no Centro de administração do Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="stage-1-beginning"></a>Etapa 1: início

#### <a name="create-the-team"></a>Criar a equipe

The first step is to define the goal of the team (which can range from business processes to org structure to projects, or simply creating an open, unstructured collaboration hub). Defining the team goal goes hand in hand with identifying the right people. As far as practicable, it’s a good idea to foster open collaboration by aiming for broad membership. 

Os proprietários da equipe convidam membros, definem a imagem e a descrição da equipe e podem definir permissões para membros individuais. 

> [!Tip]
>  O ideal é selecionar pelo menos dois proprietários para a equipe. Assim, ela estará coberta em caso de ausência ou a reatribuição.

#### <a name="team-origins"></a>Origens da equipe

As equipes podem ser criadas por meio de diversos métodos:

-   Create the team from scratch. Add members by using individual email aliases or usernames, or expand a distribution list.
-   Create the team from an existing team, and use its channel configuration and any app configuration as a template. You can optionally also use its membership list.
-   Adicione uma equipe a um Grupo do Office 365 existente. Assim, a equipe também terá acesso à caixa de correio e ao site do SharePoint do grupo.
-   Use the Microsoft Graph Teams APIs or PowerShell cmdlets to create teams. The APIs can programmatically create teams based on Global Address Book attributes (such as region or department) or business processes (client engagements or classroom rosters, for example).

Use estes links para obter mais informações sobre como organizar as equipes:

-   [Práticas recomendadas para organizar equipes no Teams](best-practices-organizing.md)
-   [Implantar chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [Implantar reuniões e conferências](deploy-meetings-microsoft-teams-landing-page.md)
-   [Implantar o Cloud Voice](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Qual é o objetivo da equipe?</li><li>Quem pertence à equipe?</li><li>A equipe será privada ou pública?</li><li>Os novos membros podem adicionar a si mesmos ou os proprietários da equipe devem adicioná-los?</li><li>Quem terá permissões para criar canais ou adicionar guias, bots e conectores?</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Crie a equipe.</li><li>Planeje canais.</li></ul>|


#### <a name="set-up-channels"></a>Configure canais

Qualquer proprietário ou membro de equipe com permissões apropriadas pode criar canais em uma equipe. É importante considerar o objetivo de cada canal. As opções incluem colaboração em referência a projetos, discussões de tópicos ou áreas de interesse comum. Por padrão, todas as equipes incluem um canal Geral. A maioria das equipes precisa de mais do que isso, e os membros criarão canais adicionais. É provável que o conjunto de canais cresça de forma gradual, à medida que novos tópicos ou projetos surgirem. As discussões poderão ultrapassar os limites do canal em que começaram.

Para despertar interesse, o proprietário do canal pode postar uma mensagem de boas-vindas, carregar documentos relevantes na guia **Arquivos** ou adicionar guias ou conectores ao canal. O proprietário também define a descrição do canal e pode "adicionar a Favoritos automaticamente" os canais importantes para que eles sejam listados por padrão para todos os membros da equipe.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Que canais iniciais serão adicionados à equipe?</li><li>Que diretrizes, se houver, serão fornecidas para a adição de novos canais? (Eles serão configurados por projeto, por tópico ou...?)</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Crie canais iniciais.</li><li>Poste uma mensagem de boas-vindas.</li><li>Comece a colaborar.</li></ul>|

### <a name="stage-2-middle"></a>Estágio 2: meio

À medida que o trabalho em equipe começa, a associação à equipe provavelmente começa a evoluir, juntamente com a hierarquia de canais. A menos que a equipe precise ser estritamente controlada e bloqueada, convém incentivar a exploração, mesmo que isso leve a impasses. À medida que os usuários se sentirem mais à vontade, poderão experimentar menções de \@equipe, marcar canais como favoritos e usar o canal Geral para se familiarizarem com as postagens. Cada equipe é diferente. Deixe que o uso oriente a evolução do design. Monitore o uso e a integridade da equipe por meio dos recursos de relatórios do Teams.

A confiança, a tolerância e o espírito de colaboração aumentarão gradativamente, à medida que as comunicações dos grupos-chave forem iniciadas e mantidas no Teams. Os membros da equipe veem a utilidade das conversas em grupo, em comparação com os chats entre duas pessoas. Equipes individuais tendem a desenvolver sua própria personalidade, auxiliadas por recursos divertidos, como Giphys e figurinhas. Ao mesmo tempo, é importante que o comportamento nocivo ou rude seja desencorajado sempre que ocorrer.

Como as equipes são semelhantes a organismos vivos, ocasionalmente precisam ser verificadas e cuidadas. Estas são algumas das práticas recomendadas:

-   Use defensores para manter o uso, se ele começar a diminuir, e também para descobrir e propagar novos comportamentos criativos. 
-   Gerencie os convidados criteriosamente, garantindo que o acesso deles seja encerrado quando a necessidade de negócios terminar.
-   Permita que os canais evoluam junto com as necessidades de negócios. Adicione novos canais conforme necessário e deixe que os antigos desapareçam (ou considere arquivá-los ou excluí-los, se eles contiverem dados confidenciais ou efêmeros, com base em seus requisitos de retenção).
-   Crie novas equipes à medida que surgirem grupos ou áreas de interesse maiores.
-   Experimente diferentes colaborações de canal, como reuniões de canal ou conversas de guias referentes a documentos.

Se uma equipe começar a cair na rotina, considere estas opções:

-   Direcione as comunicações para as equipes, em vez de enviar emails.
-   Use aplicativos móveis para aumentar o envolvimento.
-   Reduza o número de canais.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Quem monitorará o uso para identificar problemas?</li><li>Que métricas serão usadas para determinar a integridade de uma equipe?</li><li>Identifique equipes que chegaram ao fim de sua vida útil.</li><li>Identifique equipes não íntegras que ainda servem a um propósito, mas precisam ser revigoradas.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>Implemente um processo para monitorar a integridade de equipes individuais.</li></ul>|

### <a name="stage-3-end"></a>Etapa 3: fim

Quando o trabalho de uma equipe chega ao fim, é importante reconhecer formalmente que ela terminou. Assim, os membros da equipe são informados do encerramento. Além disso, é impedido o acesso a informações desatualizadas e obsoletas. Você pode usar a própria equipe para realizar tarefas de encerramento, como post-mortems e resumos executivos.

Você pode excluir equipes que sabe que não são necessárias (por exemplo, uma equipe criada exclusivamente para testes ou que contém dados confidenciais). Na verdade, as equipes são excluídas com uma “exclusão reversível” que a TI pode reverter por até 21 dias (30 dias para Grupos do Office 365). A exclusão de equipes não afeta os chats nem o conteúdo retidos de acordo com políticas de conformidade.

Você também pode usar as políticas de expiração e retenção, além de recursos de arquivamento, para reduzir a exposição de equipes que não estão mais ativas ou cujos proprietários deixaram a organização.

Para obter informações sobre como configurar políticas de expiração e retenção, confira [Visão geral de segurança e conformidade no Microsoft Teams](security-compliance-overview.md).

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Defina como é o fim da vida útil de uma equipe.</li><li>Decida se deseja manter o conteúdo de uma equipe disponível e por quanto tempo.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Documente as práticas recomendadas e as lições aprendidas.</li><li>Arquive os dados, se necessário.</li></ul>|

