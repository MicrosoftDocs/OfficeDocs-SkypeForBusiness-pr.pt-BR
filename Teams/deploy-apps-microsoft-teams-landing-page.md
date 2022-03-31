---
title: Conheça os aplicativos no Microsoft Teams
ms.reviewer: ''
description: Saiba mais sobre aplicativos e decida quais aplicativos permitir no Teams com base no perfil e nos requisitos de negócios da sua organização.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 02/10/2021
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
ms.openlocfilehash: b6fd5ef344550cf85420faef1748c34f6e87e88b
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556522"
---
# <a name="about-apps-in-microsoft-teams"></a>Sobre aplicativos no Microsoft Teams

Os aplicativos permitem que os usuários localizem conteúdo de seus serviços favoritos e o compartilhem no Teams. Eles permitem que você realize tarefas como fixar serviços na parte superior de um canal, automatizar notificações usando bots ou compartilhar e atribuir tarefas. Para saber mais sobre o uso de aplicativos, leia [Visão geral dos aplicativos para usuários finais](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

Os diferentes tipos de aplicativos que os usuários finais podem usar no Teams são aplicativos criados pela Microsoft, aplicativos de terceiros certificados e aplicativos personalizados criados por sua própria organização.

## <a name="use-microsoft-provided-apps"></a>Usar aplicativos fornecidos pela Microsoft

O Teams vem com um conjunto de aplicativos integrados, incluindo listas, Tarefas, Elogiar, Aprovações e muito mais. Recomendamos que você inclua os aplicativos do Microsoft Teams - como o Planner - na implementação inicial do Microsoft Teams. Adicione outros aplicativos à medida que você impulsiona a adoção do Teams. Algumas funcionalidades padrão, como fluxo de atividades, chat, calendário e chamadas, estão disponíveis por padrão e também fixadas para facilitar o acesso para usuários finais.

## <a name="use-third-party-apps"></a>Usar aplicativos de terceiros

Além dos aplicativos fornecidos pela Microsoft, você pode usar aplicativos de terceiros validados pela Microsoft. A Microsoft trabalha com Microsoft 365 desenvolvedores para fornecer as informações necessárias para agilizar as decisões sobre o uso de aplicativos do Teams. Para obter mais informações, consulte [Segurança e Conformidade de aplicativos do Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps).

## <a name="use-open-source-sample-apps-provided-by-microsoft"></a>Usar aplicativos de amostra de código aberto fornecidos pela Microsoft

Você também pode usar [modelos do Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json), aplicativos prontos para produção para o Microsoft Teams que são direcionados à comunidade, de código aberto e disponíveis no GitHub.

## <a name="create-custom-apps"></a>Criar aplicativos personalizados

Você pode criar rapidamente soluções personalizadas de baixo código usando a integração do Teams com o [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions). Você também pode criar seu próprio aplicativo personalizado para atender às suas necessidades de negócios. Para obter mais informações, confira [Construir aplicativos para o Microsoft Teams](/microsoftteams/platform/overview).  

## <a name="apps-deployment-decisions"></a>Decisões de implantação de aplicativos

O Teams fornece uma grande experiência de colaboração imediata para sua organização, e a maioria das organizações descobrem que as configurações padrão funcionam para eles. Este artigo o ajuda a decidir se quer alterar alguma das configurações padrão com base no perfil da sua organização e nos requisitos comerciais, e depois o acompanha em cada alteração. Dividimos as configurações em dois grupos, começando com o conjunto central de [alterações que você está mais propenso a fazer](#core-deployment-decisions). O segundo grupo inclui as [configurações adicionais](#additional-deployment-decisions) que você pode querer configura com base nas necessidades da sua organização.

## <a name="core-deployment-decisions"></a>Decisões principais de implantação

Estas são as configurações de aplicativos que a maioria das organizações deseja alterar (se as configurações padrão do Teams não atenderem suas necessidades).

### <a name="app-availability-settings"></a>Configurações de disponibilidade do aplicativo

O Teams fornece muitos aplicativos publicados pela Microsoft e por terceiros para envolver os usuários, dar suporte à produtividade e integrar os serviços de negócios comumente usados no Teams.
Obtenha aplicativos na Teams Store. Por padrão, todos os aplicativos, incluindo aplicativos personalizados enviados por meio do[processo de aprovação do Teams Store](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), são ativados para todos os usuários.  Por exemplo, os usuários podem usar o aplicativo do Planner para criar e gerenciar tarefas de equipe no Teams.

Por padrão, todos os aplicativos fornecidos por terceiros, aprovados pela Microsoft e personalizados estão disponíveis, e é possível ativar ou desativar aplicativos individualmente. Existem configurações de toda a organização que permitem ativar ou desativar aplicativos terceirizados e/ou personalizados para toda a sua organização.

| Pergunte-se | Ação |
|--------------|--------|
|Vai alterar as configurações padrão dos aplicativos Teams? | Para mais informações sobre políticas e configurações que podem ser usadas no gerenciamento de aplicativos da sua organização, confira as[Configurações de Administrador para aplicativos no Microsoft Teams](admin-settings.md).|

### <a name="app-permissions-and-other-considerations"></a>Permissões de aplicativos e outras considerações

Os aplicativos são aceitos pelos usuários e gerenciados pelo administrador ou pelo profissional de TI através das políticas. No entanto, as permissões do aplicativo e o perfil de risco são definidos no próprio aplicativo.

| Pergunte-se | Ação |
|--------------|--------|
|<br>A quais aplicativos quero permitir o acesso? A quais aplicativos não quero permitir o acesso?  | <ul><li>Confira [Permissões e considerações dos aplicativos Microsoft Teams](app-permissions.md) para ver uma lista de tarefas que deverão ser consideradas ao permitir acesso a um aplicativo, bot, guia ou conector.</li><li>Consulte [Gerenciar seus aplicativos no centro administrativo do Microsoft Teams](manage-apps.md) para obter informações sobre como disponibilizar um aplicativo aos usuários em sua organização.</li></ul>|

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
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Você pode alterar essas configurações, com base nas necessidades e na configuração da sua organização.

### <a name="activity-reports"></a>Relatórios de atividades

Você pode usar relatórios de atividade para ver como os usuários em sua organização estão usando o Teams. Por exemplo, se alguns usuários ainda não estiverem usando o Teams, é provável que não saibam por onde começar ou não entendam como podem usá-lo para se tornarem mais produtivos e colaborativos. Sua organização pode usar os relatórios de atividades para decidir onde priorizar os esforços de treinamento e comunicação. Para exibir relatórios de atividades, você deve ser um administrador global no Microsoft 365 e Office 365, administrador de serviço do Teams ou administrador do Skype for Business.

| Pergunte a si mesmo | Ação |
|--------------|--------|
| <br>Quem precisa ver os relatórios de atividade e eles têm a função correta para visualizá-los? |<ul><li>Se não quiser atribuir uma função de administrador a um usuário, você poderá [atribuir a função de leitor de relatórios](teams-activity-reports.md#reports-reader-role).</li><li>Confira [Funções e permissões](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [Exibir e atribuir funções](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para informar-se sobre como atribuir funções de administrador no Azure Active Directory.</li></ul> |

### <a name="app-templates"></a>Modelos de aplicativos

Os modelos de aplicativo são aplicativos prontos para produção para a Microsoft que são orientados pela comunidade, de software livre e disponíveis no GitHub. Cada aplicativo contém instruções detalhadas para implantá-lo e instalá-lo para sua organização e é um aplicativo pronto para uso que você pode instalar e começar a usar imediatamente.

O código-fonte completo também está disponível, para que você possa explorá-lo em detalhes ou bifurcar o código e alterá-lo para atender às suas necessidades específicas.

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Deseja instalar algum modelo de aplicativo do Teams, como o Icebreaker? |Para saber mais, leia[Modelos de aplicativos para o Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json).|
