---
title: Conheça os aplicativos no Microsoft Teams
ms.reviewer: null
description: Saiba mais sobre aplicativos e decida quais aplicativos permitir no Teams com base no perfil e nos requisitos de negócios da sua organização.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
  - M365-collaboration
f1.keywords:
  - NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
  - Microsoft Teams
ms.custom: seo-marvel-apr2020
---
# <a name="about-apps-in-microsoft-teams"></a>Sobre aplicativos no Microsoft Teams

Os aplicativos são uma ótima maneira de reunir suas ferramentas e serviços de local de trabalho e colaborar com outras pessoas. Os aplicativos ajudam os usuários finais a serem mais produtivos, colaborativos e eficazes em suas tarefas diárias. As organizações usam aplicativos para se conectar com seus clientes, fornecer serviços e compartilhar informações. Os aplicativos permitem que os usuários sejam mais eficazes Teams chats, reuniões e canais. Exemplos são usuários finais que usam um Calendário fixado no Teams para colaborar rapidamente com outras pessoas, um aplicativo com funcionalidade de bots informando aos usuários sobre qoS de um serviço Web em um canal Teams e um aplicativo para compartilhar e atribuir tarefas a vários usuários finais em um canal.

Nossa ampla seleção de aplicativos validados e seguros na loja fornece aos usuários finais acesso às ferramentas e serviços que sua organização precisa todos os dias. Microsoft Teams aplicativos são aplicativos SaaS baseados na Web que não precisam ser implantados. Os usuários finais podem usar aplicativos Teams somente com base nas permissões fornecidas por você. Como administrador, basta aprovar ou bloquear o uso de qualquer aplicativo para os usuários da sua organização. Você controla a disponibilidade de aplicativos para todos os usuários em reuniões, chats e canais.

