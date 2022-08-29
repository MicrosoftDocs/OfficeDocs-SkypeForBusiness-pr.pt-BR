---
title: Gerenciar políticas de permissão de aplicativos no Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Saiba mais sobre as políticas de permissão de aplicativo no Microsoft Teams e como controlar a disponibilidade de aplicativos para seus usuários finais.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: e82dbc8ad122e3d427b86a52c39a10f89df88098
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396832"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gerenciar políticas de permissão de aplicativos no Microsoft Teams

Como administrador, você pode usar políticas de permissão de aplicativo para controlar quais aplicativos estão disponíveis para usuários do Microsoft Teams em sua organização. Você pode permitir ou bloquear todos os aplicativos ou aplicativos específicos publicados pela Microsoft, terceiros e sua organização. Ao bloquear um aplicativo, os usuários que têm a política não conseguem instalá-lo da loja de aplicativos do Teams. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

Você gerencia políticas de permissão de aplicativo no centro de administração do Microsoft Teams. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

![Captura de tela da política de permissão do aplicativo.](media/app-permission-policies.png)

> [!NOTE]
> As configurações do aplicativo em toda a organização substituem a política global e quaisquer políticas personalizadas que você cria e atribui aos usuários.

Se sua organização já estiver no Teams, as configurações do aplicativo definidas em **Configurações para todo o locatário** no Centro de administração do Microsoft 365 são refletidas nas configurações do aplicativo para toda a organização na página [Gerenciar aplicativos](manage-apps.md). Se você é novo no Teams e está apenas começando, por padrão, todos os aplicativos são permitidos na política global. Isso inclui aplicativos publicados pela Microsoft, provedores de software de terceiros e sua organização.

Digamos, por exemplo, que você deseja permitir apenas alguns aplicativos específicos para a equipe de RH em sua organização. Primeiro, na página [Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps), certifique-se de que os aplicativos que deseja permitir para a equipe de RH são permitidos no nível da organização. Em seguida, crie uma política personalizada, defina-a para bloquear e permitir os aplicativos desejados e atribua a política aos usuários da equipe de RH.

> [!NOTE]
> Para saber mais sobre as configurações de aplicativo de terceiros que são exclusivas do ambiente de GCCH (Nuvem da Comunidade Governamental – Alta) e DoD (Departamento de Defesa) do Microsoft 365, confira [Gerenciar configurações de aplicativo em toda a organização para o Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government).

## <a name="create-a-custom-app-permission-policy"></a>Criar uma política de permissão de aplicativo personalizada

Use uma ou mais políticas de permissão de aplicativo personalizadas, se você quiser controlar os aplicativos que estão disponíveis para diferentes grupos de usuários. Você pode criar e atribuir políticas personalizadas separadas com base no fato de os aplicativos serem publicados pela Microsoft, por terceiros ou pela sua organização. Depois de criar uma política personalizada, você não pode alterá-la se os aplicativos de terceiros estiverem desabilitados nas configurações de aplicativos de toda a organização.

