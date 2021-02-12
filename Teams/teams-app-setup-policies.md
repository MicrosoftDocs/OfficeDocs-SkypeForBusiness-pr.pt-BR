---
title: Gerenciar políticas de configuração de aplicativo no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de configuração de aplicativos no Microsoft Teams para usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ffc2f15cdbef49daf36e09ca9676925ebb1ac99e
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145918"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gerenciar políticas de configuração de aplicativo no Microsoft Teams

Como administrador, você pode usar políticas de configuração de aplicativo para realizar as seguintes tarefas:

- Personalize o Teams para destacar os aplicativos mais importantes para os usuários. Escolha os aplicativos para fixar e definir a ordem em que eles aparecem. Fixar aplicativos permite mostrar aplicativos de que os usuários em sua organização precisam, incluindo aplicativos criado por terceiros ou por desenvolvedores em sua organização.
- Controle se os usuários podem fixar aplicativos no Teams.
- Instale aplicativos em nome dos usuários **(em visualização).** Você escolhe quais aplicativos são instalados por padrão para os usuários quando eles iniciam o Teams. Lembre-se de que os usuários [](teams-app-permission-policies.md) ainda podem instalar aplicativos por conta própria se a política de permissão do aplicativo atribuída a eles permitir.

Os aplicativos são fixados na barra de aplicativos, que é a barra na lateral do cliente de área de trabalho do Teams e na parte inferior dos clientes móveis do Teams (iOS e Android).

