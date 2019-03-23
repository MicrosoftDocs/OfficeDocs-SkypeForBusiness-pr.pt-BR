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
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre as políticas de permissão do aplicativo no Microsoft Teams e como usá-los para controlar quais aplicativos estão disponíveis para usuários em sua organização.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: e88493e5ecb764f207ee0eebd9a46e68db3671cd
ms.sourcegitcommit: 5ed00e911a151d3ab834528f121db8653c25dc12
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747682"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gerenciar políticas de permissões de aplicativo no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Como um administrador, você pode usar políticas de permissão de aplicativo para controlar quais aplicativos estão disponíveis para usuários do Microsoft Teams em sua organização. Você pode permitir ou bloquear todos os aplicativos ou aplicativos específicos publicados pela Microsoft, terceiros e sua organização. Quando você bloqueia um aplicativo, os usuários não conseguem instalá-lo do repositório de app equipes.

Você gerenciar políticas de permissão do aplicativo no Centro de administração do Microsoft Teams. Você pode aplicar configurações toda a organização, use a política global de (padrão de toda a organização) e criar e atribuir políticas personalizadas para usuários individuais ou de usuários em um grupo.  

![Captura de tela da política de permissão de aplicativo](media/app-permission-policies.png)

> [!NOTE]
> Usuários em sua organização receberá automaticamente a política global, a menos que você criar e atribuir uma política personalizada. Configurações de aplicativo de toda a organização substituem a política global e quaisquer políticas personalizadas que você criar e atribuir aos usuários.

Digamos, por exemplo, que você deseja bloquear todos os aplicativos de terceiros e permitir que aplicativos específicos da Microsoft para a equipe de RH em sua organização. Você seria criar uma política personalizada denominada política de permissão do aplicativo de RH, defini-la para bloquear e permitir que os aplicativos que deseja e atribuí-la aos usuários na equipe de RH.

## <a name="manage-org-wide-app-settings"></a>Gerenciar configurações de aplicativo de toda a organização

Use as configurações de aplicativo de toda a organização para controlar quais aplicativos estão disponíveis em toda a organização. Configurações de aplicativo de toda a organização determinam o comportamento para todos os usuários e substituem quaisquer outras políticas de permissão app atribuídas aos usuários. Configurações de aplicativo de toda a organização entrarão em vigor imediatamente e você pode usá-los para controlar aplicativos mal-intencionados ou problemáticos.

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes app** > **políticas de permissão**.
2. Selecione **configurações de toda a organização**. Em seguida, você pode configurar as configurações que você deseja no painel. 
![Captura de tela das configurações de aplicativo de toda a organização](media/app-permission-policies-org-wide-settings.png)
3. Em **aplicativos de terceiros**, desativar ou ativar essas configurações para controlar o acesso aos aplicativos de terceiros:

    - **Permitir que aplicativos de terceiros em equipes**: essa opção controla se os usuários podem usar aplicativos de terceiros.
    - **Permitir que qualquer novos aplicativos de terceiros publicados no armazenamento por padrão**: esta controla se os novos aplicativos de terceiros que são publicados para o aplicativo de equipes armazenam se tornam disponíveis automaticamente nas equipes. Você só pode definir essa opção se você permitir que aplicativos de terceiros.

4. Em **aplicativos personalizados**, desativar ou ativar **Permitir a interação com aplicativos personalizados**. Esta configuração controla se os usuários podem interagir com os aplicativos personalizados (sideloaded). Tenha em mente que isso é diferente da permitindo que os usuários *carreguem* aplicativos personalizados.
5. Em **aplicativos bloqueado**, procurar e adicionar os aplicativos que você deseja bloquear em sua organização. Você pode escolher os aplicativos do catálogo de aplicativos locatário ou app store equipes.
6. Clique em **Salvar** para que as configurações de aplicativos de toda a organização entrem em vigor.

## <a name="create-a-custom-app-permission-policy"></a>Criar uma política de permissão do aplicativo personalizado

