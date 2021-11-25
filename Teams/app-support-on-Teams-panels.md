---
title: Microsoft Teams aplicativos/linha de negócios (LOB) suporte a aplicativos Teams painéis
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
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
ms.openlocfilehash: 8852ef3d212d2a284f4af72662c771d4c13b13af
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205631"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams aplicativos/linha de negócios (LOB) suporte a aplicativos Teams painéis

Teams painéis adicionam suporte Teams [aplicativos/aplicativos de linha de negócios (LOB).](/microsoftteams/platform/overview) Isso permitirá que as empresas adicionem experiências adicionais nos painéis para atender às necessidades da sua organização. Esta versão dá suporte ao conteúdo estático da Web.

> [!IMPORTANT]
> Esse recurso só estará disponível depois de atualizar seus dispositivos Teams painéis. Você precisa ter o aplicativo Teams versão 1449/1.0.97.2021070601 ou mais recente para ter suporte a aplicativos em Teams painéis.

## <a name="teams-app-experience-on-teams-panels"></a>Teams experiência do aplicativo em Teams painéis

![Captura de tela do Teams de administração mostrando qual seção permitirá que os usuários naveguem até aplicativos.](media/tac1update.png) 

*A Teams tela inicial dos painéis inclui opções de navegação do aplicativo, descritas na captura de tela em vermelho. Observe que esses são ícones de exemplo e podem não estar disponíveis para uso.*

![Captura de tela da tela do aplicativo onde os aplicativos podem ser adicionados.](media/appscreen.png)

*Quando um usuário final toca em um dos ícones do aplicativo, ele verá a Teams de aplicativos exibida na captura de tela anterior. O retângulo cinza na captura de tela é onde os aplicativos são exibidos Teams painel. A barra de aplicativos é fixa e parte do aplicativo Teams painéis.*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurar e gerenciar Teams de painéis no Teams de administração 

