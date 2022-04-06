---
title: Conheça os aplicativos no Microsoft Teams
ms.reviewer: ''
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
ms.openlocfilehash: bb3d38060a9538196795e3da7b325840321814d8
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686388"
---
# <a name="about-apps-in-microsoft-teams"></a>Sobre aplicativos no Microsoft Teams

Os aplicativos são uma ótima maneira de reunir suas ferramentas e serviços do local de trabalho e colaborar com outras pessoas. Os aplicativos ajudam os usuários finais a serem mais produtivos, colaborativos e eficazes em suas tarefas diárias. As organizações usam aplicativos para se conectar com seus clientes, fornecer serviços e compartilhar informações. Os aplicativos permitem que os usuários sejam mais eficazes Teams chats, reuniões e canais. Exemplos são os usuários finais que usam um Calendário fixado no Teams para colaborar rapidamente com outras pessoas, um aplicativo com funcionalidade de bots informando os usuários de QoS de um serviço Web em um canal do Teams e um aplicativo para compartilhar e atribuir tarefas a vários usuários finais em um canal.

Nossa ampla seleção de aplicativos validados e seguros na loja fornece aos usuários finais acesso às ferramentas e serviços de que sua organização precisa todos os dias. Microsoft Teams aplicativos são aplicativos SaaS baseados na Web que não precisam ser implantados. Os usuários finais podem usar aplicativos Teams com base apenas nas permissões fornecidas por você. Como administrador, basta aprovar ou bloquear o uso de qualquer aplicativo para os usuários da sua organização. Você controla a disponibilidade de aplicativos para todos os usuários em reuniões, chats e canais.

