---
title: Gerenciar políticas de permissões de aplicativo no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre as políticas de permissão do aplicativo no Microsoft Teams e como usá-las para controlar quais aplicativos estão disponíveis para os usuários em sua organização.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: fac559fb492155af9953beb74c2fac1526f01432
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681917"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gerenciar políticas de permissões de aplicativo no Microsoft Teams

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

> [!NOTE]
> Para obter o método atual de gerenciamento de aplicativos no Microsoft Teams, consulte [gerenciar as configurações do Microsoft Teams para sua organização](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).

Como administrador, você pode usar políticas de permissão do aplicativo para controlar quais aplicativos estão disponíveis para os usuários do Microsoft Teams em sua organização. Você pode permitir ou bloquear todos os aplicativos ou aplicativos específicos publicados pela Microsoft, por terceiros e pela sua organização. Quando você bloqueia um aplicativo, os usuários não podem instalá-lo na App Store do teams.

Você gerencia políticas de permissão do aplicativo no centro de administração do Microsoft Teams. Você pode aplicar as configurações de toda a organização, usar a política global (padrão para toda a organização) e criar e atribuir políticas personalizadas a usuários ou usuários individuais em um grupo.  

![Captura de tela da política de permissão do aplicativo](media/app-permission-policies.png)

> [!NOTE]
> Os usuários em sua organização receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. As configurações de aplicativo de toda a organização substituem a política global e quaisquer políticas personalizadas que você criar e atribuir aos usuários.

Digamos, por exemplo, que você queira bloquear todos os aplicativos de terceiros e permitir que aplicativos específicos da Microsoft para a equipe de RH em sua organização. Você criaria uma política personalizada denominada política de permissão do aplicativo HR, defini-la para bloquear e permitir os aplicativos desejados e, em seguida, atribuí-la aos usuários na equipe de RH.

## <a name="manage-org-wide-app-settings"></a>Gerenciar configurações de aplicativo de toda a organização

Use as configurações de aplicativo de toda a organização para controlar quais aplicativos estão disponíveis em sua organização. As configurações de aplicativo de toda a organização governam o comportamento para todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. As configurações de aplicativo de toda a organização entram em vigor imediatamente e você pode usá-las para controlar aplicativos mal-intencionados ou problemáticos.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de permissão**do **aplicativo** > Teams.
2. Selecione **configurações de toda a organização**. Em seguida, você pode definir as configurações desejadas no painel. 
![Captura de tela das configurações do aplicativo de toda a organização](media/app-permission-policies-org-wide-settings.png)
3. Em **aplicativos de terceiros**, desative ou ative essas configurações para controlar o acesso a aplicativos de terceiros:

    - **Permitir aplicativos de terceiros no Teams**: controla se os usuários podem usar aplicativos de terceiros.
    - **Permitir que todos os novos aplicativos de terceiros publicados na loja por padrão**: controlam se novos aplicativos de terceiros publicados na App App Store se tornam disponíveis automaticamente no Teams. Você só pode definir esta opção se permitir aplicativos de terceiros.

4. Em **aplicativos personalizados**, desative ou ative **permitir interação com aplicativos personalizados**. Esta configuração controla se os usuários podem interagir com aplicativos personalizados (Sideload). Tenha em mente que isso é diferente de permitir que os ** usuários carreguem aplicativos personalizados.
5. Em **aplicativos bloqueados**, procure e adicione os aplicativos que você deseja bloquear em toda a organização. Você pode escolher os aplicativos do catálogo de aplicativos do locatário ou da App Team Store.
6. Clique em **salvar** para que as configurações de aplicativo de toda a organização entrem em vigor.

## <a name="create-a-custom-app-permission-policy"></a>Criar uma política de permissão de aplicativo personalizada

Se você quiser controlar os aplicativos que estão disponíveis para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de permissão de aplicativo personalizadas. Você pode criar e atribuir políticas personalizadas separadas com base em aplicativos que são publicados pela Microsoft, por terceiros ou por sua organização. É importante saber que, após a criação de uma política personalizada, você não poderá alterá-la se os aplicativos de terceiros estiverem desabilitados nas configurações de toda a organização. 

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de permissão**do **aplicativo** > Teams.
2. Selecione **nova política**.
    ![Captura de tela da política de permissão de novo aplicativo](media/app-permission-policies-new-policy.png)
3. Digite um nome descritivo para a política.
4. Em **aplicativos da Microsoft**, **aplicativos de terceiros**e **aplicativos**de locatários, selecione uma das seguintes opções:

    - **Permitir todos os aplicativos**
    - **Permitir aplicativos específicos e bloquear todos os outros**
    - **Bloquear aplicativos específicos e permitir todos os outros**
    - **Bloquear todos os aplicativos**