Para fornecer aos usuários finais os aplicativos necessários, leia para entender os tipos de aplicativos e onde os usuários acessam esses aplicativos. Para saber mais sobre o uso de aplicativos, leia [Visão geral dos aplicativos para usuários finais](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

Os diferentes tipos de aplicativos que os usuários finais podem usar Teams são:

* [Principais aplicativos que fazem parte Teams](#core-apps).
* Outros [aplicativos criados pela Microsoft](#microsoft-provided-apps).
* [Aplicativos de terceiros](#third-party-apps-validated-by-microsoft) por parceiros (validados pela Microsoft).
* [Aplicativos personalizados](#custom-apps) criados por sua própria organização.

## <a name="core-apps"></a>Principais aplicativos

Algumas funcionalidades padrão, como feed de atividade, Teams canais, chat, calendário e chamadas estão disponíveis e fixados por padrão para facilitar o acesso para usuários finais. Como administrador, você pode modificar o comportamento padrão usando a [política de instalação](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Os aplicativos principais são os aplicativos fixados Teams por padrão." lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Aplicativos fornecidos pela Microsoft

A Microsoft fornece muitos aplicativos para melhorar a produtividade e a colaboração. Você e os usuários finais podem encontrar esses aplicativos procurando a Microsoft listada como o Publisher no centro de administração ou listadas como Provedor no Armazenamento de Equipe.

O Teams vem com um conjunto de aplicativos integrados, incluindo listas, Tarefas, Elogiar, Aprovações e muito mais. Recomendamos que você inclua os aplicativos do Microsoft Teams - como o Planner - na implementação inicial do Microsoft Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Aplicativos da Microsoft no Teams de administração" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Aplicativos de terceiros validados pela Microsoft

Além dos aplicativos fornecidos pela Microsoft, você pode usar aplicativos de terceiros validados pela Microsoft. A Microsoft valida a funcionalidade e a segurança desses aplicativos antes de disponibilizar esses aplicativos Teams store.

<!--- TBD: Link to the new article later when it is created.
To understand the benefits of app validation, see [validation of third-party apps]().

--->

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Um exemplo de aplicativos de terceiros no Teams store":::

<!--- TBD: Check the relevance of this link here.
For more information, see [Microsoft Teams App Security and Compliance](/microsoft-365-app-certification/teams/teams-apps).
--->

## <a name="custom-apps"></a>Aplicativos personalizados

Os aplicativos criados por desenvolvedores em sua organização são chamados de aplicativos personalizados. O desenvolvimento desse aplicativo é encomendado para requisitos específicos da sua organização e você tem controles para permitir ou não esses aplicativos. Os desenvolvedores em sua organização podem criar rapidamente soluções personalizadas de baixo código usando Teams integração com o [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Depois que um administrador permite o uso de aplicativos personalizados, os usuários finais encontram esses aplicativos clicando em **Built for your org** na navegação esquerda do Teams store.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Aplicativos personalizados Teams no Teams da área de trabalho" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>Compreender o sideload de aplicativos personalizados

Ao desenvolver aplicativos personalizados e antes de distribuí-los aos usuários finais, os desenvolvedores testam os aplicativos adicionando-os à loja para testar por conta própria ou testar com uma equipe na qual eles sideload o aplicativo. Esse método é chamado de sideload de aplicativos e se aplica somente a aplicativos personalizados.

Os desenvolvedores podem fazer sideload de um aplicativo para torná-lo disponível para os membros de uma equipe específica, normalmente para testar um aplicativo de sub-desenvolvimento. Isso não requer aprovação do administrador se o sideload for permitido. Como administrador, você pode não permitir o sideload para qualquer desenvolvedor.

Se você não permitir o sideload, os desenvolvedores ainda poderão testar seus aplicativos em um locatário [de teste](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Depois que o desenvolvimento de aplicativos personalizados é concluído, os desenvolvedores solicitam que os administradores distribuam seus aplicativos personalizados para os usuários finais. Para obter detalhes, [consulte como publicar um aplicativo personalizado](/microsoftteams/upload-custom-apps). Como administrador, você pode permitir ou não usar um aplicativo personalizado para usuários específicos.

### <a name="about-app-templates"></a>Sobre modelos de aplicativos

Modelos de aplicativo para Teams são aplicativos de exemplo funcionais e prontos para produção criados pela Microsoft para ilustrar casos de uso popular, mostrar práticas recomendadas de desenvolvimento de aplicativos e fornecer aplicativos de código aberto que os desenvolvedores podem estender para criar aplicativos personalizados. Os desenvolvedores da sua organização personalizam modelos de aplicativo para suas necessidades de organização com alterações simples no código disponível GitHub. Como administrador, você fornece esses aplicativos como aplicativos personalizados para seus usuários finais.

Para saber mais, consulte [Microsoft Teams Modelos de Aplicativo.](https://adoption.microsoft.com/microsoft-teams/app-templates/)

## <a name="understand-app-capabilities"></a>Compreender os recursos do aplicativo

Os aplicativos de mensagens incluem conteúdo de um aplicativo em um canal ou chat. A reunião de aplicativos de extensibilidade integra os aplicativos de um desenvolvedor em reuniões e oferece uma experiência responsiva na reunião. Para fornecer várias funcionalidades, os desenvolvedores de aplicativo aproveitam os seguintes recursos de aplicativo.

Os bots fornecem respostas, atualizações e assistência. Você pode conversar com aqueles um-a-um ou dentro de um canal. Eles podem ajudar com o gerenciamento de tarefas, agendamento e muito mais. Por exemplo, você pode usar o aplicativo Polly para criar pesquisas rápidas, obter comentários e fazer uma verificação de pulsação.

As guias fixadas na parte superior de um canal permitem que você interaja com conteúdo e serviços com uma experiência como a Web.
Os conectores oferecem conteúdo e atualizações de serviços que você usa com frequência (como Jira Cloud e Bitbucket) diretamente em uma conversa de canal.

Extensões de mensagens são atalhos para inserir conteúdo do aplicativo ou para agir em uma mensagem sem que os usuários finais tenha que navegar para longe da conversa. As extensões de mensagens podem ter comandos de pesquisa para que os usuários finais encontrem rapidamente o conteúdo externo e o insiram em comandos de mensagem ou ação.

Para exibir casos de uso comum mapeados para Teams recursos, consulte Mapear seus casos de uso [para Teams recursos do aplicativo](/microsoftteams/platform/concepts/design/map-use-cases).

<!--- TBD: Admins do many considerations and decisions around app adoption and app governance. These are to be covered in a separate article. Commenting the below content for now as part of this article revamp.

## Apps deployment decisions

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

## Core deployment decisions

These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).

### App availability settings

Teams provides many apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.
Get apps from the Teams Store. By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users. For example, users can use the Planner app to build and manage team tasks in Teams.

By default, all Microsoft-provided, third-party, and custom apps are available, and you can turn individual apps on or off. There are org-wide settings that let you turn all third-party and/or custom apps on or off for your entire organization.

| Ask yourself | Action |
|--------------|--------|
|Will you change the default Teams apps settings? | For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### App permissions and other considerations

Apps are consented to by users and managed by the admin or IT pro through policies. However, app permissions and risk profile are defined in the app itself.

| Ask yourself | Action |
|--------------|--------|
|<br>Which apps do I want to allow access to? Which ones do I not want to allow access to?  | <ul><li>See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</li><li>See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</li></ul>|

--->

<!--- TBD: Rewrite this to talk about bots and tabs as a capability of apps. Admins do not govern bots, tabs, etc. Admins only govern apps that contain capabilities such as connectors, bots, etc. This writeup gives an impression that admins manage apps + bots + tabs + connectors, etc.

### Bots for private chats and channels

Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat. Teams supports bots in private chats and channels. Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom bots in my organization?|For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### Built-in and custom tabs

Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services. Add tabs to help users access and manage the data they need or use the most. In channels, the Conversations and Files tabs are created by default. In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default. In addition to these built-in tabs, you can design and add custom tabs. To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](/microsoftteams/platform/tabs/what-are-tabs).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

<!--- TBD: Activity reports is not part of app overview. Commenting for now. To be reused in a different article later.

### Activity reports

You can use activity reports to see how users in your organization are using Teams. For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative. Your organization can use the activity reports to decide where to prioritize training and communication efforts. To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.

| Ask yourself | Action |
|--------------|--------|
| <br>Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
