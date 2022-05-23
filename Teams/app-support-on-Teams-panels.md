---
title: Microsoft Teams de aplicativos/lob (linha de negócios) em Teams painéis
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Descreve o suporte para Teams aplicativos/aplicativos LOB.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2bf4066675755e0f93844644a6a59404af678a38
ms.sourcegitcommit: d425748a50964ebc78e5d38fce564a444a449f43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65635409"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams de aplicativos/lob (linha de negócios) em Teams painéis

Teams painéis adicionam suporte para Teams [aplicativos/aplicativos de linha de negócios (LOB](/microsoftteams/platform/overview)). Isso permitirá que as empresas adicionem experiências adicionais nos painéis para atender às necessidades da sua organização. Esta versão dá suporte a conteúdo estático da Web.

> [!IMPORTANT]
> Esse recurso só está disponível depois de atualizar seus Teams dispositivos de painéis. Você precisa ter o aplicativo Teams versão 1449/1.0.97.2021070601 ou mais recente para ter suporte a aplicativos em Teams painéis.

## <a name="teams-app-experience-on-teams-panels"></a>Teams experiência do aplicativo em Teams painéis

![Captura de tela do Teams de administração mostrando qual seção permitirá que os usuários naveguem até aplicativos.](media/tac1update.png) 

*A Teams tela inicial dos painéis inclui opções de navegação do aplicativo, descritas na captura de tela em vermelho. Observe que esses são ícones de exemplo e podem não estar disponíveis para uso.*

![Captura de tela da tela do aplicativo em que os aplicativos podem ser adicionados.](media/appscreen.png)

*Quando um usuário final tocar em um dos ícones do aplicativo, ele verá a tela Teams aplicativo exibida na captura de tela anterior. O retângulo cinza na captura de tela é onde os aplicativos são exibidos no painel do Teams. A barra de aplicativos é fixa e faz parte do Teams aplicativo de painéis.*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurar e gerenciar aplicativos Teams painéis no Teams de administração 

