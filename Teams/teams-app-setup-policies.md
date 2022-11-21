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
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Saiba como criar, editar e gerenciar políticas de configuração de aplicativo para fixar e instalar aplicativos e permitir que os usuários carreguem aplicativos personalizados.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4c94f0610535fa014b0f759b104dd1aef901e055
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131000"
---
# <a name="use-app-setup-policies-to-pin-and-auto-install-apps-in-teams"></a>Usar políticas de configuração de aplicativo para fixar e instalar automaticamente aplicativos no Teams

Como administrador, você usa políticas de instalação de aplicativo para instalar e fixar aplicativos e controlar quais usuários específicos podem carregar aplicativos personalizados. A fixação ajuda a promover a adoção e fornecer acesso rápido aos aplicativos relevantes em sua organização.

* **[Fixar aplicativos](#pin-apps):** As políticas de configuração do aplicativo permitem que você escolha aplicativos para fixar, defina o pedido que os aplicativos aparecem para seus usuários na barra de aplicativos do Teams ou na área de mensagem de composição. Os administradores também controlarão se os usuários finais poderão fixar seus próprios aplicativos ou não.

* **[Instalar aplicativos](#install-apps):** As políticas de configuração do aplicativo permitem instalar os aplicativos permitidos em nome dos usuários quando eles iniciam o Teams e durante as reuniões.

* **Carregar aplicativos personalizados:** As políticas de configuração do aplicativo permitem controlar quais usuários podem carregar aplicativos personalizados no Teams. Consulte [Artigo Carregar aplicativos personalizados](teams-custom-app-policies-and-settings.md) .

Por padrão, as seguintes políticas internas de configuração de aplicativo estão disponíveis no Centro de administração do Microsoft Teams:

* **Global (padrão em toda a organização)**: essa política padrão se aplica a todos os usuários em sua organização, a menos que você atribua outra política. Edite a política global para fixar aplicativos que são mais importantes para seus usuários.

* **FirstlineWorker**: esta política é para o trabalhador de linha de frente. A política não pode ser personalizada. Você pode atribuí-la aos trabalhadores de linha de frente da sua organização.

## <a name="pin-apps"></a>Fixar aplicativos

Fixar um aplicativo exibe o aplicativo na barra de aplicativos no cliente do Teams. Os administradores podem fixar o aplicativo e podem permitir que os usuários fixem. A fixação é usada para realçar aplicativos que são mais necessários pelos usuários e promover a facilidade de acesso. A fixação funciona para todos os [tipos de aplicativos no Teams](deploy-apps-microsoft-teams-landing-page.md) – aplicativos principais, aplicativos fornecidos pela Microsoft, aplicativos de terceiros e aplicativos personalizados desenvolvidos em sua organização.

Os administradores podem fixar um aplicativo por meio de uma política de configuração de aplicativo. Os aplicativos fixados por administradores são instalados automaticamente para os usuários para os quais o aplicativo é permitido. Esse aplicativo não pode ser desinstalado pelos usuários finais. Usando uma política de configuração de aplicativo, você poderá realizar as seguintes tarefas:

* Personalize o Teams para usuários finais para realçar os aplicativos mais importantes para eles. Você escolhe os aplicativos a serem fixados e a ordem em que eles serão exibidos.
* Controle se os usuários poderão fixar aplicativos ou não.

Os aplicativos são fixados na barra de aplicativos no lado esquerdo do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams. As extensões de mensagens estão disponíveis na parte inferior da área de redação de mensagem.

|Cliente de área de trabalho do Teams  |Cliente de dispositivo móvel do Teams |
|---------|---------|
|![Captura de tela mostrando a barra de aplicativos no cliente da área de trabalho do Teams.](media/app-setup-policies-desktop-app-bar.png).  |   ![Captura de tela mostrando a barra de aplicativos no cliente móvel do Teams.](media/mobile-app-ui.png)      |

Para fixar aplicativos usando uma política de configuração de aplicativo, siga estas etapas:

1. Entre no Centro de administração do Teams e acesse **Aplicativos do Teams** > **[Políticas de configuração](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Selecione **Adicionar**.

1. Insira um nome e uma descrição para a política.

1. Opcionalmente, ative **a fixação do usuário** para permitir que os usuários fixem aplicativos e alterem a ordem dos aplicativos fixados.

1. Em **Aplicativos fixados**, selecione **Adicionar aplicativos**.

1. No painel **Adicionar aplicativos fixados**, pesquise os aplicativos que deseja adicionar e selecione **Adicionar**.

    :::image type="content" source="media/add-pinned-apps-trimmed.png" alt-text="Capturas de tela que mostram como adicionar aplicativos fixados na política de configuração do aplicativo." lightbox="media/add-pinned-apps-large.png":::

1. Selecione **Adicionar**.

1. Na **barra de aplicativos** ou **extensões de mensagens**, organize os aplicativos na ordem em que você deseja que os aplicativos apareçam no cliente do Teams.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Uma captura de tela dos aplicativos fixados e extensões de mensagens fixadas na política de instalação.":::

1. Selecione **Salvar**.

> [!NOTE]
> No Teams para Educação, o aplicativo Atribuições é fixado por padrão na política global, mesmo que você não o veja listado na política global.

> [!NOTE]
> Para os trabalhadores de linha de frente da sua organização, recomendamos usar a experiência do aplicativo de linha de frente personalizada. Esse recurso fixa os aplicativos mais relevantes no Teams para usuários que têm uma [Licença F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline). Para saber mais, confira [Personalizar aplicativos do Teams para seus funcionários de linha de frente](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

## <a name="install-apps"></a>Instalar aplicativos

Usando uma política de configuração de aplicativo, um administrador pode realizar as seguintes tarefas:

* Instalar aplicativos para usuários finais em seu ambiente pessoal do Teams.
* Instalar aplicativos para usuários finais como [extensões de mensagens](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).

Os usuários finais podem instalar aplicativos por conta própria se a [política de permissão do aplicativo](teams-app-permission-policies.md) permitir que eles o instalem e o aplicativo for permitido pelo administrador do Teams. Se um aplicativo for bloqueado, os usuários finais poderão [solicitar aprovação de administrador](user-requests-approve-apps.md).

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

:::image type="content" source="media/app-setup-policies-update.png" alt-text="Captura de tela mostrando a página de políticas de configuração do aplicativo com opções para gerenciar políticas ou adicionar novas políticas.":::

### <a name="edit-an-app-setup-policy"></a>Editar uma política de configuração de aplicativo

Use o Centro de administração do Microsoft Teams para editar uma política, incluindo a política global (padrão em toda a organização) e as políticas personalizadas que você cria. Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

1. Entre no Centro de administração do Teams e acesse **Aplicativos do Teams** > **[Políticas de configuração](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Escolha a política que você deseja editar e selecione **Editar**.

1. Faça as alterações desejadas.

1. Selecione **Salvar**.

### <a name="assign-a-custom-policy-in-app-setup-policy-to-users-and-groups"></a>Atribuir uma política personalizada na política de configuração de aplicativo a usuários e grupos

Para saber como atribuir políticas aos usuários finais e aos grupos, confira [como atribuir políticas a usuários e grupos](assign-policies-users-and-groups.md).

## <a name="considerations-and-limitations"></a>Considerações e limitações

* Você não pode instalar aplicativos personalizados com guias configuráveis usando políticas de configuração de aplicativo.

* Os usuários finais não podem desinstalar um aplicativo instalado por um administrador.

* Os usuários finais podem desafixar um aplicativo que é fixado por meio da política de configuração do aplicativo se a fixação do usuário for permitida na política.

* Os usuários podem alterar a ordem de seus aplicativos fixados na área de trabalho e nos clientes móveis do Teams se a opção de fixação do usuário estiver ativada. Os usuários não podem alterar a ordem de seus aplicativos fixados em clientes Web do Teams.

* As fixações do administrador sempre têm precedência. Se a opção Fixação de usuário estiver ativada, os aplicativos fixados pelos usuários exibirão abaixo dos aplicativos fixados pelos administradores. Se a opção fixação de usuário estiver desativada, os usuários perderão os pinos existentes e apenas os aplicativos fixados pelos administradores estarão disponíveis na barra de aplicativos.

* A configuração de fixação do usuário está disponível no centro de administração do Teams em ambientes de GCC (Nuvem da Comunidade Governamental) do Microsoft 365 (GCC, GCC High e DoD), mas não tem efeito.

* No Teams para Educação, o aplicativo Atribuições é fixado por padrão na política global, mesmo que você não o veja listado na política global.

* Não há limite para o número máximo de aplicativos fixados que podem ser adicionados a uma política. No entanto, pelo menos dois aplicativos devem ser fixados nos clientes móveis do Teams (iOS e Android). Se uma política tiver menos de dois aplicativos, os clientes móveis não refletirão as configurações da política e continuarão a usar a configuração existente.

* Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

* Nem todos os aplicativos podem ser fixados no Teams por meio de uma política de configuração de aplicativo. Alguns aplicativos podem não suportar essa funcionalidade. Para localizar aplicativos que podem ser fixados, pesquise o aplicativo no painel **Adicionar aplicativos fixados**. As guias que têm um escopo pessoal (guias estáticas) e bots podem ser fixadas no cliente da área de trabalho do Teams e esses aplicativos estão disponíveis no painel **Adicionar aplicativos fixados**. Enquanto a loja de aplicativos do Teams lista todos os aplicativos do Teams. O painel **Adicionar aplicativos fixados** inclui apenas aplicativos que podem ser fixados no Teams por meio de uma política.

* Em Teams para Educação, o aplicativo Calling não está disponível. Quando você cria uma nova política personalizada na política de instalação do aplicativo, o aplicativo Chamando é exibido na lista de aplicativos. No entanto, o aplicativo não está fixado aos clientes do Teams e os usuários do Teams para Educação não verão o aplicativo de Chamada no Teams.

## <a name="related-articles"></a>Artigos relacionados

* [Configurações de administrador para aplicativos no Teams](admin-settings.md)
* [Atribuir políticas a usuários finais no Teams](assign-policies-users-and-groups.md)
