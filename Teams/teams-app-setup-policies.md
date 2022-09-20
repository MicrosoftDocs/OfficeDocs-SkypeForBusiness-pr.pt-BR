---
title: Gerenciar políticas de configuração de aplicativo no Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como criar, editar e gerenciar políticas de configuração de aplicativo para fixar e instalar aplicativos e permitir que os usuários carreguem aplicativos personalizados.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: d192bffdc83510da021914627c65b03f190c6c63
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837171"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gerenciar políticas de configuração de aplicativo no Microsoft Teams

Como administrador, você usa políticas de configuração de aplicativo para instalar e fixar aplicativos e permite que os usuários carreguem aplicativos personalizados. A fixação ajuda a promover a adoção de aplicativos relevantes em sua organização.

* **Fixar aplicativos:** as políticas de configuração permitem selecionar aplicativos para fixar e definir a ordem em que eles aparecerão para seus usuários na barra de aplicativos do Microsoft Teams ou na área de redação de mensagem. Os administradores também controlarão se os usuários finais poderão fixar seus próprios aplicativos ou não. Confira [Fixar aplicativos](#pin-apps).
* **Instalar aplicativos:** as políticas de configuração de aplicativo permitem instalar os aplicativos permitidos em nome dos usuários quando eles iniciam o Teams e durante as reuniões. Para obter mais informações, confira [Instalar aplicativos](#install-apps).
* **Carregar aplicativos personalizados:** as políticas de configuração de aplicativo permitem que os usuários carreguem aplicativos personalizados no Teams. Para obter mais informações, confira [Carregar aplicativos personalizados](teams-custom-app-policies-and-settings.md).

Por padrão, as seguintes políticas internas de configuração de aplicativo estão disponíveis no Centro de administração do Microsoft Teams:

* **Global (padrão em toda a organização)**: essa política padrão se aplica a todos os usuários em sua organização, a menos que você atribua outra política. Edite a política global para fixar aplicativos que são mais importantes para seus usuários.

* **FirstlineWorker**: esta política é para o trabalhador de linha de frente. A política não pode ser personalizada. Você pode atribuí-la aos trabalhadores de linha de frente da sua organização.

## <a name="pin-apps"></a>Fixar aplicativos

Fixar aplicativos permite destacar aplicativos que os usuários da sua organização mais precisam. A fixação funciona para todos os tipos de aplicativos no Teams — Aplicativos principais, aplicativos fornecidos pela Microsoft, aplicativos de terceiros e personalizados desenvolvidos em sua organização. Fixar um aplicativo por meio de uma política de configuração de aplicativo também o instala, se esse aplicativo for permitido para o usuário. Usando uma política de configuração de aplicativo, você poderá realizar as seguintes tarefas:

* Personalizar o Microsoft Teams para que os usuários finais destaquem os aplicativos que são mais importantes para eles. Você escolhe os aplicativos a serem fixados e a ordem em que eles serão exibidos.
* Controle se os usuários poderão fixar aplicativos ou não.

Os aplicativos são fixados na barra de aplicativos no lado esquerdo do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams.

|Cliente de área de trabalho do Teams  |Cliente de dispositivo móvel do Teams |
|---------|---------|
|![Barra de aplicativos no cliente da área de trabalho do Teams.](media/app-setup-policies-desktop-app-bar.png).  |   ![Barra de aplicativos no cliente móvel do Teams.](media/mobile-app-ui.png)      |

As extensões de mensagens estão disponíveis na parte inferior da área de redação de mensagem.

Para fixar aplicativos usando uma política de configuração de aplicativo, siga estas etapas:

1. Entre no Centro de administração do Teams e acesse **Aplicativos do Teams** > **[Políticas de configuração](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Selecione **Adicionar**.

1. Insira um nome e uma descrição para a política.

1. Ative a **Fixação do usuário**.

   > [!NOTE]
   > A configuração de **Fixação do usuário** está disponível no Centro de administração do Teams em ambientes da Nuvem da Comunidade Governamental do Microsoft 365 (GCC, GCC High e DoD), mas não tem efeito.

1. Em **Aplicativos fixados**, selecione **Adicionar aplicativos**.

1. No painel **Adicionar aplicativos fixados**, pesquise os aplicativos que deseja adicionar e selecione **Adicionar**. Você também pode filtrar aplicativos por política de permissão de aplicativo.

1. Selecione **Adicionar**.

1. Na **Barra de aplicativos** ou **Extensões de mensagens**, organize os aplicativos na ordem em que você deseja que eles apareçam no Teams.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Uma captura de tela dos aplicativos fixados e das extensões de mensagens fixadas na política de instalação.":::

1. Selecione **Salvar**.

> [!NOTE]
> No Teams para Educação, o aplicativo Atribuições é fixado por padrão na política global, mesmo que você não o veja listado na política global.

> [!NOTE]
> Para os trabalhadores de linha de frente da sua organização, recomendamos usar a experiência do aplicativo de linha de frente personalizada. Esse recurso fixa os aplicativos mais relevantes no Teams para usuários que têm uma [Licença F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt). Para saber mais, confira [Personalizar aplicativos do Teams para seus funcionários de linha de frente](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

## <a name="install-apps"></a>Instalar aplicativos

Usando uma política de configuração de aplicativo, um administrador pode realizar as seguintes tarefas:

* Instalar aplicativos para usuários finais em seu ambiente pessoal do Teams.
* Instalar aplicativos para usuários finais como [extensões de mensagens](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).

Os usuários finais poderão instalar aplicativos por conta própria se a [](teams-app-permission-policies.md) política de permissão do aplicativo permitir e o aplicativo for permitido pelo administrador do Teams. Em vez disso, se um aplicativo estiver bloqueado para um usuário ou para uma organização, os usuários finais poderão [solicitar aprovação do administrador](user-requests-approve-apps.md).

Para instalar aplicativos usando uma política de configuração de aplicativo, siga estas etapas:

1. Entre no Centro de administração do Teams e acesse **Aplicativos do Teams** > **[Políticas de configuração](https://admin.teams.microsoft.com/policies/app-setup)**.
1. Selecione **Adicionar**.
1. Forneça um nome e uma descrição para a política.
1. Em aplicativos **Instalados**, selecione **Adicionar aplicativos**.
1. No painel **Adicionar aplicativos instalados**, pesquise os aplicativos que deseja instalar para os usuários. Você também pode filtrar aplicativos por política de permissão de aplicativo.
1. Selecione **Adicionar**.

:::image type="content" source="media/install-apps-in-meeting.png" alt-text="Uma captura de tela da instalação de aplicativos por meio da política de aplicativo.":::

## <a name="manage-app-setup-policies"></a>Gerenciar políticas de configuração de aplicativo

Você gerencia as políticas de configuração de aplicativo no Centro de administração do Microsoft Teams. Use a política global (padrão em toda a organização) ou crie e atribua políticas personalizadas. Os usuários finais obtêm a política global. Se você criar uma política personalizada, ela substituirá a política global. O administrador global ou o administrador de serviço do Teams poderão gerenciar essas políticas.

Edite as configurações na política global para incluir os aplicativos desejados. Para personalizar o Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas.

![Página de políticas de configuração de aplicativo para gerenciar políticas ou adicionar novas políticas.](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>Editar uma política de configuração de aplicativo

Use o Centro de administração do Microsoft Teams para editar uma política, incluindo a política global (padrão em toda a organização) e as políticas personalizadas que você cria. Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

1. Entre no Centro de administração do Teams e acesse **Aplicativos do Teams** > **[Políticas de configuração](https://admin.teams.microsoft.com/policies/app-setup)**.
1. Escolha a política que você deseja editar e selecione **Editar**.

1. Faça as alterações desejadas.

1. Selecione **Salvar**.

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>Atribuir uma política de configuração de aplicativo personalizada a usuários e grupos

Para saber como atribuir políticas aos usuários finais e aos grupos, confira [como atribuir políticas a usuários e grupos](assign-policies-users-and-groups.md).

## <a name="considerations-and-limitations"></a>Considerações e limitações

* Você não pode instalar aplicativos personalizados com guias configuráveis usando políticas de configuração de aplicativo.
* Os usuários finais não podem desinstalar um aplicativo instalado por um administrador.
* Os aplicativos fixados por meio da política de configuração de aplicativo podem ser desafixados pelo usuário (se a fixação do usuário for permitida na política de instalação).
* No Teams para Educação, o aplicativo Atribuições é fixado por padrão na política global, mesmo que você não o veja listado na política global.
* Não há limite para o número máximo de aplicativos fixados que podem ser adicionados a uma política. No entanto, pelo menos dois aplicativos devem ser fixados nos clientes móveis do Teams (iOS e Android). Se uma política tiver menos de dois aplicativos, os clientes móveis não refletirão as configurações da política e continuarão a usar a configuração existente.
* Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

## <a name="faqs"></a>Perguntas frequentes

### <a name="working-with-app-setup-policies"></a>Trabalhando com políticas de configuração de aplicativo

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Por que não consigo encontrar um aplicativo no painel Adicionar aplicativos fixados

Nem todos os aplicativos podem ser fixados no Teams por meio de uma política de configuração de aplicativo. Alguns aplicativos podem não suportar essa funcionalidade. Para localizar aplicativos que podem ser fixados, pesquise o aplicativo no painel **Adicionar aplicativos fixados**. As guias que têm um escopo pessoal (guias estáticas) e bots podem ser fixadas no cliente da área de trabalho do Teams e esses aplicativos estão disponíveis no painel **Adicionar aplicativos fixados**.

Lembre-se de que a loja de aplicativos do Teams lista todos os aplicativos do Teams. O painel **Adicionar aplicativos fixados** inclui apenas aplicativos que podem ser fixados no Teams por meio de uma política.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sou um administrador do Teams para Educação. O que preciso saber sobre as políticas de configuração do aplicativo no Teams para Educação

O aplicativo de Chamada não está disponível no Teams para Educação. Quando você cria uma nova política de configuração de aplicativo personalizado, o aplicativo de Chamada é exibido na lista de aplicativos. No entanto, o aplicativo não está fixado aos clientes do Teams e os usuários do Teams para Educação não verão o aplicativo de Chamada no Teams.

### <a name="user-experience"></a>Experiência de usuário

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Como os usuários poderão ver todos os seus aplicativos fixados no Teams

Para exibir todos os aplicativos fixados para um usuário, os usuários terão que fazer o seguinte, dependendo do número de aplicativos instalados e do tamanho da janela de cliente do Teams.

|Cliente de área de trabalho do Teams |Cliente de dispositivo móvel do Teams |
|---------|---------|
|Na barra de aplicativos ao lado do Teams, selecione **... Mais aplicativos**.| Na barra de aplicativos perto da parte inferior do Teams, deslize o dedo para cima.|
|![Mais aplicativos no cliente da área de trabalho do Teams.](media/app-setup-policies-desktop-more-apps.png)   |![mais aplicativos no cliente móvel do Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>O que preciso saber sobre a experiência móvel do Teams

Os clientes móveis do Teams (iOS e Android) suportam aplicativos pessoais com guias estáticas. Os aplicativos fixados no cliente da área de trabalho do Teams aparecerão nos clientes móveis do Teams. Bots pessoais aparecerão no Chat dos clientes móveis.

Os aplicativos de terceiros (que podem ser baixados na Teams Store) precisam ser aprovados antes de aparecerem no celular. Se um administrador fixar um aplicativo não aprovado pela Microsoft para Dispositivos Móveis, ele será exibido na Área de Trabalho do Teams, mas não aparecerá no dispositivo móvel. Para obter mais informações, confira [Clientes móveis](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients).

Com os clientes móveis do Teams, os usuários verão os principais aplicativos do Teams, como Atividade, Chat e Teams, e você poderá fixar alguns dos aplicativos fornecidos pela Microsoft.

#### <a name="order-of-apps-pinned-through-a-policy"></a>Ordem dos aplicativos fixados por meio de uma política

Os usuários podem alterar a ordem de seus aplicativos fixados na área de trabalho do Teams e nos clientes móveis se a opção **Fixação do usuário** estiver ativada. Os usuários não podem alterar a ordem de seus aplicativos fixados em clientes Web do Teams.

#### <a name="does-user-pinning-take-precedence"></a>A fixação do usuário tem precedência

As fixações do administrador sempre têm precedência. Se a **opção de fixação do** usuário estiver ativada, os aplicativos fixados pelos usuários serão exibidos abaixo dos aplicativos fixados pelos administradores. Se **a opção de fixação** do usuário estiver desativada, os usuários perderão os pinos existentes e somente os aplicativos fixados pelos administradores estarão disponíveis na barra de aplicativos.

### <a name="custom-teams-apps"></a>Aplicativos personalizados do Teams

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Minha organização criou um aplicativo personalizado do Teams e o publicou no AppSource ou no catálogo de aplicativos do locatário, mas o ícone do aplicativo não aparece conforme o esperado quando o aplicativo é fixado na barra de aplicativos do Teams. Como corrigir isso?

Certifique-se de seguir as diretrizes do logotipo antes de enviar o aplicativo. Para saber mais, confira [Lista de verificação para envio do Painel do Vendedor](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="related-articles"></a>Artigos relacionados

* [Configurações de administrador para aplicativos no Teams](admin-settings.md)
* [Atribuir políticas a usuários finais no Teams](assign-policies-users-and-groups.md)
