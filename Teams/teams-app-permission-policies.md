---
title: Gerenciar políticas de permissões de aplicativo no Microsoft Teams
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
description: Saiba mais sobre as políticas de permissão de aplicativo no Microsoft Teams e como usá-las para controlar quais aplicativos estão disponíveis para usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802491"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gerenciar políticas de permissões de aplicativo no Microsoft Teams

Como administrador, você pode usar as políticas de permissão do aplicativo para controlar quais aplicativos estarão disponíveis para os usuários do Microsoft Teams em sua organização. Você pode permitir ou bloquear todos os aplicativos ou aplicativos específicos publicados pela Microsoft, por terceiros e pela sua organização. Ao bloquear um aplicativo, os usuários que têm a política não conseguem instalá-lo da loja de aplicativos do Teams. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

Você gerencia políticas de permissão de aplicativo no centro de administração do Microsoft Teams. Você pode usar a política global (padrão em toda a organização) ou criar e atribuir políticas personalizadas. Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

![Captura de tela da política de permissão do aplicativo](media/app-permission-policies.png)

> [!NOTE]
> As configurações de aplicativos em toda a organização substituem a política global e quaisquer políticas personalizadas que você criar e atribuir aos usuários.

Se sua organização já estiver no Teams, as  configurações de aplicativo que você definiu nas configurações de todo o [](manage-apps.md) locatário no Centro de administração do Microsoft 365 serão refletidas nas configurações de aplicativos em toda a organização na página Gerenciar aplicativos. Se você é novo no Teams e está apenas começando, por padrão, todos os aplicativos são permitidos na política global. Isso inclui aplicativos publicados pela Microsoft, terceiros e sua organização.

Por exemplo, você deseja bloquear todos os aplicativos de terceiros e permitir aplicativos específicos da Microsoft para a equipe de RH em sua organização. Primeiro, vá para [](manage-apps.md) a página Gerenciar aplicativos e certifique-se de que os aplicativos que você deseja permitir para a equipe de RH sejam permitidos no nível da organização. Em seguida, crie uma política personalizada chamada Política de Permissão de Aplicativo de RH, de configurar para bloquear e permitir os aplicativos que você deseja e atribuí-la aos usuários na equipe de RH.

> [!NOTE]
> Se você implantou o Teams em um ambiente do Microsoft 365 Government Community Cloud (GCC), confira Gerenciar configurações de aplicativos em toda a organização do [Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) para saber mais sobre configurações de aplicativos de terceiros que são exclusivas do GCC.

## <a name="create-a-custom-app-permission-policy"></a>Criar uma política de permissão de aplicativo personalizada

Se você quiser controlar os aplicativos que estão disponíveis para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de permissão de aplicativo personalizadas. Você pode criar e atribuir políticas personalizadas separadas com base em se os aplicativos são publicados pela Microsoft, por terceiros ou por sua organização. É importante saber que depois de criar uma política personalizada, você não poderá alterá-la se aplicativos de terceiros estão desabilitados nas configurações de aplicativos em toda a organização.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas **de permissão de aplicativos**  >  **do** Teams.
2. Clique em **Adicionar**. <br>
    ![Captura de tela da nova política de permissão do aplicativo](media/app-permission-policies-new-policy.png)
3. Insira um nome e uma descrição para a política.
4. Em **aplicativos da Microsoft,** **aplicativos de** terceiros e **aplicativos personalizados,** selecione um dos seguintes:

    - **Permitir todos os aplicativos**
    - **Permitir aplicativos específicos e bloquear todos os outros**
    - **Bloquear aplicativos específicos e permitir todos os outros**
    - **Bloquear todos os aplicativos**

5. Se você **selecionou Permitir aplicativos específicos** e bloquear outros, adicione os aplicativos que deseja permitir:

    1. Selecione **Permitir aplicativos**.
    1. Pesquise os aplicativos que você deseja permitir e clique em **Adicionar**. Os resultados da pesquisa são filtrados para o editor de aplicativos (**aplicativos da Microsoft,** **aplicativos de** terceiros ou **aplicativos personalizados**).
    1. Quando você escolher a lista de aplicativos, clique em **Permitir**. 

6. Da mesma forma, se você selecionou Bloquear aplicativos específicos e permitir todos os **outros,** pesquise e adicione os aplicativos que deseja bloquear e clique em **Bloquear.**
7. Clique em **Salvar**.

## <a name="edit-an-app-permission-policy"></a>Editar uma política de permissão de aplicativo

Você pode usar o centro de administração do Microsoft Teams para editar uma política, incluindo a política global e as políticas personalizadas que você criar.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas **de permissão de aplicativos**  >  **do** Teams.
2. Selecione a política clicando à esquerda do nome da política e clique em **Editar**.
3. A partir daqui, faça as alterações desejadas. Você pode gerenciar configurações com base no editor de aplicativos e adicionar e remover aplicativos com base na configuração de permitir/bloquear.
4. Clique em **Salvar**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Atribuir uma política de permissão de aplicativo personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Gerenciar configurações de aplicativos em toda a organização para o Microsoft 365 Government  

Em um Microsoft 365 Government - implantação GCC do Teams, é importante saber o seguinte sobre configurações de aplicativos de terceiros, que são exclusivas do GCC.

Na GCC, todos os aplicativos de terceiros são bloqueados por padrão. Além disso, você verá a observação a seguir sobre como gerenciar aplicativos de terceiros na página políticas de permissão do aplicativo no centro de administração do Microsoft Teams.

![Captura de tela da política de permissão do aplicativo no GCC](media/app-permission-policies-gcc.png)

Use configurações de aplicativos em toda a organização para controlar se os usuários podem instalar aplicativos de terceiros. As configurações de aplicativos em toda a organização regem o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Você pode usá-los para controlar aplicativos mal-intencionados ou problemáticos.