Microsoft Teams aplicativos trazem informações importantes, ferramentas comuns e processos confiáveis para onde as pessoas coletam, aprendem e trabalham. Teams aplicativos funcionam [por meio de recursos integrados.](/microsoftteams/platform/concepts/capabilities-overview) Agora, como administrador de TI, você tem a opção de quais aplicativos incluir no dispositivo de painéis Teams sua organização e personalizar permissões por meio do centro de administração [Teams.](https://admin.teams.microsoft.com/)

Agora você pode usar os Teams aplicativos Teams painéis e personalizar a experiência do usuário com base nas necessidades da sua organização. Você pode decidir qual aplicativo Web seus usuários podem acessar e usar e priorizar os exibições do aplicativo. Algumas opções, como o bot e os recursos de mensagens, não são suportadas no momento. Saiba mais sobre [os aplicativos Teams e](/microsoftteams/platform/overview) como gerenciar seus [dispositivos em Microsoft Teams](/microsoftteams/devices/device-management).

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Gerenciar aplicativos Teams painéis no Teams de administração

**Observação**: você deve ser um administrador global ou um administrador de serviço Teams para acessar o [Teams de administração.](https://admin.teams.microsoft.com/)

Os usuários finais podem exibir, mas não instalar aplicativos Teams painéis. Como administrador, você pode exibir e gerenciar todos os aplicativos Teams para sua organização por meio do Teams de administração. Saiba mais sobre como gerenciar [seus aplicativos](/microsoftteams/manage-apps) no centro de administração Microsoft Teams por meio da página **Gerenciar aplicativos.** A **página Gerenciar aplicativos** no centro de administração Teams também é onde você pode carregar [aplicativos personalizados.](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store)

Depois de configurar aplicativos, você [](/microsoftteams/teams-app-setup-policies) pode [usar](/microsoftteams/teams-app-permission-policies) políticas de permissão de aplicativo e políticas de configuração de aplicativos para configurar a experiência do aplicativo para contas de sala específicas em sua organização.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Fixar aplicativos em Teams painéis com políticas de configuração de aplicativos

Como Teams oferece a capacidade de exibir uma ampla variedade de aplicativos, os administradores podem decidir quais aplicativos são  mais essenciais para a organização e fixá-los apenas para a tela inicial de painéis Teams para acesso rápido. Se houver mais de cinco aplicativos fixados ou aplicativos não fixados, eles aparecerão na **tela Mais.** A Microsoft recomenda criar uma política de configuração de aplicativo personalizada especificamente para Teams painéis.

![Captura de tela da interface do usuário da página políticas de configuração do aplicativo.](media/appsetup1.png) 

Para gerenciar aplicativos fixados exibidos nos painéis Teams, entre no centro de administração do Teams para sua organização e navegue até **Teams** políticas de Instalação de aplicativos Selecione ou Crie uma nova política Fixado aplicativos \>  \>  \> .

![Captura de tela da seção aplicativos fixados na interface do usuário.](media/appsetup2.png) 

*Os aplicativos incluídos nesta imagem são apenas exemplos e podem não estar disponíveis para uso.*

A Microsoft recomenda  que você Upload aplicativos personalizados e o **pinning** do usuário para a melhor Teams de aplicativos em Teams painéis.

Para obter mais informações sobre como fixar aplicativos, consulte [Manage app setup policies](/microsoftteams/teams-app-setup-policies).

## <a name="manage-apps-display-order-in-teams-panels"></a>Gerenciar a ordem de exibição de aplicativos Teams painéis 

![Captura de tela da seção aplicativos dentro da interface do usuário.](media/appsetup3.png)

*Os aplicativos incluídos nesta imagem são apenas exemplos e podem não estar disponíveis para uso.*

Para gerenciar a ordem na qual os aplicativos são exibidos nos painéis Teams, entre no centro de administração do Teams para sua organização e navegue até **Teams** políticas de Instalação de aplicativos Selecione os aplicativos fixados em \>  \>  \> **política:** **Mover para cima/para baixo**.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Atribuir políticas de instalação a uma conta de recurso de sala

Depois de criar a política de instalação, o administrador precisará atribuir essa política à conta de recurso de sala que será assinada nos painéis Teams de sala. Para obter mais informações, consulte [Atribuir políticas a usuários e grupos.](/microsoftteams/assign-policies-users-and-groups)

## <a name="faq"></a>Perguntas frequentes

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Quanto tempo leva para os painéis Teams obter as políticas de configuração de aplicativos novas ou atualizadas?

Depois de editar ou atribuir novas políticas no centro de administração Teams, pode levar até 24 horas para que as alterações entre em vigor. Os administradores podem tentar entrar/entrar no painel, tocar no ícone Configurações e voltar para **a** **tela** inicial para tentar atualizar as políticas.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Qual é a ordem dos aplicativos na tela "Mais"?

Na página **Mais** aplicativos, os aplicativos fixados aparecerão primeiro. Em seguida, quaisquer outros aplicativos instalados aparecerão em ordem alfabética.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Por que os aplicativos de bot não estão aparecendo Teams painéis?

Somente o conteúdo da Web de guias estáticas é suportado no momento.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Por que aplicativos Teams nativos, como Calendário e Tarefas, não aparecem em Teams painéis?

Aplicativos Teams nativos, como Calendário e Tarefas, não são mostrados Teams painéis.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>No centro Teams de administração, na seção políticas de instalação, qual é a diferença entre aplicativos instalados e aplicativos fixados?

Para Teams painéis, a Microsoft recomenda o uso de aplicativos fixados, para que o administrador possa selecionar o aplicativo desejado e reorganizar sua ordenação.

**Observação:** Alguns aplicativos não suportam o pinamento de aplicativos. Entre em contato com o desenvolvedor do aplicativo para habilitar a funcionalidade de pinamento de aplicativo.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Por que outros aplicativos aparecem na tela "Mais", mesmo que eles não fazem parte dos aplicativos instalados ou fixados na seção Teams de configuração de aplicativos?

Se os aplicativos foram instalados anteriormente por meio de outras políticas de aplicativo ou manualmente nos clientes da área de trabalho/web do Teams para a conta de recurso de sala usada em painéis Teams, o administrador pode precisar entrar na conta de recurso de sala no Teams e desinstalar manualmente os aplicativos clicando com o botão direito do mouse no aplicativo e selecionando **Desinstalar**.

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Por que não consigo encontrar um aplicativo no painel "Adicionar aplicativos fixados"?

Nem todos os aplicativos podem ser fixados Teams por meio de uma política de configuração de aplicativo. Alguns aplicativos podem não dar suporte a essa funcionalidade. Para encontrar aplicativos que podem ser fixados, pesquise o aplicativo no painel **Adicionar aplicativos** fixados. Para obter mais informações, consulte perguntas [frequentes em Trabalhando com políticas de configuração de aplicativos.](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>Por que estou vendo um pop-up "Pinning do usuário" no painel de políticas de configuração depois que eu desativar "Pinning do usuário?"

![Captura de tela da seção de política de instalação dentro da interface do usuário com um pop-up confirmando que o pining do usuário está ativo.](media/appsetup4.png)

*Os aplicativos incluídos nesta imagem são apenas exemplos e podem não estar disponíveis para uso.* 

Esse comportamento é esperado para um dispositivo em um espaço compartilhado e ajuda a evitar o pinamento de aplicativo não intencional.
