---
title: Suporte a aplicativos do Microsoft Teams/Linha de Negócios (LOB) em painéis do Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Descreve o suporte para aplicativos do Teams/aplicativos LOB.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c8d28a3f985a38e174030ddbe0e6d43e2153738
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656067"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Suporte a aplicativos do Microsoft Teams/Linha de Negócios (LOB) em painéis do Teams

Os painéis do Teams estão adicionando suporte para [aplicativos lob (aplicativos de linha de negócios) do Teams](/microsoftteams/platform/overview). Isso permitirá que as empresas adicionem experiências adicionais nos painéis para atender às necessidades da sua organização. Essa versão dá suporte a conteúdo estático da Web.

> [!IMPORTANT]
> Esse recurso só está disponível depois de atualizar seus dispositivos de painéis do Teams. Você precisa ter o aplicativo teams versão 1449/1.0.97.2021070601 ou mais recente para ter suporte de aplicativo nos painéis do Teams.

## <a name="teams-app-experience-on-teams-panels"></a>Experiência de aplicativo do Teams em painéis do Teams

![Captura de tela do centro de administração do Teams mostrando qual seção permitirá que os usuários naveguem até aplicativos.](media/tac1update.png)

*A tela inicial dos painéis do Teams inclui opções de navegação do aplicativo, descritas na captura de tela em vermelho. Observe que estes são ícones de exemplo e podem não estar disponíveis para uso.*

![Captura de tela da tela do aplicativo em que os aplicativos podem ser adicionados.](media/appscreen.png)

*Quando um usuário final tocar em um dos ícones do aplicativo, ele verá a tela do aplicativo teams exibida na captura de tela anterior. O retângulo cinza na captura de tela é onde os aplicativos são exibidos no painel do Teams. A barra de aplicativos é fixa e parte do aplicativo de painéis do Teams.*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurar e gerenciar aplicativos de painéis do Teams no centro de administração do Teams