Se você deseja controlar os aplicativos que estão disponíveis para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de permissão de aplicativo personalizado. Você pode criar e atribuir separadas políticas personalizadas com base em se os aplicativos são publicados pela Microsoft,-terceiros, ou a sua organização. É importante saber que depois de criar uma política personalizada, você não pode alterá-lo se os aplicativos de terceiros são desabilitados nas configurações de toda a organização. 

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes app** > **políticas de permissão**.
2. Selecione **nova política**.
    ![Captura de tela da nova política de permissão de aplicativo](media/app-permission-policies-new-policy.png)
3. Insira um nome descritivo para a política.
4. Em **aplicativos Microsoft**, **aplicativos de terceiros**e **aplicativos de locatário**, selecione uma das seguintes opções:

    - **Permitir que todos os aplicativos**
    - **Permitir aplicativos específicos e bloquear todas as outras pessoas**
    - **Bloquear aplicativos específicos e permitir que todos os outros**
    - **Bloquear todos os aplicativos**

5. Se você selecionou **Permitir aplicativos específicos e impedir que outros usuários**, adicione os aplicativos que você deseja permitir:

    1. Selecione **Permitir aplicativos**.
    1. Pesquise os aplicativos que você deseja permitir e clique em **Adicionar**. Os resultados da pesquisa são filtrados para o fornecedor do aplicativo (**aplicativos da Microsoft**, **aplicativos de terceiros**ou **aplicativos de locatário**).
    1. Quando você tiver escolhido a lista de aplicativos, clique em **Permitir**.

6. Da mesma forma, se você selecionou **bloquear aplicativos específicos e permitir que todos os outros**, procurar e adicionar os aplicativos que você deseja bloquear.
7. Clique em **Salvar**.

## <a name="edit-an-app-permission-policy"></a>Editar uma política de permissão do aplicativo

Você pode usar o Centro de administração do Microsoft Teams para editar uma política, incluindo a política global de (padrão de toda a organização) e políticas personalizadas que você criar. 

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes app** > **políticas de permissão**.
2. Selecione a política que você deseja editar.
3. A partir daqui, faça as alterações que você deseja. Você pode gerenciar configurações com base no fornecedor do aplicativo e, em seguida, adicionar e remover aplicativos com base na configuração de permissões/bloqueios.
4. Clique em **Salvar**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Atribuir uma política de permissão do aplicativo personalizado aos usuários

Você pode usar o Centro de administração do Microsoft Teams atribuir uma política personalizada para usuários individuais ou o Skype para o módulo de PowerShell de negócios para atribuir uma política personalizada para vários usuários, como todos os usuários em um grupo de segurança ou de um grupo de distribuição.

> [!IMPORTANT]
> É recomendável usar o PowerShell somente para atribuir políticas aos usuários. Use o Centro de administração do Microsoft Teams para criar, editar e gerenciar políticas.

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a>Atribuir uma política de permissão do aplicativo personalizado para usuários individuais

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.
2. Ao lado de **políticas atribuído**, escolha **Editar**.
3. Em **política de permissão do aplicativo**, selecione a política de permissão de aplicativo que você deseja atribuir e escolha **Salvar**.

    ![App-instalação-permissão-Atribuir-policy.png](media/app-permission-policies-assign-policy.png)

Você também pode atribuir uma política de permissão de aplicativo para um ou mais usuários da seguinte maneira:

1. Vá para **o Centro de administração do Microsoft equipes** > **apps equipes** > **políticas de permissão**.
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **Gerenciar usuários**.
4. No painel de **Gerenciar usuários** , procure o usuário pelo nome de exibição ou nome de usuário, selecione o nome e selecione **Adicionar**. Repita essa etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar usuários, selecione **Salvar**.
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>Atribuir uma política de permissão do aplicativo personalizado aos usuários em um grupo