Para fornecer aos usuários finais os aplicativos de que precisam, continue a ler para entender os tipos de aplicativos e onde os usuários acessam esses aplicativos. Para saber mais sobre o uso de aplicativos, leia Visão [geral dos aplicativos para usuários finais](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

Os diferentes tipos de aplicativos que os usuários finais podem usar Teams são:

* [Principais aplicativos que fazem parte Teams](#core-apps).
* Outros [aplicativos criados pela Microsoft](#microsoft-provided-apps).
* [Aplicativos de terceiros](#third-party-apps-validated-by-microsoft) por parceiros (validados pela Microsoft).
* [Aplicativos personalizados](#custom-apps) criados por sua própria organização.

## <a name="core-apps"></a>Principais aplicativos

Algumas funcionalidades padrão, como feed de atividades, Teams canais, chat, calendário e chamadas, estão disponíveis e fixadas por padrão para facilitar o acesso para os usuários finais. Como administrador, você pode modificar o comportamento padrão usando a política [de instalação](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Os aplicativos principais são os aplicativos fixados Teams por padrão." lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Aplicativos fornecidos pela Microsoft

A Microsoft fornece muitos aplicativos para melhorar a produtividade e a colaboração. Você e os usuários finais podem encontrar esses aplicativos procurando a Microsoft listada como o Publisher no centro de administração ou listadas como Provedor no repositório de equipes.

O Teams vem com um conjunto de aplicativos integrados, incluindo listas, Tarefas, Elogiar, Aprovações e muito mais. Recomendamos que você inclua os aplicativos do Microsoft Teams - como o Planner - na implementação inicial do Microsoft Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Aplicativos da Microsoft no Teams de administração" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Aplicativos de terceiros validados pela Microsoft

Além dos aplicativos fornecidos pela Microsoft, você pode usar aplicativos de terceiros validados pela Microsoft. A Microsoft valida a funcionalidade e a segurança desses aplicativos antes de disponibilizar esses aplicativos Teams armazenamento. Para entender os benefícios da validação do aplicativo, consulte [a validação de aplicativos de terceiros](overview-of-app-validation.md).

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Um exemplo de aplicativos de terceiros na Teams store":::

## <a name="custom-apps"></a>Aplicativos personalizados

Os aplicativos criados por desenvolvedores em sua organização são chamados de aplicativos personalizados. O desenvolvimento desse aplicativo é solicitado para requisitos específicos da sua organização e você tem controles para permitir ou não permitir esses aplicativos. Os desenvolvedores em sua organização podem criar rapidamente soluções personalizadas de baixo código usando Teams integração com o [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Depois que um administrador permitir o uso de aplicativos personalizados, os usuários finais encontrarão esses aplicativos clicando em Compilar para sua organização na navegação à esquerda da Teams store.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Aplicativos personalizados Teams loja no Teams da área de trabalho" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>Entender o sideload de aplicativos personalizados

Ao desenvolver aplicativos personalizados e antes de distribuí-los aos usuários finais, os desenvolvedores testam os aplicativos adicionando-os à loja para testar por conta própria ou testar com uma equipe na qual eles fazem sideload do aplicativo. Esse método é chamado de sideload de aplicativos e se aplica somente a aplicativos personalizados.

Os desenvolvedores podem fazer sideload de um aplicativo para dispo-lo para os membros de uma equipe específica, normalmente para testar um aplicativo em desenvolvimento. Isso não exigirá aprovação do administrador se o sideload for permitido. Como administrador, você pode não permitir o sideload para qualquer desenvolvedor.

Se você não permitir o sideload, os desenvolvedores ainda poderão testar seus aplicativos em um [locatário de teste](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Após a conclusão do desenvolvimento de aplicativos personalizados, os desenvolvedores solicitam que os administradores distribuam seus aplicativos personalizados para os usuários finais. Para obter detalhes, [confira como publicar um aplicativo personalizado](/microsoftteams/upload-custom-apps). Como administrador, você pode permitir ou não o uso de um aplicativo personalizado para usuários específicos.

### <a name="about-app-templates"></a>Sobre modelos de aplicativo

Os modelos de aplicativo para Teams são aplicativos de exemplo funcionais e prontos para produção criados pela Microsoft para ilustrar casos de uso populares, demonstrar as práticas recomendadas de desenvolvimento de aplicativos e fornecer aplicativos de software livre que os desenvolvedores podem estender para criar aplicativos personalizados. Os desenvolvedores de sua organização personalizam modelos de aplicativo para suas necessidades de organização com alterações simples no código disponível GitHub. Como administrador, você fornece esses aplicativos como aplicativos personalizados para os usuários finais.

Para saber mais, confira [Microsoft Teams modelos de aplicativo](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="understand-app-capabilities"></a>Entender os recursos do aplicativo

Para fornecer experiências avançadas que permitem que os usuários finais trabalhem dentro do Teams, os desenvolvedores de aplicativos aproveitam os recursos de aplicativo a seguir. As extensões de mensagens permitem que os usuários interajam com seu serviço Web Teams cliente. Eles pesquisam ou iniciam ações em um sistema externo. Você pode enviar o resultado da interação para o cliente Teams como um cartão com formatação avançada. A reunião de aplicativos de extensibilidade integra os aplicativos de um desenvolvedor em reuniões e oferece uma experiência responsiva na reunião.

Os bots também são chamados de chatbot ou bot de conversa. É um aplicativo que executa tarefas simples e repetitivas. Uma interação de bot pode ser uma pergunta e resposta rápidas ou pode ser uma conversa complexa que fornece acesso a serviços ou assistência. Os usuários podem conversar um pouco um para um ou em um canal. Por exemplo, você pode usar o aplicativo Polly para criar pesquisas rápidas, obter comentários e fazer uma verificação de pulso.

As guias são Teams páginas da Web com reconhecimento de conteúdo fixadas na parte superior de um canal ou chat. As guias permitem que você interaja com conteúdo e serviços com uma experiência semelhante à Web. Você pode adicionar guias como parte de um canal dentro de uma equipe, chat em grupo ou aplicativo pessoal para um usuário individual.

Webhooks e conectores fornecem conteúdo e atualizações de serviços que os usuários finais usam com frequência (como Jira Cloud e Bitbucket) diretamente em uma conversa de canal. Os aplicativos que usam essa funcionalidade podem se comunicar com aplicativos externos e podem enviar ou receber notificações e mensagens de um serviço externo.

Extensões de mensagens são atalhos para inserir conteúdo do aplicativo ou agir em uma mensagem sem que os usuários finais precisem sair da conversa. As extensões de mensagens podem ter comandos de pesquisa para que os usuários finais localizem rapidamente o conteúdo externo e o insiram em uma mensagem ou comandos de ação.

Para exibir casos de uso comuns mapeados Teams recursos, consulte Mapear seus casos de [uso para Teams recursos do aplicativo](/microsoftteams/platform/concepts/design/map-use-cases).

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
