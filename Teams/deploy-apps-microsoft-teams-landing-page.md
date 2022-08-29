---
title: Conheça os aplicativos no Microsoft Teams
ms.reviewer: ''
description: Saiba mais sobre aplicativos e decida quais aplicativos permitir no Teams com base no perfil e nos requisitos de negócios da sua organização.
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-collaboration
- m365-frontline
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: 78f0f0857884f70d5e758b1c52e13341c15faa0e
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397192"
---
# <a name="understand-microsoft-teams-apps"></a>Entenda os aplicativos do Microsoft Teams

Os aplicativos são uma ótima maneira de reunir suas ferramentas e serviços do local de trabalho e colaborar com outras pessoas. Os aplicativos ajudam os usuários finais a serem mais produtivos, colaborativos e eficazes em suas tarefas diárias. As organizações usam aplicativos para se conectar com seus clientes, fornecer serviços e compartilhar informações. Exemplos são usuários finais usando um aplicativo de Calendário do Outlook fixado no Teams para colaborar rapidamente com outras pessoas, um aplicativo com funcionalidade de bots que informa os usuários sobre a qualidade de um serviço Web em um canal do Teams e um aplicativo para compartilhar e atribuir tarefas a vários usuários finais em um canal.

Nosso amplo catálogo de aplicativos validados e seguros na Loja do Teams fornece aos usuários finais acesso às ferramentas e serviços de que sua organização precisa todos os dias. Os aplicativos do Microsoft Teams são aplicativos SaaS baseados na Web que não precisam ser implantados. Os usuários finais podem usar aplicativos no Teams com base apenas nas [permissões fornecidas por você](app-policies.md). Como administrador, você usa políticas de nível empresarial para permitir ou bloquear qualquer aplicativo para os usuários da sua organização. Você controla a disponibilidade de aplicativos para cada usuário em vários contextos, como reuniões, bate-papos e canais.