5. Se você selecionou **permitir aplicativos específicos e bloquear outras pessoas**, adicione os aplicativos que deseja permitir:

    1. Selecione **permitir aplicativos**.
    1. Procure os aplicativos que você deseja permitir e, em seguida, clique em **Adicionar**. Os resultados da pesquisa são filtrados para o fornecedor do aplicativo (**aplicativos da Microsoft**, **aplicativos**de terceiros ou **aplicativos locatários**).
    1. Quando tiver escolhido a lista de aplicativos, clique em **permitir**.

6. Da mesma forma, se você selecionou **bloquear aplicativos específicos e permitir todos os outros**, procure e adicione os aplicativos que deseja bloquear.
7. Clique em **Salvar**.

## <a name="edit-an-app-permission-policy"></a>Editar uma política de permissão do aplicativo

Você pode usar o centro de administração do Microsoft Teams para editar uma política, incluindo a política global (padrão de toda a organização) e políticas personalizadas que você criar. 

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de permissão**do **aplicativo** > Teams.
2. Selecione a política que você deseja editar.
3. Aqui, faça as alterações desejadas. Você pode gerenciar as configurações com base no editor do aplicativo e adicionar e remover aplicativos com base na configuração permitir/bloquear.
4. Clique em **Salvar**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Atribuir uma política de permissão de aplicativo personalizada aos usuários

Você pode usar o centro de administração do Microsoft Teams para atribuir uma política personalizada a usuários individuais ou o módulo do PowerShell do Skype for Business para atribuir uma política personalizada a vários usuários, como todos os usuários de um grupo de segurança ou grupo de distribuição.

> [!IMPORTANT]
> Recomendamos usar o PowerShell somente para atribuir políticas a usuários. Use o centro de administração do Microsoft Teams para criar, editar e gerenciar políticas.

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a>Atribuir uma política de permissão de aplicativo personalizada a usuários individuais

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.
2. Ao lado de **políticas atribuídas**, escolha **Editar**.
3. Em **política de permissão do aplicativo**, selecione a política de permissão do aplicativo que você deseja atribuir e, em seguida, escolha **salvar**.

    ![App-setup-Permission-Assign-Policy. png](media/app-permission-policies-assign-policy.png)

Você também pode atribuir uma política de permissão do aplicativo a um ou mais usuários da seguinte maneira:

1. Vá para**políticas de permissão**de**aplicativos** >  **do centro** > de administração do Microsoft Teams.
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **gerenciar usuários**.
4. No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e, em seguida, selecione **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar usuários, selecione **salvar**.
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>Atribuir uma política de permissão de aplicativo personalizada a usuários em um grupo

Você pode querer atribuir uma política de permissão de aplicativo personalizada a vários usuários que você já tenha identificado. Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança. Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business. Para obter mais informações sobre como usar o PowerShell para gerenciar o Microsoft Teams, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).

Neste exemplo, atribuímos uma política de permissão de aplicativo personalizada chamada política de permissão do aplicativo HR a todos os usuários do grupo de projetos de RH da Contoso Pharmaceuticals.  

> [!NOTE]
> Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenha o GroupObjectId do grupo específico.
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Obter os membros do grupo especificado.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Atribua todos os usuários do grupo a uma política de permissão de aplicativo específica. Neste exemplo, a política de permissão do aplicativo em RH.
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.

## <a name="faq"></a>Perguntas frequentes

### <a name="working-with-app-permission-policies"></a>Trabalhando com políticas de permissão do aplicativo

#### <a name="can-i-control-line-of-business-lob-apps"></a>Posso controlar os aplicativos de linha de negócios (LOB)?

Sim, você pode usar políticas de permissão do aplicativo para controlar a distribuição e distribuição de aplicativos personalizados (LOB).

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Como as políticas de permissão do aplicativo se relacionam a aplicativos fixos e políticas de configuração de aplicativos?

Você pode usar as políticas de configuração do aplicativo em conjunto com políticas de permissão do aplicativo. Aplicativos pré-projetados são selecionados do conjunto de aplicativos habilitados para um usuário. Além disso, se um usuário tiver uma política de permissão do aplicativo que bloqueie um aplicativo na política de configuração do aplicativo, esse aplicativo não aparecerá no Microsoft Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a>Posso usar políticas de permissão do aplicativo para restringir o upload de aplicativos personalizados (também conhecidos como Sideload)?

Para saber mais sobre como restringir o upload de aplicativos personalizados, consulte [gerenciar configurações e políticas personalizadas do aplicativo no](teams-custom-app-policies-and-settings.md)Microsoft Teams.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo leva para as alterações de política entrarem em vigor?

Depois de editar a política global ou atribuir uma política aos usuários, pode levar até 24 horas para que as alterações entrem em vigor. As configurações de aplicativo de toda a organização entram em vigor imediatamente.

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

 ## <a name="related-topics"></a>Tópicos relacionados
- [Configurações de administração para aplicativos no Teams](admin-settings.md)
- [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
- [Gerenciar políticas de aplicativo personalizado e as configurações no Teams](teams-custom-app-policies-and-settings.md)