Microsoft Teams aplicativos trazem informações importantes, ferramentas comuns e processos confiáveis para onde as pessoas se reúnem, aprendem e trabalham. Teams aplicativos funcionam [por meio de funcionalidades integradas](/microsoftteams/platform/concepts/capabilities-overview). Agora, como administrador de TI, você tem a opção de quais aplicativos incluir no dispositivo de painéis Teams sua organização e personalizar permissões por meio do centro de administração Teams[.](https://admin.teams.microsoft.com/)

Agora você pode usar os Teams em Teams e personalizar a experiência do usuário com base nas necessidades da sua organização. Você pode decidir qual aplicativo Web seus usuários podem acessar e usar e priorizar as exibições do aplicativo. Algumas opções, como os recursos de bot e mensagens, não têm suporte no momento. Saiba mais sobre [os Teams aplicativos](/microsoftteams/platform/overview) [e como gerenciar seus dispositivos Microsoft Teams](/microsoftteams/devices/device-management).

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Gerenciar aplicativos Teams painéis no Teams de administração

**Observação**: você deve ser um administrador global ou um Teams de serviço para acessar o [Teams de administração](https://admin.teams.microsoft.com/).

Os usuários finais podem exibir, mas não instalar aplicativos Teams painéis. Como administrador, você pode exibir e gerenciar todos os Teams para sua organização por meio do Teams de administração. Saiba mais sobre como você pode [gerenciar seus aplicativos no Microsoft Teams de](/microsoftteams/manage-apps) administração por meio da página **Gerenciar aplicativos**. A **página Gerenciar aplicativos** no Teams de administração também é onde você pode carregar [aplicativos personalizados](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store).

Depois de configurar aplicativos, você pode [](/microsoftteams/teams-app-permission-policies) usar políticas de permissão [](/microsoftteams/teams-app-setup-policies) de aplicativo e políticas de configuração de aplicativo para configurar a experiência do aplicativo para contas de sala específicas em sua organização.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Fixar aplicativos em Teams com políticas de configuração de aplicativo

Como Teams oferece a capacidade de exibir uma ampla variedade de aplicativos, os administradores podem decidir quais aplicativos são mais essenciais para a organização e fixá-lo apenas na tela inicial dos painéis  do Teams para acesso rápido. Se houver mais de cinco aplicativos fixados ou aplicativos desafixados, eles aparecerão na **tela** Mais. A Microsoft recomenda criar uma política de configuração de aplicativo personalizada especificamente para Teams painéis.

![Captura de tela da interface do usuário da página de políticas de configuração do aplicativo.](media/appsetup1.png) 

Para gerenciar aplicativos **fixados** \>  \>  \> exibidos nos painéis do Teams, entre no centro de administração do Teams para sua organização e navegue até políticas de Instalação de aplicativos do Teams Selecionar ou criar uma nova política de aplicativos fixados **.**

![Captura de tela da seção de aplicativos fixados na interface do usuário.](media/appsetup2.png) 

*Os aplicativos incluídos nesta imagem são apenas exemplos e podem não estar disponíveis para uso.*

A Microsoft recomenda que você **desative Upload** aplicativos personalizados  e a fixação do usuário para obter a melhor Teams de aplicativos em Teams painéis.

Para obter mais informações sobre como fixar aplicativos, consulte [Gerenciar políticas de configuração de aplicativo](/microsoftteams/teams-app-setup-policies).

## <a name="manage-apps-display-order-in-teams-panels"></a>Gerenciar a ordem de exibição de aplicativos Teams painéis 

![Captura de tela da seção aplicativos na interface do usuário.](media/appsetup3.png)

*Os aplicativos incluídos nesta imagem são apenas exemplos e podem não estar disponíveis para uso.*

Para gerenciar a ordem na qual os aplicativos são exibidos nos painéis do Teams, entre no centro de administração do Teams para sua organização e navegue até políticas de Instalação de aplicativos do Teams Selecione os aplicativos **fixados** \>  \>  \> por política **:** Mover para cima **/para baixo**.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Atribuindo políticas de configuração a uma conta de recurso de sala

Depois de criar a política de configuração, o administrador precisará atribuir essa política à conta de recurso da sala que será conectada aos painéis Teams ambiente. Para obter mais informações, consulte [Atribuir políticas a usuários e grupos](/microsoftteams/assign-policies-users-and-groups).

## <a name="faq"></a>Perguntas frequentes

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Quanto tempo leva para que os Teams para obter as políticas de configuração de aplicativo novas ou atualizadas?

Depois de editar ou atribuir novas políticas no Teams de administração, pode levar até 24 horas para que as alterações entre em vigor. Os administradores podem tentar sair/entrar no painel, tocar no ícone Configurações e voltar para **a** tela Inicial para tentar atualizar as políticas.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Qual é a ordenação dos aplicativos na tela "Mais"?

Na página **Mais** aplicativos, os aplicativos fixados aparecerão primeiro. Em seguida, todos os outros aplicativos instalados aparecerão em ordem alfabética.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Por que os aplicativos de bot não estão aparecendo Teams painéis?

Somente o conteúdo da Web de guias estáticas tem suporte no momento.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Por que os Teams nativos, como Calendário e Tarefas, não são exibidos Teams painéis?

Aplicativos Teams nativos, como Calendário e Tarefas, não são mostrados Teams painéis.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>No centro Teams de administração, na seção de políticas de configuração, qual é a diferença entre aplicativos instalados e aplicativos fixados?

Para Teams, a Microsoft recomenda usar aplicativos fixados, para que o administrador possa selecionar o aplicativo desejado e reorganizar sua ordenação.

**Nota:** Alguns aplicativos não dão suporte à fixação de aplicativos. Entre em contato com o desenvolvedor do aplicativo para habilitar a funcionalidade de fixação de aplicativos.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Por que outros aplicativos estão aparecendo na tela "Mais", mesmo que eles não fazem parte dos aplicativos instalados ou fixados na seção Teams política de configuração do aplicativo?

Se os aplicativos foram instalados anteriormente por meio de outras políticas de aplicativo ou manualmente nos clientes da área de trabalho/web do Teams para a conta de recurso de sala usada em painéis do Teams, o administrador pode precisar entrar na conta de recurso da sala no Teams e desinstalar manualmente os aplicativos clicando com o botão direito do mouse no aplicativo e selecionando Desinstalar.

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Por que não consigo encontrar um aplicativo no painel "Adicionar aplicativos fixados"?

Nem todos os aplicativos podem ser fixados Teams por meio de uma política de configuração de aplicativo. Alguns aplicativos podem não dar suporte a essa funcionalidade. Para localizar aplicativos que podem ser fixados, pesquise o aplicativo no **painel Adicionar aplicativos fixados** . Para obter mais informações, consulte as [perguntas frequentes sobre como trabalhar com políticas de configuração de aplicativo](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane).

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>Por que estou vendo um pop-up "Fixação de usuário" no painel de políticas de configuração depois que eu desativo a "Fixação do usuário?"

![Captura de tela da seção de política de configuração na interface do usuário com um pop-up confirmando que a fixação do usuário está ativa.](media/appsetup4.png)

*Os aplicativos incluídos nesta imagem são apenas exemplos e podem não estar disponíveis para uso.* 

Esse comportamento é esperado para um dispositivo em um espaço compartilhado e ajuda a evitar a fixação não intencional do aplicativo.