1. Na página **Políticas de permissão,** selecione **configurações de aplicativos** em toda a organização. Em seguida, você pode definir as configurações que deseja no painel.

    ![Captura de tela das configurações de aplicativos em toda a organização](media/app-permission-policies-gcc-org-wide.png)
    
2. Em **aplicativos de** terceiros, desativar ou ativar essas configurações para controlar o acesso a aplicativos de terceiros:

    - **Permitir aplicativos de terceiros:** isso controla se os usuários podem usar aplicativos de terceiros. Se você desativar essa configuração, os usuários não poderão instalar ou usar aplicativos de terceiros. Em um Microsoft 365 Government - implantação GCC do Teams, essa configuração está desligada por padrão.
    - **Permita que novos** aplicativos de terceiros publicados na loja por padrão: isso controla se novos aplicativos de terceiros publicados na loja de aplicativos do Teams ficam automaticamente disponíveis no Teams. Você só poderá definir essa opção se permitir aplicativos de terceiros.

3. Em **aplicativos bloqueados,** adicione os aplicativos que você deseja bloquear em sua organização. Em um Microsoft 365 Government - implantação GCC do Teams, todos os aplicativos de terceiros são adicionados a essa lista por padrão. Para qualquer aplicativo de terceiros que você deseja permitir em sua organização, remova o aplicativo dessa lista de aplicativos bloqueados. Quando você bloqueia um aplicativo em toda a organização, o aplicativo é bloqueado automaticamente para todos os usuários, independentemente de ele ser permitido em qualquer política de permissão de aplicativo
4. Clique **em Salvar** para que as configurações de aplicativos em toda a organização entre em vigor.

Conforme mencionado anteriormente, para permitir aplicativos de terceiros, você pode editar e usar a política global (padrão em toda a organização) ou criar e atribuir políticas personalizadas.

## <a name="faq"></a>Perguntas frequentes

### <a name="working-with-app-permission-policies"></a>Trabalhar com políticas de permissão de aplicativo

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Quais interações de aplicativo afetam as políticas de permissão?
As políticas de permissão controlam o uso do aplicativo controlando a instalação, a descoberta e a interação dos usuários finais. Os administradores ainda podem gerenciar aplicativos no centro de administração do Microsoft Teams, independentemente das políticas de permissão atribuídas a eles.

#### <a name="can-i-control-line-of-business-lob-apps"></a>Posso controlar aplicativos de linha de negócios (LOB) ?
Sim, você pode usar políticas de permissão de aplicativo para controlar a distribuição e distribuição de aplicativos personalizados (LOB). Você pode criar uma política personalizada ou editar a política global para permitir ou bloquear aplicativos personalizados com base nas necessidades da sua organização.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Como as políticas de permissão de aplicativo se relacionam a aplicativos fixados e políticas de configuração de aplicativos?

Você pode usar políticas de configuração de aplicativo junto com políticas de permissão de aplicativo. Os aplicativos pré-fixados são selecionados no conjunto de aplicativos habilitados para um usuário. Além disso, se um usuário tiver uma política de permissão de aplicativo que bloqueia um aplicativo em sua política de configuração de aplicativo, esse aplicativo não aparecerá no Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>Posso usar políticas de permissão de aplicativo para restringir o carregamento de aplicativos personalizados?

Você pode usar as configurações  de toda a organização na página Gerenciar aplicativos ou políticas de configuração de aplicativos para restringir o carregamento de aplicativos personalizados para sua organização.  

Para restringir o carregamento de aplicativos personalizados por usuários específicos, use políticas de aplicativo personalizadas. Para saber mais, confira Gerenciar políticas e configurações [de aplicativos personalizados no Teams.](teams-custom-app-policies-and-settings.md)

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>O bloqueio de um aplicativo se aplica a clientes móveis do Teams?

Sim, quando você bloqueia um aplicativo, esse aplicativo é bloqueado em todos os clientes do Teams.  

### <a name="user-experience"></a>Experiência do usuário

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>O que um usuário experimentará quando um aplicativo for bloqueado?

Os usuários não podem interagir com um aplicativo bloqueado ou seus recursos, como bots, guias e extensões de mensagens. Em um contexto compartilhado, como um chat de equipe ou grupo, os bots ainda podem enviar mensagens para todos os participantes desse contexto. O Teams indica ao usuário quando um aplicativo é bloqueado.

Por exemplo, quando um aplicativo é bloqueado, os usuários não podem fazer nada do seguinte:

- Adicionar o aplicativo pessoalmente ou a um chat ou equipe
- Enviar mensagens para o bot do aplicativo
- Executar ações de botão que enviam informações de volta para o aplicativo, como mensagens ativas  
- Exibir a guia do aplicativo
- Configurar conectores para receber notificações
- Usar a extensão de mensagens do aplicativo

O portal herdado permitia controlar aplicativos no nível da organização, o que significa que quando um aplicativo é bloqueado, ele é bloqueado para todos os usuários na organização. Bloquear um aplicativo na página [Gerenciar aplicativos](manage-apps.md) funciona exatamente da mesma maneira.

Para políticas de permissão de aplicativo atribuídas a usuários específicos, se um aplicativo com funcionalidade de bot ou conector foi permitido e bloqueado e, em seguida, se o aplicativo for permitido apenas para alguns usuários em um contexto compartilhado, membros de um chat de grupo ou canal que não têm permissão para esse aplicativo podem ver o histórico de mensagens e mensagens que foram postadas pelo bot ou conector , mas não pode interagir com ele.

## <a name="related-topics"></a>Tópicos relacionados

[Configurações de administração para aplicativos no Teams](admin-settings.md)

[Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md)
