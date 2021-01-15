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
ms.openlocfilehash: 7d5a2c70eae9227b550e1e435634a6a8773be39c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821111"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gerenciar políticas de configuração de aplicativo no Microsoft Teams

> [!NOTE]
> Se você habilitar a configuração do aplicativo em toda a **organização,** permitir a interação com aplicativos personalizados, talvez ainda não veja as políticas de configuração do aplicativo no centro de administração do Microsoft Teams. Ele está sendo lançado e estará disponível em breve em sua organização.

Como administrador, você pode usar políticas de configuração de aplicativo para realizar as seguintes tarefas:

- Personalize o Teams para destacar os aplicativos mais importantes para os usuários. Você escolhe os aplicativos para fixar e definir a ordem em que eles aparecem. Fixar aplicativos permite que você mostre aplicativos de que os usuários em sua organização precisam, incluindo aplicativos construídos por terceiros ou por desenvolvedores em sua organização.
- Controle se os usuários podem fixar aplicativos no Teams.
- Instale aplicativos em nome dos **usuários (na visualização).** Você escolhe quais aplicativos são instalados por padrão para os usuários quando eles iniciam o Teams. Lembre-se de que os usuários [](teams-app-permission-policies.md) ainda podem instalar aplicativos por conta própria se a política de permissão do aplicativo atribuída a eles permitir isso.

Os aplicativos são fixados na barra de aplicativos, que é a barra no lado do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams (iOS e Android).