Os aplicativos do Microsoft Teams trazem informações importantes, ferramentas comuns e processos confiáveis para onde as pessoas se reúnem, aprendem e trabalham. Os aplicativos do Teams funcionam [por meio de recursos integrados](/microsoftteams/platform/concepts/capabilities-overview). Agora, como administrador de TI, você tem a opção de quais aplicativos incluir no dispositivo de painéis do Teams da sua organização e personalizar permissões por meio do [centro de administração do Teams](https://admin.teams.microsoft.com/).

Agora você pode usar os aplicativos do Teams nos painéis do Teams e personalizar a experiência do usuário com base nas necessidades da sua organização. Você pode decidir qual aplicativo Web seus usuários podem acessar e usar e priorizar as exibições do aplicativo. Algumas opções, como o bot e os recursos de mensagens, não têm suporte no momento. Saiba mais sobre [os aplicativos do Teams](/microsoftteams/platform/overview) e [como gerenciar seus dispositivos no Microsoft Teams](/microsoftteams/devices/device-management).

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Gerenciar aplicativos em painéis do Teams no centro de administração do Teams

**Observação**: você deve ser um administrador global ou um administrador de serviço do Teams para acessar o [centro de administração do Teams](https://admin.teams.microsoft.com/).

Os usuários finais podem exibir, mas não instalar aplicativos em painéis do Teams. Como administrador, você pode exibir e gerenciar todos os aplicativos do Teams para sua organização por meio do centro de administração do Teams. Saiba mais sobre como [gerenciar seus aplicativos no centro de administração do Microsoft Teams](/microsoftteams/manage-apps) por meio da página **Gerenciar aplicativos** . A página **Gerenciar aplicativos** no centro de administração do Teams também é onde você pode carregar [aplicativos personalizados](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store).

Depois de configurar aplicativos, você pode usar [políticas de permissão de aplicativo](/microsoftteams/teams-app-permission-policies) e [políticas de configuração de aplicativo](/microsoftteams/teams-app-setup-policies) para configurar a experiência do aplicativo para contas de sala específicas em sua organização.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Fixar aplicativos em painéis do Teams com políticas de configuração de aplicativo

Como o Teams oferece a capacidade de exibir uma ampla gama de aplicativos, os administradores podem decidir quais aplicativos são mais essenciais para a organização e fixar apenas estes para os painéis do Teams Tela **inicial** para acesso rápido. Se houver mais de cinco aplicativos fixados ou aplicativos não apoiados, eles aparecerão na tela **Mais** . A Microsoft recomenda a criação de uma política personalizada na política de instalação do aplicativo especificamente para painéis do Teams.

![Captura de tela da interface do usuário da página de políticas de configuração do aplicativo.](media/appsetup1.png)

Para gerenciar aplicativos fixados exibidos nos painéis do Teams, entre no centro de administração do Teams para sua organização e navegue até as **políticas de instalação** de **aplicativos** \> do Teams **Selecione ou Crie uma nova política** \> **De aplicativos fixados**\>.

![Captura de tela da seção aplicativos fixados na interface do usuário.](media/appsetup2.png)

*Os aplicativos incluídos nesta imagem são apenas exemplos e podem não estar disponíveis para uso.*

A Microsoft recomenda que você desative **Carregar aplicativos personalizados** e **fixação de usuário** para a melhor experiência de aplicativo do Teams nos painéis do Teams.

Para saber mais sobre como fixar aplicativos, consulte [Gerenciar políticas de configuração de aplicativo](/microsoftteams/teams-app-setup-policies).

## <a name="manage-apps-display-order-in-teams-panels"></a>Gerenciar ordem de exibição de aplicativos nos painéis do Teams

![Captura de tela da seção aplicativos na interface do usuário.](media/appsetup3.png)

*Os aplicativos incluídos nesta imagem são apenas exemplos e podem não estar disponíveis para uso.*

Para gerenciar a ordem na qual os aplicativos são exibidos nos painéis do Teams, entre no centro de administração do Teams para sua organização e navegue até as **políticas de instalação** de **aplicativos** \> **do Teams Selecione os** **aplicativos fixados** \> em política\>: **mover-se para cima/para baixo**.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Atribuindo políticas de configuração a uma conta de recurso de sala

Depois de criar a política de instalação, o administrador precisará atribuir essa política à conta de recursos da sala que será assinada nos painéis do Teams. Para obter mais informações, consulte [Atribuir políticas a usuários e grupos](/microsoftteams/assign-policies-users-and-groups).

## <a name="faq"></a>Perguntas frequentes

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Quanto tempo leva para os painéis do Teams obterem as políticas de configuração de aplicativo novas ou atualizadas?

Depois de editar ou atribuir novas políticas no centro de administração do Teams, pode levar até 24 horas para que as alterações entrem em vigor. Os administradores podem tentar sair/entrar no painel, tocar no ícone **Configurações** e voltar para a tela **Inicial** para tentar atualizar as políticas.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Qual é a ordenação dos aplicativos na tela "Mais"?

Na página **Mais** aplicativos, os aplicativos fixados serão exibidos primeiro. Em seguida, qualquer outro aplicativo instalado aparecerá em ordem alfabética.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Por que os aplicativos bot não estão aparecendo nos painéis do Teams?

Somente o conteúdo da Web de guias estáticas tem suporte no momento.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Por que aplicativos nativos do Teams, como Calendário e Tarefas, não aparecem nos painéis do Teams?

Aplicativos nativos do Teams, como Calendário e Tarefas, não são mostrados nos painéis do Teams.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>No centro de administração do Teams, na seção políticas de configuração, qual é a diferença entre aplicativos instalados e aplicativos fixados?

Para painéis do Teams, a Microsoft recomenda o uso de aplicativos fixados, de modo que o administrador seja capaz de selecionar o aplicativo desejado e reorganizar sua ordenação.

**Nota:** Alguns aplicativos não dão suporte à fixação de aplicativos. Entre em contato com o desenvolvedor do aplicativo para habilitar a funcionalidade de fixação de aplicativo.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Por que outros aplicativos estão aparecendo na tela "Mais", mesmo que não façam parte dos aplicativos instalados ou fixados na seção política de configuração do aplicativo Teams?

Se os aplicativos foram instalados anteriormente por meio de outras políticas de aplicativo ou manualmente na área de trabalho/clientes Web do Teams para a conta de recursos de sala usada nos painéis do Teams, o administrador poderá precisar entrar na conta de recursos da sala no Teams e desinstalar manualmente os aplicativos clicando com o botão direito do mouse no aplicativo e selecionando **Desinstalar**.

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Por que não consigo encontrar um aplicativo no painel "Adicionar aplicativos fixados"?

Nem todos os aplicativos podem ser fixados no Teams por meio de uma política de configuração de aplicativo. Alguns aplicativos podem não suportar essa funcionalidade. Para localizar aplicativos que podem ser fixados, pesquise o aplicativo no painel **Adicionar aplicativos fixados**. Para obter mais informações, consulte [as perguntas frequentes em Trabalhar com políticas de configuração de aplicativo](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane).

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>Por que estou vendo um pop-up "Fixação de usuário" no painel de políticas de configuração depois de desativar "Fixação de usuário?"

![Captura de tela da seção de política de configuração dentro da interface do usuário com um pop-up confirmando que a fixação do usuário está ativa.](media/appsetup4.png)

*Os aplicativos incluídos nesta imagem são apenas exemplos e podem não estar disponíveis para uso.*

Esse comportamento é esperado para um dispositivo em um espaço compartilhado e ajuda a evitar a fixação não intencional do aplicativo.
