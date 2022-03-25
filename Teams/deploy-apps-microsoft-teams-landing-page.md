---
title: Aplicativos, bots e conectores no Microsoft Teams
ms.reviewer: ''
description: Saiba mais sobre aplicativos, bots e conectores, e como decidir quais implantar no Microsoft Teams com base no perfil e requisitos de negócios da sua organização.
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
ms.openlocfilehash: be7ee83b510096d8d6ffc0c4a0a5984917ad55c5
ms.sourcegitcommit: 42c355d3f4bbe52c063b8f2119baefc0b88f9563
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403972"
---
# <a name="about-apps-in-microsoft-teams"></a>Sobre aplicativos no Microsoft Teams

Os aplicativos permitem que você localize conteúdo de seus serviços favoritos e compartilhe-o no Teams. Eles ajudam você a fazer coisas como localizar serviços na parte superior de um canal, bater-papo com bots ou compartilhar e atribuir tarefas. Para saber mais, leia [Visão geral de aplicativos no Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

Você pode adicionar aplicativos à implantação do Teams usando os aplicativos fornecidos com o Microsoft Teams, usando aplicativos e modelos certificados de terceiros e criando seus próprios aplicativos personalizados.

## <a name="use-microsoft-provided-apps"></a>Usar aplicativos fornecidos pela Microsoft

O Teams vem com um conjunto de aplicativos integrados, incluindo listas, Tarefas, Elogiar, Aprovações e muito mais. Recomendamos que você inclua os aplicativos do Microsoft Teams - como o Planner - na implementação inicial do Microsoft Teams. Adicione outros aplicativos, bots e conectores ao direcionar a adoção do Teams.

## <a name="use-third-party-apps"></a>Usar aplicativos de terceiros

Além dos aplicativos fornecidos pela Microsoft, você pode usar aplicativos de terceiros certificados pela Microsoft. A Microsoft trabalha com parceiros desenvolvedores do Microsoft 365 para fornecer as informações necessárias para agilizar as decisões sobre o uso de aplicativos e suplementos do Teams. Para obter mais informações, consulte [Segurança e Conformidade de aplicativos do Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps).

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

Os aplicativos são aceitos pelos usuários e gerenciados pelo administrador ou pelo profissional de TI através das políticas. No entanto, na maioria das vezes, as permissões e o perfil de risco de um aplicativo são definidos no próprio aplicativo.

Os aplicativos são aceitos pelos usuários e gerenciados pelo administrador ou pelo profissional de TI através das políticas. No entanto, as permissões do aplicativo e o perfil de risco são definidos no próprio aplicativo.

| Pergunte-se | Ação |
|--------------|--------|
|<br>A quais aplicativos quero permitir o acesso? A quais aplicativos não quero permitir o acesso?  | <ul><li>Confira [Permissões e considerações dos aplicativos Microsoft Teams](app-permissions.md) para ver uma lista de tarefas que deverão ser consideradas ao permitir acesso a um aplicativo, bot, guia ou conector.</li><li>Consulte [Gerenciar seus aplicativos no centro administrativo do Microsoft Teams](manage-apps.md) para obter informações sobre como disponibilizar um aplicativo aos usuários em sua organização.</li></ul>|

### <a name="bots-for-private-chats-and-channels"></a>Bots para chats privados e canais

Os bots são programas automatizados que respondem a consultas ou fornecem atualizações e notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados. Os bots permitem que os usuários interajam com serviços de nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de um chat no Teams. O Teams oferece suporte a bots em chats privados e canais. Os administradores podem controlar se o uso de bots é permitido em uma organização do Microsoft 365 ou do Office 365.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Desejo permitir bots personalizados na minha organização?|Para saber mais sobre a adição de bots, confira [Adicionar bots para canais e chats privados no Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). Para obter mais informações sobre a ativação ou desativação de bots personalizados, confira [Configurações de administrador para aplicativos no Microsoft Teams](admin-settings.md).|

### <a name="built-in-and-custom-tabs"></a>Guias internas e personalizadas

Os proprietários e membros da equipe podem incluir guias em um canal, chat privado e chat em grupo para ajudar a integrar seus serviços de nuvem. Adicione guias para ajudar os usuários a acessar e gerenciar os dados que eles mais usam ou que mais precisam. Nos canais, as guias Conversas e Arquivos são criadas por padrão. Em cada chat privado, as guias Conversas, Arquivos, Organização e Atividade são criadas por padrão. Além dessas guias internas, você pode criar e adicionar guias personalizadas. Para saber como ativar ou desativar os aplicativos Teams de sua organização, leia [Configurações de administrador para aplicativos no Teams](admin-settings.md).

| Pergunte-se | Ação |
|--------------|--------|
|Desejo permitir guias personalizadas na minha organização?|Para obter mais informações, confira [Configurar as guias internas e personalizadas no Teams](built-in-custom-tabs.md).|

### <a name="custom-connectors"></a>Conectores personalizados

Os conectores mantêm sua equipe atualizada com conteúdo e atualizações de serviços que você usa frequentemente diretamente em um canal. Com conectores, os usuários do Teams podem receber atualizações de serviços populares, como Twitter, Trello, Wunderlist, GitHub e Azure DevOps Services em chats do Teams.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Quero que os usuários criem conectores personalizados?|Para saber mais, confira [Usar conectores personalizados no Teams](office-365-custom-connectors.md).|

## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Convém alterar essas configurações, com base nas necessidades da organização e da configuração.

### <a name="activity-reports"></a>Relatórios de atividades

Você pode usar relatórios de atividade para ver como os usuários em sua organização estão usando o Teams. Por exemplo, se alguns usuários ainda não estiverem usando o Teams, é provável que não saibam por onde começar ou não entendam como podem usá-lo para se tornarem mais produtivos e colaborativos. Sua organização pode usar os relatórios de atividades para decidir onde priorizar os esforços de treinamento e comunicação. Para exibir relatórios de atividades, você deve ser um administrador global no Microsoft 365 e Office 365, administrador de serviço do Teams ou administrador do Skype for Business.

| Pergunte a si mesmo | Ação |
|--------------|--------|
| <br>Quem precisa ver os relatórios de atividade e eles têm a função correta para visualizá-los? |<ul><li>Se não quiser atribuir uma função de administrador a um usuário, você poderá [atribuir a função de leitor de relatórios](teams-activity-reports.md#reports-reader-role).</li><li>Confira [Funções e permissões](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [Exibir e atribuir funções](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para informar-se sobre como atribuir funções de administrador no Azure Active Directory.</li></ul> |

### <a name="app-templates"></a>Modelos de aplicativos

Os modelos de aplicativos são aplicativos prontos para produção para o Microsoft Teams orientadas pela comunidade, software livre e disponíveis no GitHub. Cada um contém instruções detalhadas para implantação e instalação do aplicativo para a sua organização, fornecendo um aplicativo pronto para uso que você pode instalar e começar a usar imediatamente.

O código-fonte completo também está disponível, para que você possa explorá-lo em detalhes ou bifurcar o código e alterá-lo para atender às suas necessidades específicas.

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Deseja instalar algum modelo de aplicativo do Teams, como o Icebreaker? |Para saber mais, leia[Modelos de aplicativos para o Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json).|