Convém atribuir uma política de permissão do aplicativo personalizado a vários usuários que você identificou. Por exemplo, convém atribuir uma política a todos os usuários em um grupo de segurança. Você pode fazer isso Estabelecendo conexão com o Azure Active Directory PowerShell para o módulo de gráfico e do Skype para o módulo de PowerShell de negócios. Para obter mais informações sobre como usar o PowerShell para gerenciar equipes, consulte [Visão geral do PowerShell equipes](teams-powershell-overview.md).

Neste exemplo, nós atribuímos uma política de permissão do aplicativo personalizado chamada HR política de permissão de aplicativo para todos os usuários no grupo Contoso Pharmaceuticals RH Project.  

> [!NOTE]
> Certificar-se de que você primeiro conecte-se para o Windows Azure Active Directory PowerShell para o módulo de gráfico e Skype para o módulo de PowerShell de negócios seguindo as etapas em [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenha o GroupObjectId do grupo específico.
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Obtenha os membros do grupo especificado.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Atribua a todos os usuários no grupo a uma política de permissão de aplicativo específico. Neste exemplo, é política de permissão do aplicativo de RH.
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
Dependendo do número de membros no grupo, este comando pode levar alguns minutos para executar.

## <a name="faq"></a>Perguntas frequentes

### <a name="working-with-app-permission-policies"></a>Como trabalhar com políticas de permissão de aplicativo

#### <a name="can-i-control-line-of-business-lob-apps"></a>Eu posso controlar a linha de aplicativos de negócios (LOB)?

Sim, você pode usar políticas de permissão de aplicativo para controlar a distribuição e a distribuição de aplicativos personalizados de (LOB).

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Como as políticas de permissão do aplicativo se relacionam apps fixados e políticas de configuração de aplicativo?

Você pode usar políticas de configuração de aplicativo em conjunto com as políticas de permissão de aplicativo. Pré-fixados apps são selecionados do conjunto de aplicativos habilitados para um usuário. Além disso, se um usuário tiver uma política de permissão de aplicativo que bloqueia um aplicativo na sua política de instalação do aplicativo, esse aplicativo não aparecerá em equipes.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a>Pode usar políticas de permissão de aplicativo para restringir o carregamento de aplicativos personalizados (também conhecido como sideloading)?

Para saber mais sobre como restringir o carregamento de aplicativos personalizados, consulte [Gerenciar políticas de aplicativo personalizado and settings in equipes](teams-custom-app-policies-and-settings.md).

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo leva para que as alterações de diretiva entrem em vigor?

Após editar a política global ou atribuir uma política aos usuários, pode demorar até 24 horas para que as alterações entrem em vigor. Configurações de aplicativo de toda a organização entrarão em vigor imediatamente.

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Bloqueio de um aplicativo se aplique aos clientes móveis de equipes?

Sim, quando você bloqueia um aplicativo, que o aplicativo seja bloqueado em todos os clientes de equipes.  

### <a name="user-experience"></a>Experiência do usuário

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>O que um experiência do usuário quando um aplicativo está bloqueado?

Os usuários não podem interagir com um aplicativo bloqueado ou seus recursos, tais bots, guias e extensões de mensagens. Em um contexto compartilhado, como o chat de uma equipe ou um grupo, bots ainda podem enviar mensagens para todos os participantes de que o contexto. As equipes indica ao usuário quando um aplicativo é bloqueado. 

Por exemplo, quando um aplicativo for bloqueado, os usuários não podem fazer qualquer um dos seguintes procedimentos:

- Adicionar o aplicativo pessoalmente ou para um bate-papo ou da equipe
- Enviar mensagens para bot do aplicativo
- Executar as ações de botão que enviar informações de volta para o aplicativo, como mensagens acionáveis  
- Exibir a guia do aplicativo
- Configurar conectores para receber notificações
- Use a extensão de mensagens do aplicativo

 ## <a name="related-topics"></a>Tópicos relacionados
- [Configurações de administração para aplicativos no Teams](admin-settings.md)
- [Gerenciar políticas de configuração de aplicativo em equipes](teams-app-setup-policies.md)
- [Gerenciar políticas de aplicativo personalizado e configurações no equipes](teams-custom-app-policies-and-settings.md)