Este artigo ajuda você a entender os tipos de aplicativos e de onde os seus usuários acessam esses aplicativos. Para saber mais sobre o uso de aplicativos, leia [Visão geral dos aplicativos para usuários finais](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

Os diferentes tipos de aplicativos que os usuários finais podem usar no Teams são:

* [Principais aplicativos que fazem parte do Teams](#core-apps).
* Outros [aplicativos criados pela Microsoft](#microsoft-provided-apps).
* [Aplicativos de terceiros](#third-party-apps-validated-by-microsoft) por parceiros (validados pela Microsoft).
* [Aplicativos personalizados](#custom-apps) criados por sua própria organização.

## <a name="core-apps"></a>Principais aplicativos

Algumas funcionalidades do Teams, como feed de atividades, equipes, chat, calendário, chamadas, arquivos e tarefas (locatários educacionais), estão disponíveis e fixadas por padrão para facilitar o acesso dos usuários finais. Para trabalhadores da linha de frente, somente atividades, turnos, chat e chamadas estão disponíveis e fixadas. Como um administrador, você pode modificar este comportamento padrão usando a [política de instalação](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Os aplicativos principais são os aplicativos fixados no Teams por padrão." lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Aplicativos fornecidos pela Microsoft

A Microsoft fornece muitos aplicativos para melhorar a produtividade e a colaboração. Você e os usuários finais podem encontrar esses aplicativos procurando a Microsoft listada como fornecedor no centro de administração do Teams ou listadas como provedor na loja do Teams.

O Teams vem com um conjunto de aplicativos integrados, incluindo listas, Tarefas, Elogiar, Aprovações e muito mais. Recomendamos que você inclua os aplicativos em destaque—como o Planner—em sua distribuição inicial do Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Captura de tela de aplicativos da Microsoft no centro de administração do Teams." lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Aplicativos de terceiros validados pela Microsoft

Além dos aplicativos fornecidos pela Microsoft, você pode usar aplicativos de terceiros certificados pela Microsoft. A Microsoft valida a funcionalidade e a segurança desses aplicativos antes de disponibilizar esses aplicativos na loja do Teams. Para entender os benefícios da validação do aplicativo, consulte a [validação de aplicativos de terceiros](overview-of-app-validation.md).

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Captura de tela de um exemplo de aplicativos de terceiros na loja do Teams.":::

## <a name="custom-apps"></a>Aplicativos personalizados

Os aplicativos criados por desenvolvedores em sua organização são chamados de aplicativos personalizados (ou aplicativos de Linha de Negócios). A sua organização pode encomendar a criação de aplicativos personalizados para requisitos específicos da organização. Você tem o controle para permitir ou bloquear esses aplicativos para toda a organização ou para usuários específicos. Os desenvolvedores podem criar soluções personalizadas de baixo código usando a integração do Teams com o [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Depois que um administrador permite o uso de aplicativos personalizados, os usuários finais encontram esses aplicativos selecionando **Criado para sua organização** na navegação à esquerda da loja do Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Captura de tela de aplicativos personalizados na loja do Teams no aplicativo de desktop do Teams." lightbox="media/built-for-your-org2.png":::

Para obter mais informações, confira [Entender e gerenciar aplicativos personalizados e com sideload](custom-app-overview.md).

## <a name="about-app-templates"></a>Sobre Modelos de Aplicativo

Usando os métodos de desenvolvimento de aplicativos, a Microsoft cria e fornece aplicativos de exemplo funcionais e prontos para produção. Coletivamente, esses aplicativos são chamados de modelos de aplicativo para o Teams e são fornecidos para:

* Ilustrar alguns casos de uso de colaboração no Teams.
* Demonstrar práticas recomendadas e métodos de desenvolvimento de aplicativos.
* Forneça aplicativos de software livre que os desenvolvedores podem estender para criar seus próprios aplicativos.

Os desenvolvedores de sua organização personalizam modelos de aplicativo com alterações simples no código-fonte fornecido. Você fornece esses aplicativos como aplicativos personalizados para seus usuários finais, para atender às necessidades de qualquer organização.

Para saber mais, confira [Modelos de Aplicativo do Microsoft Teams](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="understand-app-capabilities"></a>Entender os recursos do aplicativo

Para fornecer experiências avançadas que permitem que os usuários finais trabalhem no Teams, os desenvolvedores de aplicativos usam os seguintes recursos de aplicativo. As extensões de mensagens permitem que os usuários interajam com o cliente do Teams do serviço Web. Eles pesquisam ou iniciam ações em um sistema externo. Você pode enviar o resultado da interação para o cliente do Teams como um cartão com formatação avançada. A reunião de aplicativos de extensibilidade integra os aplicativos de um desenvolvedor em reuniões e oferece uma experiência dinâmica na reunião.

Os bots também são chamados de chatbot ou bot de conversa. É um aplicativo que executa tarefas simples e repetitivas. Uma interação de bot pode ser uma pergunta e resposta rápidas ou pode ser uma conversa complexa que fornece acesso a serviços ou assistência. Os usuários podem conversar com um bot individualmente ou em um canal. Por exemplo, você pode usar o aplicativo Polly para criar pesquisas rápidas, obter comentários e fazer uma avaliação do clima empresarial.

As guias são páginas da Web compatíveis com o Teams fixadas na parte superior de um canal ou chat. As guias permitem que você interaja com conteúdo e serviços com uma experiência semelhante à Web. Você pode adicionar guias como parte de um canal dentro de uma equipe, chat em grupo ou aplicativo pessoal para um usuário individual.

Webhooks e conectores fornecem conteúdo e atualizações de serviços que os usuários finais usam com frequência (como Jira Cloud e Bitbucket) diretamente em uma conversa de canal. Os aplicativos que usam essa funcionalidade podem se comunicar com aplicativos externos e podem enviar ou receber notificações e mensagens de um serviço externo.

Extensões de mensagens são atalhos para inserir conteúdo do aplicativo ou agir em uma mensagem sem que os usuários finais precisem sair da conversa. As extensões de mensagens podem ter comandos de pesquisa para que os usuários finais localizem rapidamente o conteúdo externo e o insiram em uma mensagem ou comandos de ação.

Para exibir casos de uso comuns mapeados para recursos do Teams, consulte [Mapear seus casos de uso para recursos de aplicativo do Teams](/microsoftteams/platform/concepts/design/map-use-cases).

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
| Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->

## <a name="related-articles"></a>Artigos relacionados

* [Saiba mais sobre modelos de aplicativo para o Teams](/microsoftteams/platform/samples/app-templates).
