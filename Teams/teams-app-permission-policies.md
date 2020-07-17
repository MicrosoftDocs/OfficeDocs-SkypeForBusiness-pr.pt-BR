---
title: Gerenciar políticas de permissões de aplicativo no Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Saiba mais sobre as políticas de permissão do aplicativo no Microsoft Teams e como usá-las para controlar quais aplicativos estão disponíveis para os usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 15698c7eeb12187ccc510a42b9a6e2120a7907cc
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042983"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gerenciar políticas de permissões de aplicativo no Microsoft Teams

Como administrador, você pode usar as políticas de permissão do aplicativo para controlar quais aplicativos estarão disponíveis para os usuários do Microsoft Teams em sua organização. Você pode permitir ou bloquear todos os aplicativos ou aplicativos específicos publicados pela Microsoft, por terceiros e pela sua organização. Ao bloquear um aplicativo, os usuários que têm a política não conseguem instalá-lo da loja de aplicativos do Teams. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

Você gerencia políticas de permissão do aplicativo no centro de administração do Microsoft Teams. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Depois de editar ou atribuir uma política, pode demorar algumas horas para que as alterações entrem em vigor.

![Captura de tela da política de permissão do aplicativo](media/app-permission-policies.png)

> [!NOTE]
> As configurações de aplicativo de toda a organização substituem a política global e quaisquer políticas personalizadas que você criar e atribuir aos usuários.

Se sua organização já estiver no Teams, as configurações do aplicativo definidas em **configurações de todo o locatário** no centro de administração do Microsoft 365 serão refletidas nas configurações de aplicativo de toda a organização na página [gerenciar aplicativos](manage-apps.md) . Se você não tem experiência com o Microsoft Teams e simplesmente introdução, por padrão, todos os aplicativos são permitidos na política global. Isso inclui aplicativos publicados pela Microsoft, por terceiros e por sua organização.

Digamos, por exemplo, que você queira bloquear todos os aplicativos de terceiros e permitir que aplicativos específicos da Microsoft para a equipe de RH em sua organização. Primeiro, você vai para a página [gerenciar aplicativos](manage-apps.md) e verificar se os aplicativos que você deseja permitir para a equipe de RH são permitidos no nível da organização. Em seguida, crie uma política personalizada chamada política de permissão de aplicativo de RH, defina-a para bloquear e permitir os aplicativos desejados e atribuí-la a usuários na equipe de RH.