|Cliente da área de trabalho do Teams  |Cliente de dispositivo móvel do Teams |
|---------|---------|
|![O cliente da área de trabalho do Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![O cliente móvel do Teams](media/mobile-app-ui.png)      |

Para ver seus aplicativos pré-instalados, na barra de aplicativos, os usuários selecionam **... Mais aplicativos** na área de trabalho e clientes Web do Teams e passe o dedo para cima nos clientes móveis.

Você gerencia políticas de configuração de aplicativos no centro de administração do Microsoft Teams. Use a política global (padrão de toda a organização) ou crie e atribua políticas personalizadas.  Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

Edite as configurações na política global para incluir os aplicativos que você deseja. Para personalizar o Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas.

![a página políticas de configuração do aplicativo](media/app-setup-policies.png)

> [!NOTE]
> Se você tiver o Teams para Educação, é importante saber que o aplicativo Assignments está fixado por padrão na política global, mesmo que, no momento, você não o veja listado na política global. Ele será o quarto aplicativo na lista de aplicativos fixados em clientes do Teams.

## <a name="create-a-custom-app-setup-policy"></a>Criar uma política de configuração de aplicativo personalizada

Você pode usar o centro de administração do Microsoft Teams para criar uma política personalizada.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de Instalação de **aplicativos**  >  **do** Teams.

2. Selecione **Adicionar**.

   ![a página Adicionar políticas de configuração de aplicativo](media/app-setup-policies-add.png)
    
3. Insira um nome e uma descrição para a política.

4. Ativar ou desativar o **carregamento de aplicativos personalizados,** dependendo se você deseja permitir que os usuários carreguem aplicativos personalizados no Teams. Você não poderá alterar essa configuração se **Permitir** aplicativos de terceiros estiver desligado nas [configurações de aplicativos](manage-apps.md#manage-org-wide-app-settings)em toda a organização.

5. Ativar ou desativar Permitir fixação do **usuário,** dependendo se você deseja permitir que os usuários personalizem a barra de aplicativos fixando aplicativos a ela.

   > [!NOTE]
   > A  configuração Permitir fixação do usuário está disponível no Centro de administração do Teams nos ambientes do Microsoft 365 Government Community Cloud (GCC), GCC, GCC High e DoD, mas atualmente não tem efeito.

6. Para instalar aplicativos para usuários **(na visualização),** faça as seguintes tarefas:

    1. Em **Aplicativos Instalados,** selecione **Adicionar aplicativos**.
    
    2. No painel **Adicionar aplicativos** instalados, pesquise os aplicativos que você deseja instalar automaticamente para os usuários quando iniciarem o Teams. Você também pode filtrar aplicativos por política de permissão de aplicativo. Quando você escolher sua lista de aplicativos, selecione **Adicionar**.

       ![o painel Adicionar aplicativos instalados](media/app-setup-policies-add-installed-apps.png)

7. Para fixar aplicativos, faça o seguinte:

    1. Em **Aplicativos Fixados,** selecione **Adicionar aplicativos**.
    
    2. No painel **Adicionar aplicativos** fixados, pesquise os aplicativos que você deseja adicionar e selecione **Adicionar**. Você também pode filtrar aplicativos por política de permissão de aplicativo. Quando você escolher sua lista de aplicativos para fixar, selecione **Adicionar**.

       ![o painel Adicionar aplicativos fixados](media/app-setup-policies-add-apps.png)

    3. Organize os aplicativos na ordem em que você deseja que eles apareçam no Teams e selecione **Salvar**.

       ![a seção Aplicativos fixados](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Editar uma política de configuração de aplicativo

Você pode usar o centro de administração do Microsoft Teams para editar uma política, incluindo a política global (padrão em toda a organização) e as políticas personalizadas que você criar.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de Instalação de **aplicativos**  >  **do** Teams.

2. Escolha a política clicando à esquerda do nome da política e selecionando **Editar**.

3. A partir daqui, faça as alterações desejadas.

4. Selecione **Salvar**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Atribuir uma política de configuração de aplicativo personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>Perguntas frequentes

### <a name="working-with-app-setup-policies"></a>Trabalhar com políticas de configuração de aplicativo

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quais políticas de configuração de aplicativo internas estão incluídas no centro de administração do Microsoft Teams

- **Global (padrão em toda a organização)**: Essa política padrão se aplica a todos os usuários em sua organização, a menos que você atribua outra política. Edite a política global para fixar aplicativos que são mais importantes para seus usuários.

- **FirstLineWorker**: Esta política é para Trabalhadores da Linha de Frente. Você pode atribuí-lo aos Trabalhadores da Linha de Frente em sua organização. É importante saber que, como as políticas personalizadas que você cria, você precisa atribuir a política aos usuários para que as configurações sejam ativas. Para obter mais informações, acesse [a seção Atribuir uma política de](#assign-a-custom-app-setup-policy-to-users) configuração de aplicativo personalizada aos usuários deste artigo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Por que não consigo encontrar um aplicativo no painel Adicionar aplicativos fixados

Nem todos os aplicativos podem ser fixados no Teams por meio de uma política de configuração de aplicativo. Alguns aplicativos podem não dar suporte a essa funcionalidade. Para encontrar aplicativos que podem ser fixados, pesquise o aplicativo no painel **Adicionar aplicativos fixados.** Guias com escopo pessoal (guias estáticas) e bots podem ser fixados no cliente  da área de trabalho do Teams e esses aplicativos estão disponíveis no painel Adicionar aplicativos fixados.

Lembre-se de que a loja de aplicativos do Teams lista todos os aplicativos do Teams. O **painel Adicionar aplicativos** fixados inclui apenas aplicativos que podem ser fixados no Teams por meio de uma política.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sou um administrador do Teams for Education. O que preciso saber sobre as políticas de configuração de aplicativos no Teams for Education

O aplicativo De chamada não está disponível no Teams for Education. Quando você cria uma nova política de configuração de aplicativo personalizada, o aplicativo De chamada é exibido na lista de aplicativos. No entanto, o aplicativo não está fixado nos clientes do Teams e os usuários do Teams para Educação não verão o aplicativo Chamadas no Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Quantos aplicativos fixados podem ser adicionados a uma política

No mínimo dois aplicativos devem ser fixados nos clientes móveis do Teams (iOS e Android). Se uma política tiver menos de dois aplicativos, os clientes móveis não refletirão as configurações de política e, em vez disso, continuarão a usar a configuração existente.

Não há limite para o número de aplicativos fixados que você pode adicionar a uma política.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo leva para que as alterações de política entrem em vigor

Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

### <a name="user-experience"></a>Experiência do usuário

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Como os usuários podem ver todos os seus aplicativos fixados no Teams

Para exibir todos os aplicativos fixados para um usuário, os usuários podem ter que fazer o seguinte, dependendo do número de aplicativos instalados e do tamanho da janela de cliente do Teams.

|Cliente da área de trabalho do Teams |Cliente de dispositivo móvel do Teams |
|---------|---------|
|Na barra de aplicativos ao lado do Teams, selecione **... Mais aplicativos.**| Na barra de aplicativos próxima à parte inferior do Teams, passe o dedo para cima.|
|![Mais aplicativos no cliente da área de trabalho do Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![mais aplicativos no cliente móvel do Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>O que preciso saber sobre a experiência móvel do Teams

Os clientes móveis do Teams (iOS e Android) atualmente não suportam aplicativos pessoais com guias estáticas. Dependendo dos aplicativos definidos na política, os aplicativos fixados no cliente da área de trabalho do Teams podem não aparecer nos clientes móveis do Teams. Os bots pessoais ainda aparecerão no Chat em clientes móveis.

Com os clientes móveis do Teams, os usuários verão os principais aplicativos do Teams, como Atividade, Chat e Teams, e você pode fixar alguns aplicativos de terceiros da Microsoft, como Shifts.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Os usuários podem alterar a ordem dos aplicativos fixados por meio de uma política

Os usuários podem alterar a ordem de seus aplicativos fixados em clientes móveis e de área de trabalho do Teams se a opção Permitir que o usuário fixe estiver ligado.  Os usuários não podem alterar a ordem de seus aplicativos fixados em clientes Web do Teams.

#### <a name="does-user-pinning-take-precedence"></a>A pinagem do usuário tem precedência

Se a política de configuração do aplicativo atribuída ao usuário for alterada para bloquear a fixação do aplicativo do usuário, o Teams removerá todos os aplicativos fixados na barra de aplicativos. Se a política for alterada para permitir a pinagem do aplicativo do usuário, os usuários deverão fixar seus aplicativos fixados anteriormente.

### <a name="custom-teams-apps"></a>Aplicativos personalizados do Teams

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Minha organização criou um aplicativo personalizado do Teams e o publicou, no AppSource ou no catálogo de aplicativos do locatário, mas o ícone do aplicativo não é exibido como esperado quando o aplicativo é fixado na barra de aplicativos no Teams. Como faço para corrigi-lo

Certifique-se de seguir as diretrizes de logotipo antes de enviar o aplicativo. Para saber mais, consulte [Lista de verificação para envio do Painel do Vendedor.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Tópicos relacionados

[Configurações de administração para aplicativos no Teams](admin-settings.md)

[Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md)
