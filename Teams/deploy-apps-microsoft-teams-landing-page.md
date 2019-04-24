---
title: Aplicativos, bots e conectores no Microsoft Teams
ms.reviewer: ''
description: Use esses recursos de implantação para ajudá-lo a implantar os aplicativos na Microsoft.
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
ms.openlocfilehash: e182732647b79f5a3a2ae48940ce3423b157c61f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32218034"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a>Aplicativos, bots e conectores no Microsoft Teams

Os aplicativos permitem encontrar conteúdo em seus serviços favoritos e partilhá-lo diretamente no Teams. Eles ajudam você a fazer coisas como localizar serviços na parte superior de um canal, bater-papo com bots ou compartilhar e atribuir tarefas. Para saber mais, leia [Visão geral de aplicativos no Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

É recomendável incluir os aplicativos em destaque, como o Planner, na implementação inicial do Teams. Adicione outros aplicativos, bots e conectores ao direcionar a adoção do Teams.

## <a name="apps-deployment-decisions"></a>Decisões de implantação de aplicativos

O Teams oferece uma excelente experiência de colaboração pronta para uso para sua organização e a maioria das organizações acha que as configurações padrão atendem suas necessidades. Este artigo ajuda você a decidir se deseja alterar as configurações padrão, com base no perfil da organização e requisitos de negócios e, em seguida, orienta você em cada alteração. Dividimos as configurações em dois grupos, começando com o conjunto principal de [alterações que você provavelmente realizará](#core-deployment-decisions). O segundo grupo inclui [configurações adicionais](#additional-deployment-decisions) que poderão ser configuradas com base nas necessidades de sua organização.

## <a name="core-deployment-decisions"></a>Decisões principais de implantação

Estas são as configurações de aplicativos que a maioria das organizações deseja alterar (se as configurações padrão do Teams não atenderem suas necessidades).

### <a name="app-availability-settings"></a>Configurações de disponibilidade do aplicativo 

O Teams oferece vários aplicativos publicados pela Microsoft e por terceiros para envolver usuários, dar apoio à produtividade e integrar serviços empresariais normalmente usados no Teams. Obtenha aplicativos na Teams Store. Por padrão, todos os aplicativos, incluindo aplicativos personalizados enviados por meio do[processo de aprovação do Teams Store](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), são ativados para todos os usuários.  Por exemplo, os usuários podem usar o aplicativo do Planner para criar e gerenciar tarefas de equipe no Teams.

Por padrão, todos os aplicativos personalizados e fornecidos pela Microsoft estão disponíveis, e é possível ativar ou desativar aplicativos individualmente. Há uma configuração de toda a organização que permite ativar ou desativar aplicativos personalizados para toda a sua organização.

| Pergunte-se | Ação |
|--------------|--------|
|Vai alterar as configurações padrão dos aplicativos Teams? | Para mais informações sobre políticas e configurações que podem ser usadas no gerenciamento de aplicativos da sua organização, confira as[Configurações de Administrador para aplicativos no Microsoft Teams](admin-settings.md).|
|||

### <a name="app-permissions-and-other-considerations"></a>Permissões de aplicativos e outras considerações

Os aplicativos são aceitos pelos usuários e gerenciados pelo administrador ou pelo profissional de TI através das políticas. No entanto, na maioria das vezes, as permissões e o perfil de risco de um aplicativo são definidos no próprio aplicativo. 

| Pergunte-se | Ação |
|--------------|--------|
|<br>A quais aplicativos quero permitir o acesso? A quais aplicativos não quero permitir o acesso?  | <ul><li>Confira [Permissões e considerações dos aplicativos Microsoft Teams](app-permissions.md) para ver uma lista de tarefas que deverão ser consideradas ao permitir acesso a um aplicativo, bot, guia ou conector.</li><li>Confira [Publicar aplicativos no catálogo de aplicativos do locatário do Teams](tenant-apps-catalog-teams.md) para obter informações sobre como disponibilizar um aplicativo para os usuários de sua organização.</li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a>Bots para chats privados e canais

Os bots são programas automatizados que respondem a consultas ou fornecem atualizações e notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados. Os bots permitem que os usuários interajam com serviços de nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de um chat no Teams. O Teams oferece suporte a bots em chats privados e canais. Os administradores podem controlar se o uso de bots é permitido em um locatário do Office 365.

| Pergunte-se | Ação |
|--------------|--------|
|Desejo permitir bots personalizados em meu locatário do Office 365?|Para saber mais sobre a adição de bots, confira [Adicionar bots para canais e chats privados no Microsoft Teams](add-bots.md). Para obter mais informações sobre a ativação ou desativação de bots personalizados, confira [Configurações de administrador para aplicativos no Microsoft Teams](admin-settings.md).|
|||

### <a name="built-in-and-custom-tabs"></a>Guias internas e personalizadas

Os proprietários e membros da equipe podem incluir guias em um canal, chat privado e chat em grupo para ajudar a integrar seus serviços de nuvem. Adicione guias para ajudar os usuários a acessar e gerenciar os dados que eles mais usam ou que mais precisam. Nos canais, as guias Conversas e Arquivos são criadas por padrão. Em cada chat privado, as guias Conversas, Arquivos, Organização e Atividade são criadas por padrão. Além dessas guias internas, você pode criar e adicionar guias personalizadas. Para saber como ativar ou desativar os aplicativos Teams de sua organização, leia [Configurações de administrador para aplicativos no Teams](admin-settings.md).

| Pergunte-se | Ação |
|--------------|--------|
|Desejo permitir guias personalizadas em meu locatário do Office 365?|Para obter mais informações, confira [Configurar as guias internas e personalizadas no Teams](built-in-custom-tabs.md).|
|||

### <a name="office-365-and-custom-connectors"></a>Office 365 e conectores personalizados

Os conectores mantêm sua equipe atualizada com conteúdo e atualizações de serviços que você usa frequentemente diretamente em um canal. Com conectores, os usuários do Teams podem receber atualizações de serviços populares, como Twitter, Trello, Wunderlist, GitHub e Azure DevOps Services em chats do Teams.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Quero que os usuários criem conectores personalizados?|Para saber mais, confira [Usar o Office 365 e conectores personalizados no Teams](office-365-custom-connectors.md).|
|||

## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Convém alterar essas configurações, com base nas necessidades da organização e da configuração.

### <a name="activity-reports"></a>Relatórios de atividades

Você pode usar relatórios de atividade para ver como os usuários em sua organização estão usando o Teams. Por exemplo, se alguns usuários ainda não estiverem usando o Teams, é provável que não saibam por onde começar ou não entendam como podem usá-lo para se tornarem mais produtivos e colaborativos. Sua organização pode usar os relatórios de atividades para decidir onde priorizar os esforços de treinamento e comunicação. Para exibir relatórios de atividades, você deve ser um administrador global no Office 365, administrador de serviço do Teams ou administrador do Skype for Business.

| Pergunte-se | Ação |
|--------------|--------|
| <br>Quem precisa ver os relatórios de atividade e eles têm a função correta para visualizá-los? |<ul><li>Se não quiser atribuir uma função de administrador a um usuário, você poderá [atribuir a função de leitor de relatórios](teams-activity-reports.md#reports-reader-role).</li><li>Confira [Funções e permissões](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [Exibir e atribuir funções](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para informar-se sobre como atribuir funções de administrador no Azure Active Directory.</li></ul> |
|||


## <a name="next-steps"></a>Próximas etapas
- [Direcione a adoção](adopt-microsoft-teams-landing-page.md) de aplicativos em destaque, como o Planner.
- [Implementar reuniões e conferências](deploy-meetings-microsoft-teams-landing-page.md)
- [Implementar o Cloud Voice](cloud-voice-landing-page.md)