> [!NOTE]
> Se você implantou o Microsoft Teams em um ambiente da Comunidade do governo Microsoft 365, consulte [gerenciar configurações de aplicativo de toda a organização para o governo da microsoft 365](#manage-org-wide-app-settings-for-microsoft-365-government) para saber mais sobre as configurações de aplicativo de terceiros exclusivas para gcc.

## <a name="create-a-custom-app-permission-policy"></a>Criar uma política de permissão de aplicativo personalizada

Se você quiser controlar os aplicativos que estão disponíveis para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de permissão de aplicativo personalizadas. Você pode criar e atribuir políticas personalizadas separadas com base em aplicativos que são publicados pela Microsoft, por terceiros ou por sua organização. É importante saber que, após criar uma política personalizada, você não poderá alterá-la se os aplicativos de terceiros estiverem desabilitados nas configurações de aplicativo de toda a organização.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de permissão de **aplicativos do teams**  >  **Permission policies**.
2. Clique em **Adicionar**. <br>
    ![Captura de tela da política de permissão de novo aplicativo](media/app-permission-policies-new-policy.png)
3. Insira um nome e uma descrição para a política.
4. Em **aplicativos da Microsoft**, **aplicativos de terceiros**e **aplicativos personalizados**, selecione uma das seguintes opções:

    - **Permitir todos os aplicativos**
    - **Permitir aplicativos específicos e bloquear todos os outros**
    - **Bloquear aplicativos específicos e permitir todos os outros**
    - **Bloquear todos os aplicativos**

5. Se você selecionou **permitir aplicativos específicos e bloquear outras pessoas**, adicione os aplicativos que deseja permitir:

    1. Selecione **permitir aplicativos**.
    1. Procure os aplicativos que você deseja permitir e, em seguida, clique em **Adicionar**. Os resultados da pesquisa são filtrados para o fornecedor do aplicativo (**aplicativos da Microsoft**, **aplicativos**de terceiros ou **aplicativos personalizados**).
    1. Quando tiver escolhido a lista de aplicativos, clique em **permitir**. 

6. Da mesma forma, se você selecionou **bloquear aplicativos específicos e permitir todos os outros**, procure e adicione os aplicativos que deseja bloquear e, em seguida, clique em **Bloquear**.
7. Clique em **Salvar**.

## <a name="edit-an-app-permission-policy"></a>Editar uma política de permissão do aplicativo

Você pode usar o centro de administração do Microsoft Teams para editar uma política, incluindo a política global e políticas personalizadas criadas por você.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de permissão de **aplicativos do teams**  >  **Permission policies**.
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Aqui, faça as alterações desejadas. Você pode gerenciar as configurações com base no editor do aplicativo e adicionar e remover aplicativos com base na configuração permitir/bloquear.
4. Clique em **Salvar**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Atribuir uma política de permissão de aplicativo personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Gerenciar configurações de aplicativo de toda a organização para o governo Microsoft 365  

Em uma implantação do Microsoft 365 governo-GCC do Teams, é importante saber o seguinte sobre as configurações do aplicativo de terceiros, que são exclusivas do GCC.

Em GCC, todos os aplicativos de terceiros são bloqueados por padrão. Além disso, você verá a observação a seguir sobre o gerenciamento de aplicativos de terceiros na página de políticas de permissão do aplicativo no centro de administração do Microsoft Teams.

![Captura de tela da política de permissão do aplicativo em GCC](media/app-permission-policies-gcc.png)

Use as configurações de aplicativo de toda a organização para controlar se os usuários podem instalar aplicativos de terceiros. As configurações de aplicativo de toda a organização governam o comportamento para todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Você pode usá-los para controlar aplicativos mal-intencionados ou problemáticos.

1. Na página **políticas de permissão** , selecione **configurações de aplicativo de toda a organização**. Em seguida, você pode definir as configurações desejadas no painel.

    ![Captura de tela das configurações de aplicativo de toda a organização](media/app-permission-policies-gcc-org-wide.png)
    
2. Em **aplicativos de terceiros**, desative ou ative essas configurações para controlar o acesso a aplicativos de terceiros:

    - **Permitir aplicativos de terceiros**: isso controla se os usuários podem usar aplicativos de terceiros. Se você desabilitar essa configuração, os usuários não poderão instalar ou usar aplicativos de terceiros. Em uma implantação do Microsoft 365 governo-GCC do Teams, essa configuração está desativada por padrão.
    - **Permitir que todos os novos aplicativos de terceiros publicados na loja por padrão**: controlam se novos aplicativos de terceiros publicados na App App Store se tornam disponíveis automaticamente no Teams. Você só pode definir esta opção se permitir aplicativos de terceiros.

3. Em **aplicativos bloqueados**, adicione os aplicativos que você deseja bloquear em toda a organização. Em uma implantação do Microsoft 365 governo-GCC do Teams, todos os aplicativos de terceiros são adicionados a essa lista por padrão. Para qualquer aplicativo de terceiros que você deseja permitir em sua organização, remova o aplicativo desta lista de aplicativos bloqueados. Quando você bloqueia um aplicativo em toda a organização, o aplicativo é bloqueado automaticamente para todos os seus usuários, independentemente de ser permitido em qualquer política de permissão do aplicativo
4. Clique em **salvar** para que as configurações de aplicativo de toda a organização entrem em vigor.

Conforme mencionado anteriormente, para permitir aplicativos de terceiros, você pode editar e usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas.

## <a name="faq"></a>Perguntas frequentes

### <a name="working-with-app-permission-policies"></a>Trabalhando com políticas de permissão do aplicativo

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Quais interações de aplicativo as políticas de permissão afetam?
Políticas de permissão controlam o uso do aplicativo controlando a instalação, descoberta e interação para os usuários finais. Os administradores ainda podem gerenciar aplicativos no centro de administração do Microsoft Teams independentemente das políticas de permissão atribuídas a eles.

#### <a name="can-i-control-line-of-business-lob-apps"></a>Posso controlar os aplicativos de linha de negócios (LOB)?
Sim, você pode usar políticas de permissão do aplicativo para controlar a distribuição e distribuição de aplicativos personalizados (LOB). Você pode criar uma política personalizada ou editar a política global para permitir ou bloquear aplicativos personalizados com base nas necessidades da sua organização.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Como as políticas de permissão do aplicativo se relacionam a aplicativos fixos e políticas de configuração de aplicativos?

Você pode usar as políticas de configuração do aplicativo em conjunto com políticas de permissão do aplicativo. Aplicativos pré-projetados são selecionados do conjunto de aplicativos habilitados para um usuário. Além disso, se um usuário tiver uma política de permissão do aplicativo que bloqueie um aplicativo na política de configuração do aplicativo, esse aplicativo não aparecerá no Microsoft Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>Posso usar políticas de permissão do aplicativo para restringir o upload de aplicativos personalizados?

Você pode usar as configurações de toda a organização na página **gerenciar aplicativos** ou políticas de configuração do aplicativo para restringir o carregamento de aplicativos personalizados para a sua organização.  

Para impedir que usuários específicos carreguem aplicativos personalizados, use políticas de aplicativo personalizadas. Para saber mais, consulte [gerenciar políticas e configurações personalizadas do aplicativo no Microsoft Teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Bloquear um aplicativo se aplica a clientes móveis do Microsoft Teams?

Sim, quando você bloqueia um aplicativo, esse aplicativo é bloqueado em todos os clientes do teams.  

### <a name="user-experience"></a>Experiência do usuário

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>O que uma experiência do usuário quando um aplicativo está bloqueado?

Os usuários não podem interagir com um aplicativo bloqueado ou com seus recursos, tais como bots, guias e extensões de mensagens. Em um contexto compartilhado, como uma equipe ou um chat em grupo, os bots ainda podem enviar mensagens para todos os participantes desse contexto. Teams indica ao usuário quando um aplicativo é bloqueado.

Por exemplo, quando um aplicativo é bloqueado, os usuários não podem fazer nenhum dos seguintes procedimentos:

- Adicionar o aplicativo pessoalmente ou a um chat ou a uma equipe
- Enviar mensagens ao bot do aplicativo
- Executar ações de botão que enviam informações de volta para o aplicativo, como mensagens acionáveis  
- Exibir a guia do aplicativo
- Configurar conectores para receber notificações
- Usar a extensão de mensagens do aplicativo

O portal herdado permitia o controle de aplicativos no nível da organização, o que significa que, quando um aplicativo é bloqueado, ele fica bloqueado para todos os usuários da organização. Bloquear um aplicativo na página [gerenciar aplicativos](manage-apps.md) funciona exatamente da mesma maneira.

Para políticas de permissão de aplicativo atribuídas a usuários específicos, se um aplicativo com recurso de bot ou conector era permitido e bloqueado, e se o aplicativo for permitido somente para alguns usuários em um contexto compartilhado, os membros de um chat em grupo ou canal que não têm permissão para esse aplicativo poderão ver o histórico de mensagens e as mensagens que foram lançadas pelo bot ou pelo conector , mas não é possível interagir com ele.

## <a name="related-topics"></a>Tópicos relacionados

[Configurações de administração para aplicativos no Teams](admin-settings.md)

[Atribuir políticas a seus usuários no Teams](assign-policies.md)