|Cliente de área de trabalho do Teams  |Cliente de dispositivo móvel do Teams |
|---------|---------|
|![O cliente de área de trabalho do Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![O cliente móvel do Teams](media/mobile-app-ui.png)      |

Para ver seus aplicativos pré-instalados, na barra de aplicativos, os usuários **selecionam... Mais aplicativos** na área de trabalho do Teams e clientes Web e passe o dedo para cima nos clientes móveis.

Você gerencia políticas de configuração de aplicativos no Centro de administração do Microsoft Teams. Use a política global (padrão de toda a organização) ou crie e atribua políticas personalizadas.  Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

Edite as configurações na política global para incluir os aplicativos que você deseja. Para personalizar o Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas.

![a página políticas de configuração de aplicativos](media/app-setup-policies.png)

> [!NOTE]
> Se você tiver o Teams for Education, é importante saber que o aplicativo Tarefas está fixado por padrão na política global, embora atualmente, você não o veja listado na política global. Ele será o quarto aplicativo na lista de aplicativos fixados em clientes do Teams.

## <a name="create-a-custom-app-setup-policy"></a>Criar uma política de configuração de aplicativo personalizada

Você pode usar o Centro de administração do Microsoft Teams para criar uma política personalizada.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas **de configuração** de aplicativos  >  **do** Teams.

2. Selecione **Adicionar**.

   ![a página Adicionar políticas de configuração de aplicativo](media/app-setup-policies-add.png)
    
3. Insira um nome e uma descrição para a política.

4. A ativar ou desativar o carregamento de aplicativos **personalizados,** dependendo se você deseja permitir que os usuários carreguem aplicativos personalizados para o Teams. Você não poderá alterar essa configuração se **Permitir** aplicativos de terceiros estiver desligado nas [configurações de](manage-apps.md#manage-org-wide-app-settings)aplicativos de toda a organização.

5. A ligue ou desligue Permitir **fixação** do usuário, dependendo se você deseja permitir que os usuários personalizem a barra de aplicativos fixando aplicativos a ela.

   > [!NOTE]
   > A  configuração Permitir fixação do usuário está disponível no Centro de administração do Teams em ambientes de GCC (Government Community Cloud) do Microsoft 365 (GCC, GCC High and DoD), mas atualmente não tem efeito.

6. Para instalar aplicativos para usuários **(na visualização),** faça as seguintes tarefas:

    1. Em **Aplicativos instalados,** selecione **Adicionar aplicativos.**
    
    2. No painel **Adicionar aplicativos instalados,** procure os aplicativos que você deseja instalar automaticamente para os usuários quando eles iniciarem o Teams. Você também pode filtrar aplicativos por política de permissão do aplicativo. Quando você escolher sua lista de aplicativos, selecione **Adicionar.**

       ![o painel Adicionar aplicativos instalados](media/app-setup-policies-add-installed-apps.png)

7. Para fixar aplicativos, faça o seguinte:

    1. Em **Aplicativos fixados,** selecione **Adicionar aplicativos.**
    
    2. No painel **Adicionar aplicativos fixados,** procure os aplicativos que você deseja adicionar e selecione **Adicionar.** Você também pode filtrar aplicativos por política de permissão do aplicativo. Quando você escolheu sua lista de aplicativos para fixar, selecione **Adicionar.**

       ![o painel Adicionar aplicativos fixados](media/app-setup-policies-add-apps.png)

    3. Organize os aplicativos na ordem em que você deseja que eles apareçam no Teams e selecione **Salvar.**

       ![a seção Aplicativos fixados](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Editar uma política de configuração de aplicativo

Você pode usar o Centro de administração do Microsoft Teams para editar uma política, incluindo a política global (padrão de toda a organização) e as políticas personalizadas que você criar.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas **de configuração** de aplicativos  >  **do** Teams.

2. Escolha a política clicando à esquerda do nome da política e selecionando **Editar**.

3. A partir daqui, faça as alterações desejadas.

4. Selecione **Salvar**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Atribuir uma política de configuração de aplicativo personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>Perguntas frequentes

### <a name="working-with-app-setup-policies"></a>Trabalhando com políticas de configuração de aplicativos

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quais políticas internas de configuração de aplicativos estão incluídas no Centro de administração do Microsoft Teams

- **Global (padrão em toda a organização)**: essa política padrão se aplica a todos os usuários em sua organização, a menos que você atribua outra política. Edite a política global para fixar aplicativos que são mais importantes para seus usuários.

- **FrontlineWorker:** esta política é para Trabalhadores de Linha de Frente. Você pode atribuí-lo aos Trabalhadores de Linha de Frente em sua organização. É importante saber que, como as políticas personalizadas que você cria, é preciso atribuir a política aos usuários para que as configurações sejam ativas. Para obter mais informações, acesse a seção Atribuir uma política de configuração [de aplicativo personalizada aos](#assign-a-custom-app-setup-policy-to-users) usuários deste artigo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Por que não consigo encontrar um aplicativo no painel Adicionar aplicativos fixados

Nem todos os aplicativos podem ser fixados no Teams por meio de uma política de configuração de aplicativo. Alguns aplicativos podem não dar suporte a essa funcionalidade. Para encontrar aplicativos que podem ser fixados, procure o aplicativo no painel Adicionar aplicativos **fixados.** As guias que têm um escopo pessoal (guias estáticas) e bots podem ser fixadas ao cliente de área de trabalho do Teams e esses aplicativos estão disponíveis no painel Adicionar aplicativos **fixados.**

Lembre-se de que a loja de aplicativos do Teams lista todos os aplicativos do Teams. O **painel Adicionar aplicativos** fixados inclui apenas aplicativos que podem ser fixados no Teams por meio de uma política.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sou administrador do Teams for Education. O que preciso saber sobre políticas de configuração de aplicativos no Teams for Education

O aplicativo Chamada não está disponível no Teams for Education. Quando você cria uma nova política de configuração de aplicativo personalizado, o aplicativo Chamada é exibido na lista de aplicativos. No entanto, o aplicativo não está fixado aos clientes do Teams e os usuários do Teams para Educação não verão o aplicativo Chamadas no Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Quantos aplicativos fixados podem ser adicionados a uma política

Um mínimo de dois aplicativos deve ser fixado nos clientes móveis do Teams (iOS e Android). Se uma política tiver menos de dois aplicativos, os clientes móveis não refletirão as configurações de política e continuarão a usar a configuração existente.

Não há limite para o número de aplicativos fixados que você pode adicionar a uma política.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo leva para que as alterações de política entre em vigor

Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

### <a name="user-experience"></a>Experiência de usuário

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Como os usuários podem ver todos os aplicativos fixados no Teams

Para exibir todos os aplicativos fixados para um usuário, os usuários podem ter que fazer o seguinte dependendo do número de aplicativos instalados e do tamanho da janela do cliente do Teams.

|Cliente de área de trabalho do Teams |Cliente de dispositivo móvel do Teams |
|---------|---------|
|Na barra de aplicativos ao lado do Teams, selecione **... Mais aplicativos.**| Na barra de aplicativos na parte inferior do Teams, deslize o dedo para cima.|
|![Mais aplicativos no cliente de área de trabalho do Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![mais aplicativos no cliente móvel do Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>O que preciso saber sobre a experiência móvel do Teams

Os clientes móveis do Teams (iOS e Android) atualmente não são suportados por aplicativos pessoais com guias estáticas. Dependendo dos aplicativos definidos na política, os aplicativos fixados no cliente de área de trabalho do Teams podem não aparecer nos clientes móveis do Teams. Os bots pessoais ainda aparecerão no Chat em clientes móveis.

Com os clientes móveis do Teams, os usuários verão os principais aplicativos do Teams, como Atividade, Chat e Teams, e você pode fixar alguns aplicativos de primeira mão da Microsoft, como o Shifts.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Os usuários podem alterar a ordem dos aplicativos fixados por meio de uma política

Os usuários podem alterar a ordem de seus aplicativos fixados na área de trabalho do Teams e em clientes móveis se a opção Permitir que o usuário fixe está ligado.  Os usuários não podem alterar a ordem de seus aplicativos fixados em clientes Web do Teams.

#### <a name="does-user-pinning-take-precedence"></a>O pinamento do usuário tem precedência

Se a política de configuração de aplicativo atribuída ao usuário for alterada para bloquear a fixação do aplicativo do usuário, o Teams removerá todos os aplicativos fixados na barra do aplicativo. Se a política for alterada para permitir a pinagem do aplicativo do usuário, os usuários deverão fixar os aplicativos anteriormente fixados.

### <a name="custom-teams-apps"></a>Aplicativos personalizados do Teams

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Minha organização criou um aplicativo personalizado do Teams e o publicou, no AppSource ou no catálogo de aplicativos do locatário, mas o ícone do aplicativo não é exibido como esperado quando o aplicativo é fixado na barra de aplicativos no Teams. Como faço para corrigi-lo

Certifique-se de seguir as diretrizes do logotipo antes de enviar o aplicativo. Para saber mais, confira a [lista de verificação do envio do Painel do Vendedor.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Tópicos relacionados

[Configurações de administrador para aplicativos no Teams](admin-settings.md)

[Atribua políticas a seus usuários no Teams](assign-policies.md)
