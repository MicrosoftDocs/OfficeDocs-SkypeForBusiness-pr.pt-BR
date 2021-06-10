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
description: Saiba como usar e gerenciar políticas de configuração de aplicativos Microsoft Teams para usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059195"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gerenciar políticas de configuração de aplicativo no Microsoft Teams

Como administrador, você pode usar políticas de configuração de aplicativo para realizar as seguintes tarefas:

- Personalize o Teams para destacar os aplicativos mais importantes para os usuários. Escolha os aplicativos para fixar e definir a ordem que eles aparecem. Fixar aplicativos permite que você mostre aplicativos que os usuários em sua organização precisam, incluindo aplicativos construídos por terceiros ou por desenvolvedores em sua organização.
- Controle se os usuários podem fixar aplicativos no Teams.
- Instale aplicativos em nome dos usuários. Você escolhe quais aplicativos são instalados por padrão para os usuários quando eles começam a Teams. Lembre-se de que os usuários [](teams-app-permission-policies.md) ainda podem instalar aplicativos por conta própria se a política de permissão do aplicativo atribuída a eles permitir isso.

> [!Note]
> Para aplicativos instalados por administradores, os usuários não podem desinstalar esses aplicativos.

Os aplicativos são fixados na barra de aplicativos, que é a barra no lado do cliente da área de trabalho Teams e na parte inferior dos clientes móveis do Teams (iOS e Android).