1. Entre no centro de administração do Teams e acesse as políticas **de permissão de aplicativos** > **[do](https://admin.teams.microsoft.com/policies/app-permission)** Teams.
1. Selecione **Adicionar**.

   ![Captura de tela da nova política de permissão do aplicativo.](media/app-permission-policies-new-policy.png)

1. Forneça um nome e uma descrição para a política.
1. Em **Aplicativos da Microsoft**, **Aplicativos de terceiros** e **Aplicativos personalizados**, selecione um dos seguintes:

    * Permitir todos os aplicativos
    * Permita aplicativos específicos e bloqueie todos os outros
    * Bloquear aplicativos específicos e permita todos os outros
    * Bloquear todos os aplicativos

1. Se você selecionou **Permitir aplicativos específicos e bloquear todos os outros**, adicione os aplicativos que deseja permitir:

    1. Selecione **Permitir aplicativos**.
    1. Pesquise os aplicativos que você deseja permitir e selecione **Adicionar**. Os resultados da pesquisa são filtrados para o desenvolvedor de aplicativos (**aplicativos da Microsoft**, **aplicativos de terceiros** ou **aplicativos personalizados**).
    1. Depois de escolher a lista de aplicativos, selecione **Permitir**.

1. Da mesma forma, se você selecionou **Bloquear aplicativos específicos e permitir todos os outros**, pesquise e adicione os aplicativos que deseja bloquear e, em seguida, selecione **Bloquear**.
1. Selecione **Salvar**.

## <a name="edit-an-app-permission-policy"></a>Editar uma política de permissão de aplicativo

Você pode usar o centro de administração do Teams para editar uma política, incluindo a política global e as políticas personalizadas que você criar.

1. Entre no centro de administração do Teams e acesse as políticas **de permissão de aplicativos** > **[do](https://admin.teams.microsoft.com/policies/app-permission)** Teams.
1. Escolha a política clicando à esquerda do nome da política e selecionando **Editar**.
1. A partir daqui, faça as alterações desejadas. Você pode gerenciar as configurações com base no desenvolvedor do aplicativo, bem como adicionar e remover aplicativos com base na configuração de permissão/bloqueio.
1. Selecione **Salvar**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Atribuir uma política de permissão de aplicativo personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Gerenciar configurações de aplicativos em toda a organização para o Microsoft 365 Government  

Em uma implantação do Microsoft 365 Government – GCC, GCCH e DoD, todos os aplicativos de terceiros são bloqueados por padrão. Os aplicativos de terceiros não estão disponíveis para nuvens GCCH e DOD. Além disso, na GCC, você verá a seguinte observação sobre o gerenciamento de aplicativos de terceiros na página de políticas de permissão de aplicativos no centro de administração do Microsoft Teams.

:::image type="content" source="media/app-permission-policies-gcc.png" alt-text="Captura de tela da política de permissão do aplicativo na GCCH e no DoD.":::

Use as configurações de aplicativos de toda a organização para controlar se os usuários podem instalar aplicativos de terceiros. As configurações de aplicativo em toda a organização controlam o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários.

<!---
1. On the **Permission policies** page, select **Org-wide app settings**. You can then configure the settings you want in the panel. --->

### <a name="for-gcc-clouds"></a>Para nuvens GCC

1. Na página **Gerenciar aplicativos do Teams Apps** > , selecione **configurações de aplicativos em toda a organização**.**[](https://admin.teams.microsoft.com/policies/manage-apps)** Você pode então definir as configurações desejadas no painel.

   ![Captura de tela das configurações do aplicativo em toda a organização na GCC.](media/app-permission-policies-gcc-org-wide.png)

1. Em **Aplicativos de terceiros**, desabilite ou ative essas configurações para controlar o acesso a aplicativos de terceiros:

    * **Permitir aplicativos de terceiros**: essa opção controla se os usuários podem usar aplicativos de terceiros. Se você desabilitar esta configuração, seus usuários não poderão instalar ou usar aplicativos de terceiros. Em uma implantação do Microsoft 365 Government – GCC e DoD no Teams, essa configuração está desativada por padrão.
    * **Permitir novos aplicativos de terceiros publicados na loja por padrão**: essa opção controla se os novos aplicativos de terceiros publicados na loja de aplicativos do Teams se tornam automaticamente disponíveis no Teams. Você só pode definir essa opção se permitir aplicativos de terceiros.

1. Em **Aplicativos bloqueados**, adicione os aplicativos que deseja bloquear em sua organização. Em uma implantação do Microsoft 365 Government – GCCH e DoD do Teams, todos os aplicativos de terceiros são adicionados a esta lista por padrão. Para qualquer aplicativo de terceiros que você deseja permitir em sua organização, remova o aplicativo desta lista de aplicativos bloqueados. Quando você bloqueia um aplicativo em toda a organização, o aplicativo é automaticamente bloqueado para todos os seus usuários, independentemente de ser permitido em qualquer política de permissão de aplicativo.

1. Selecione **Salvar** para que as configurações do aplicativo em toda a organização entrem em vigor.

Para permitir aplicativos de terceiros, edite e use a política global (padrão em toda a organização) ou crie e atribua políticas personalizadas.

### <a name="for-gcch-and-dod-clouds"></a>Para nuvens GCCH e DoD

1. Entre no centro de administração do Teams e acesse as políticas **de permissão de aplicativos** > **[do](https://admin.teams.microsoft.com/policies/app-permission)** Teams.

1. Selecione **configurações de aplicativo em toda a organização**. Em **Aplicativos bloqueados**, adicione os aplicativos que deseja bloquear em sua organização. Em uma implantação do Microsoft 365 Government – GCCH e DoD do Teams, todos os aplicativos de terceiros são adicionados a esta lista por padrão. Quando você bloqueia um aplicativo em toda a organização, o aplicativo é automaticamente bloqueado para todos os seus usuários, independentemente de ser permitido em qualquer política de permissão de aplicativo.

   :::image type="content" source="media/app-permission-policies-gcch-dod-org-wide.png" alt-text="Captura de tela das configurações de aplicativo em toda a organização na GCCH e no DoD.":::

1. Selecione **Salvar** para que as configurações do aplicativo em toda a organização entrem em vigor.

## <a name="faq"></a>Perguntas frequentes

### <a name="work-with-app-permission-policies"></a>Trabalhar com políticas de permissão de aplicativo

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Quais interações de aplicativos as políticas de permissão afetam?

As políticas de permissão regem o uso do aplicativo, controlando a instalação, descoberta e interação para usuários finais. Os administradores ainda podem gerenciar aplicativos no centro de administração do Microsoft Teams, independentemente das políticas de permissão atribuídas a eles.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Como as políticas de permissão de aplicativo se relacionam a aplicativos fixados e políticas de configuração de aplicativo?

Você pode usar políticas de configuração de aplicativo junto com políticas de permissão de aplicativo. Os aplicativos pré-fixados são selecionados do conjunto de aplicativos habilitados para um usuário. Além disso, se um usuário tiver uma política de permissão de aplicativo que bloqueia um aplicativo em sua política de configuração de aplicativo, esse aplicativo não aparecerá no Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>Posso usar políticas de permissão de aplicativo para restringir o upload de aplicativos personalizados?

Você pode usar as configurações de toda a organização na página **Gerenciar aplicativos** ou políticas de configuração de aplicativos para restringir o upload de aplicativos personalizados para sua organização.  

Para impedir que usuários específicos carreguem aplicativos personalizados, use políticas de aplicativos personalizados. Para saber mais, confira [Gerenciar políticas e configurações de aplicativos personalizados no Teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>O bloqueio de um aplicativo se aplica a clientes móveis do Teams?

Sim, quando você bloqueia um aplicativo, ele é bloqueado em todos os clientes do Teams.  

### <a name="user-experience"></a>Experiência de usuário

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>O que o usuário sente quando um aplicativo é bloqueado?

Os usuários não podem interagir com um aplicativo bloqueado ou seus recursos, como bots, guias e extensões de mensagens. Em um contexto compartilhado, como uma equipe ou chat em grupo, os bots ainda podem enviar mensagens a todos os participantes desse contexto. O Teams indica ao usuário quando um aplicativo é bloqueado.

Por exemplo, quando um aplicativo é bloqueado, os usuários não podem realizar nenhuma das seguintes tarefas:

* Adicionar o aplicativo pessoalmente ou em um chat ou equipe
* Enviar mensagens para o bot do aplicativo
* Execute ações de botão que enviam informações de volta ao aplicativo, como mensagens acionáveis  
* Exibir a guia do aplicativo
* Configurar conectores para receber notificações
* Usar a extensão de mensagens do aplicativo

O portal legado permitia controlar aplicativos no nível da organização, o que significa que quando um aplicativo é bloqueado, ele é bloqueado para todos os usuários da organização. O bloqueio de um aplicativo na página [Gerenciar aplicativos](manage-apps.md) funciona exatamente da mesma maneira.

Para políticas de permissão de aplicativo atribuídas a usuários específicos, se um aplicativo com recurso de bot ou conector foi permitido e depois bloqueado, e se o aplicativo foi permitido apenas para alguns usuários em um contexto compartilhado, membros de um chat em grupo ou canal que não tem permissão para que o aplicativo possa ver o histórico de mensagens e as mensagens postadas pelo bot ou conector, mas não pode interagir com ele.

## <a name="see-also"></a>Confira também

* [Configurações de administrador para aplicativos no Teams](admin-settings.md)
* [Atribua políticas a seus usuários no Teams](policy-assignment-overview.md)
* [Comparação de disponibilidade de recursos do Teams](/office365/servicedescriptions/teams-service-description#feature-availability)