|Teams da área de trabalho  |Cliente de dispositivo móvel do Teams |
|---------|---------|
|![O Teams da área de trabalho](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![O Teams cliente móvel](media/mobile-app-ui.png)      |

Para ver os aplicativos instalados pelos administradores, na barra de aplicativos, os usuários selecionam **... Mais aplicativos** no Teams da área de trabalho e da Web e passar o dedo para cima nos clientes móveis.

Você gerencia políticas de configuração de aplicativos no Microsoft Teams de administração. Use a política global (padrão em toda a organização) ou crie e atribua políticas personalizadas.  Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

Edite as configurações na política global para incluir os aplicativos que deseja. Para personalizar Teams diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas.

![a página Políticas de configuração de aplicativo](media/app-setup-policies.png)

> [!NOTE]
> Se você tiver Teams para Educação, é importante saber que o aplicativo Assignments está fixado por padrão na política global, mesmo que no momento, você não o veja listado na política global. Ele será o quarto aplicativo na lista de aplicativos fixados Teams clientes.

## <a name="create-a-custom-app-setup-policy"></a>Criar uma política de configuração de aplicativo personalizada

Você pode usar o Microsoft Teams de administração para criar uma política personalizada.

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá **para** Teams políticas  >  **de Instalação de aplicativos.**

2. Selecione **Adicionar**.

   ![a página Adicionar políticas de configuração de aplicativo](media/app-setup-policies-add.png)

3. Insira um nome e uma descrição para a política.

4. Ativar ou desativar Upload **aplicativos** personalizados, dependendo se você deseja permitir que os usuários carreguem aplicativos personalizados para Teams. Você não poderá alterar essa configuração se **Permitir** que aplicativos de terceiros estão desligados em [configurações de aplicativos](manage-apps.md#manage-org-wide-app-settings)em toda a organização.

5. Ativar ou desativar **Permitir** fixação do usuário, dependendo se você deseja permitir que os usuários personalizem sua barra de aplicativos fixando aplicativos a ela.

   > [!NOTE]
   > A **configuração** Permitir fixação do usuário está disponível no centro de administração do Teams em ambientes Microsoft 365 Nuvem da Comunidade Governamental (GCC) (GCC, GCC Alto e DoD), mas atualmente não tem efeito.

6. Para instalar aplicativos para usuários, faça as seguintes tarefas:

    1. Em **Aplicativos Instalados,** selecione **Adicionar aplicativos**.

    2. No painel **Adicionar aplicativos instalados,** pesquise os aplicativos que você deseja instalar automaticamente para os usuários quando eles começarem a Teams. Você também pode filtrar aplicativos por política de permissão do aplicativo. Quando você escolher sua lista de aplicativos, selecione **Adicionar**.

       ![o painel Adicionar aplicativos instalados](media/app-setup-policies-add-installed-apps.png)

7. Para fixar aplicativos, faça as seguintes etapas:

    1. Em **Aplicativos Fixados,** selecione **Adicionar aplicativos**.

    2. No painel **Adicionar aplicativos fixados,** pesquise os aplicativos que você deseja adicionar e selecione **Adicionar**. Você também pode filtrar aplicativos por política de permissão do aplicativo. Quando você escolheu sua lista de aplicativos a fixar, selecione **Adicionar**.

       ![o painel Adicionar aplicativos fixados](media/app-setup-policies-add-apps.png)

    3. Organize os aplicativos na ordem que você deseja que eles apareçam no Teams e selecione **Salvar**.

       ![a seção Aplicativos fixados](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Editar uma política de configuração de aplicativo

Você pode usar o Microsoft Teams de administração para editar uma política, incluindo a política global (padrão em toda a organização) e as políticas personalizadas que você criar.

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá **para** Teams políticas  >  **de Instalação de aplicativos.**

2. Escolha a política clicando à esquerda do nome da política e selecionando **Editar**.

3. A partir daqui, faça as alterações desejadas.

4. Selecione **Salvar**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Atribuir uma política de configuração de aplicativo personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>Perguntas frequentes

### <a name="working-with-app-setup-policies"></a>Trabalhar com políticas de configuração de aplicativos

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quais políticas internas de configuração de aplicativos estão incluídas no centro de Microsoft Teams de administração

- **Global (padrão em toda a organização)**: Essa política padrão se aplica a todos os usuários em sua organização, a menos que você atribua outra política. Edite a política global para fixar aplicativos que são mais importantes para seus usuários.

- **FrontlineWorker**: Esta política é para Trabalhadores de Linha de Frente. Você pode atribuí-lo aos Trabalhadores de Linha de Frente em sua organização. É importante saber que, como políticas personalizadas que você cria, você precisa atribuir a política aos usuários para que as configurações sejam ativas. Para obter mais informações, acesse a seção Atribuir uma política de configuração [de aplicativo personalizada aos](#assign-a-custom-app-setup-policy-to-users) usuários deste artigo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Por que não consigo encontrar um aplicativo no painel Adicionar aplicativos fixados

Nem todos os aplicativos podem ser fixados Teams por meio de uma política de configuração de aplicativo. Alguns aplicativos podem não dar suporte a essa funcionalidade. Para encontrar aplicativos que podem ser fixados, pesquise o aplicativo no painel **Adicionar aplicativos** fixados. Guias com escopo pessoal (guias estáticas) e bots podem ser fixados no cliente da área de trabalho Teams e esses aplicativos estão disponíveis no painel **Adicionar** aplicativos fixados.

Lembre-se de que o Teams de aplicativos lista todos os Teams aplicativos. O **painel Adicionar aplicativos** fixados inclui apenas aplicativos que podem ser fixados Teams por meio de uma política.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sou um administrador Teams educação. O que preciso saber sobre políticas de configuração de aplicativos no Teams Education

O aplicativo Chamar não está disponível no Teams education. Quando você cria uma nova política de configuração de aplicativo personalizada, o aplicativo De chamada é exibido na lista de aplicativos. No entanto, o aplicativo não está fixado em clientes Teams e Teams usuários do Education não verão o aplicativo Chamadas no Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Quantos aplicativos fixados podem ser adicionados a uma política

Um mínimo de dois aplicativos deve ser fixado nos clientes Teams móveis (iOS e Android). Se uma política tiver menos de dois aplicativos, os clientes móveis não refletirão as configurações de política e, em vez disso, continuarão a usar a configuração existente.

Não há limite para o número de aplicativos fixados que você pode adicionar a uma política.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo leva para que as alterações de política entre em vigor

Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

### <a name="user-experience"></a>Experiência de usuário

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Como os usuários podem ver todos os aplicativos fixados no Teams

Para exibir todos os aplicativos fixados para um usuário, os usuários podem ter que fazer o seguinte, dependendo do número de aplicativos instalados e do tamanho da janela do cliente Teams.

|Teams da área de trabalho |Cliente de dispositivo móvel do Teams |
|---------|---------|
|Na barra de aplicativos ao lado do Teams, selecione **... Mais aplicativos**.| Na barra de aplicativos próxima à parte inferior Teams, passe o dedo para cima.|
|![Mais aplicativos no cliente Teams área de trabalho](media/app-setup-policies-desktop-more-apps.png)<br>   |![mais aplicativos no cliente Teams celular](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>O que preciso saber sobre a experiência Teams celular

Os Teams móveis (iOS e Android) suportam aplicativos pessoais com guias estáticas. Os aplicativos fixados no Teams da área de trabalho serão exibidos no Teams móveis. Bots pessoais aparecerão em Chat em clientes móveis.

Aplicativos de terceiros (que podem ser baixados da Teams Store) precisam ser aprovados antes de aparecerem no celular. Se um administrador fixar um aplicativo, que não é aprovado pela Microsoft para Dispositivos Móveis, ele será aparecer na área de trabalho Teams, mas não aparecer no celular. Consulte [Clientes móveis para](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) obter mais informações.

Com os Teams móveis, os usuários verão os principais Teams aplicativos, como Atividade, Chat e Teams, e você poderá fixar alguns aplicativos de primeira parte da Microsoft, como Shifts.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Os usuários podem alterar a ordem dos aplicativos fixados por meio de uma política

Os usuários podem alterar a ordem de seus aplicativos fixados Teams clientes móveis e desktop se a opção Permitir que o **pinning** do usuário seja ligado. Os usuários não podem alterar a ordem de seus aplicativos fixados em Teams web.

#### <a name="does-user-pinning-take-precedence"></a>O pinamento do usuário tem precedência

Os pinos de administrador sempre têm precedência. Se a **opção Permitir que o pinamento do** usuário estiver ligado, os usuários manterão seus aplicativos fixados abaixo dos aplicativos fixados pelo administrador. Se a **opção Permitir fixação** do usuário estiver desabilitada, os usuários perderão seus pinos pré-existentes e somente aplicativos fixados por administrador estarão presentes na barra de aplicativos.

### <a name="custom-teams-apps"></a>Aplicativos Teams personalizados

Minha organização criou um aplicativo Teams personalizado e o publicou, no AppSource ou no catálogo de aplicativos de locatários, mas o ícone do aplicativo não é exibido como esperado quando o aplicativo é fixado na barra de aplicativos em Teams. Como posso corrigi-lo

Certifique-se de seguir as diretrizes de logotipo antes de enviar o aplicativo. Para saber mais, consulte [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="related-topics"></a>Tópicos relacionados

[Configurações de administrador para aplicativos no Teams](admin-settings.md)

[Atribua políticas a seus usuários no Teams](assign-policies.md)
