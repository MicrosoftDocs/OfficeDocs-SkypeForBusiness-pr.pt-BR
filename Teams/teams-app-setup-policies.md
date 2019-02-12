---
title: Gerenciar políticas de configuração de aplicativo no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 2/11/2019
ms.reviewer: larryjin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre as políticas de configuração de aplicativo no Microsoft Teams e como usá-los para aplicativos de pin para personalizar as equipes para usuários em sua organização.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fe6281015072858c959a65a6cd17ed157db0afa9
ms.sourcegitcommit: f5f1437ec72f67f6804ca8d785f76059d0979e39
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2019
ms.locfileid: "29894244"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gerenciar políticas de configuração de aplicativo no Microsoft Teams

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Como um administrador, você pode usar políticas de configuração de aplicativo para personalizar o Microsoft Teams para destacar os aplicativos que são mais importantes para seus usuários. Você escolher os aplicativos para fixar e definir a ordem em que aparecem. Políticas de configuração de aplicativo permitem que você demonstrem aplicativos que precisam de usuários em sua organização, incluindo aquelas criadas por terceiros ou por desenvolvedores em sua organização. Você também pode usar políticas de configuração de aplicativo para gerenciar recursos internos como aparecem.

Aplicativos são fixados a barra de aplicativos. Esta é a barra na lateral direita do cliente de desktop equipes e na parte inferior dos clientes móveis equipes (iOS e Android). 

|Cliente de desktop de equipes  |Cliente móvel de equipes |
|---------|---------|
|![App-Setup-Policies-Desktop-App-Bar.PNG](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![App-Setup-Policies-Mobile-App-Bar.PNG](media/app-setup-policies-mobile-app-bar.png)      |

Você gerenciar políticas de configuração de aplicativo no Centro de administração do Microsoft Teams. Você pode usar a política global de (padrão de toda a organização) ou como criar políticas personalizadas e atribuí-las aos usuários. Usuários em sua organização receberá automaticamente a política global, a menos que você criar e atribuir uma política personalizada.

Você pode editar as configurações na política global para incluir os aplicativos que você deseja. Se você desejar personalizar equipes para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas.

![instalação-App-policies.png](media/app-setup-policies.png)

> [!NOTE]
> Se um usuário é atribuído a uma política personalizada, essa política se aplica ao usuário. Se um usuário não for atribuído a uma política personalizada, a política global se aplica ao usuário.

## <a name="create-a-custom-app-setup-policy"></a>Criar uma política de instalação do aplicativo personalizado

Você pode usar o Centro de administração do Microsoft Teams ou o Windows PowerShell para criar uma política personalizada.

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes app** > **políticas de configuração de aplicativo**.
2. Selecione **nova política**.
3. Insira um nome descritivo para a política e, em seguida, clique em **Adicionar aplicativos**.
4. No painel **Adicionar fixados apps** , pesquise os aplicativos que você deseja adicionar e, em seguida, clique em **Adicionar**.  Para ver uma lista de todos os aplicativos, selecione **armazenar equipes app**. Quando você tiver escolhido sua lista de aplicativos, clique em **Adicionar**.

     ![App-instalação-políticas-adicionar-apps.png](media/app-setup-policies-add-apps.png)

5. Organize os aplicativos na ordem que você deseja que eles aparecem em equipes e clique em **Salvar**.

    ![App-Setup-Policies-New-Policy-Setup.PNG](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Editar uma política de instalação de aplicativo

Você pode usar o Centro de administração do Microsoft Teams ou o Windows PowerShell para editar uma política, incluindo a política global de (padrão de toda a organização) e políticas personalizadas que você criar. 

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes app** > **políticas de configuração de aplicativo**.
2. Selecione a política que você deseja editar. 
3. A partir daqui, faça as alterações que você deseja. Você pode adicionar, remover e alterar a ordem dos aplicativos.
4. Clique em **Salvar**. 

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Atribuir uma política de instalação do aplicativo personalizado aos usuários

Você pode usar o Centro de administração do Microsoft Teams para atribuir uma política personalizada para usuários individuais ou o Windows PowerShell para atribuir uma política personalizada para grupos de usuários, como um grupo de segurança ou grupo de distribuição.

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a>Atribuir uma política de instalação do aplicativo personalizado para usuários individuais

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.
2. Ao lado de **políticas atribuído**, escolha **Editar**.
3. Em **política de instalação do aplicativo de equipes**, selecione a política de instalação do aplicativo que deseja atribuir e escolha **Salvar**.

    ![App-instalação-políticas-atribuir-policy.png](media/app-setup-policies-assign-policy.png)

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>Atribuir uma política de instalação do aplicativo personalizado aos usuários em um grupo

Convém atribuir uma política de instalação do aplicativo personalizado a vários usuários que você identificou. Por exemplo, convém atribuir uma política a todos os usuários em um grupo de segurança. Você pode fazer isso Estabelecendo conexão com o Azure Active Directory PowerShell para o módulo de gráfico e do Skype para o módulo de PowerShell de negócios. Para obter mais informações sobre como usar o PowerShell para gerenciar equipes, consulte [Visão geral do PowerShell equipes](teams-powershell-overview.md).

Neste exemplo, nós atribuímos uma política de instalação do aplicativo personalizado chamada HR App instalação política a todos os usuários no grupo Contoso Pharmaceuticals RH Project.  

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
Atribua a todos os usuários no grupo a uma política de instalação de aplicativo específico. Neste exemplo, é política de instalação de aplicativo de RH.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
Dependendo do número de membros no grupo, este comando pode levar alguns minutos para executar.

## <a name="faq"></a>Perguntas Freqüentes

### <a name="working-with-app-setup-policies"></a>Como trabalhar com políticas de configuração de aplicativo

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quais políticas de configuração de aplicativo interno são incluídas no Centro de administração do Microsoft Teams?

- **Global (toda a organização padrão)**: esta política padrão se aplica a todos os usuários em sua organização, a menos que você atribua outra política. Edite a política global para aplicativos de pin que são mais importantes para seus usuários. 
- **FirstLineWorker**: esta diretiva é para trabalhadores de firstline. Você pode atribuí-lo aos trabalhadores firstline em sua organização. É importante saber que, como políticas personalizadas que você criar, você precisa atribuir a política aos usuários para que as configurações estejam ativos. Para obter mais informações, vá para a seção [atribuir uma política de instalação do aplicativo personalizado para os usuários](#assign-a-custom-app-setup-policy-to-users) deste artigo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Por que não é possível encontrar um aplicativo no painel Adicionar aplicativos fixados?

Nem todos os aplicativos podem ser fixados equipes por meio de uma política de instalação do aplicativo. Alguns aplicativos podem não suportar essa funcionalidade. Para localizar aplicativos que podem ser fixados, procure o aplicativo no painel **Adicionar fixados apps** . Guias que têm um escopo pessoal (guias estáticos) e bots podem ser fixados o cliente de desktop equipes e esses aplicativos estão disponíveis no painel **Adicionar fixados apps** .

Tenha em mente que app store equipes lista todos os aplicativos de equipes, enquanto o painel de **Adicionar fixado apps** inclui apenas os aplicativos que podem ser fixados equipes através de uma diretiva. 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sou um equipes de Admin de educação. O que é necessário saber sobre políticas de configuração de aplicativo em equipes educacional?

O aplicativo de chamada não está disponível em equipes educacional. Quando você cria uma nova política de instalação do aplicativo personalizado, o aplicativo de chamada é exibido na lista de aplicativos. No entanto, o aplicativo não está vinculado aos clientes de equipes e equipes para usuários de educação não verá o aplicativo de chamadas em equipes. 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a>Quantos aplicativos podem ser adicionados a uma política?

Um mínimo de dois aplicativos deve ser vinculado aos clientes móveis equipes (iOS e Android). Se uma diretiva tiver menos de dois aplicativos, os clientes móveis não irão refletir as configurações de política e em vez disso continuarão usando a configuração existente.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo leva para que as alterações de diretiva entrem em vigor?

Após editar a política global ou atribuir uma política, pode demorar até 24 horas para que as alterações entrem em vigor.

### <a name="user-experience"></a>Experiência do usuário

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Como os usuários podem ver todos os seus aplicativos fixados em equipes?

Para exibir todos os aplicativos que são vinculados para um usuário, os usuários podem ter que fazer o seguinte, dependendo do número de aplicativos instalados e o tamanho da janela de cliente suas equipes.

|Cliente de desktop de equipes |Cliente móvel de equipes |
|---------|---------|
|Na barra de aplicativos, na lateral direita equipes, clique em **… Aplicativos mais**.| Na barra de aplicativos, na parte inferior da equipes, passe para cima.|
|![App-Setup-Policies-Desktop-more-Apps.PNG](media/app-setup-policies-desktop-more-apps.png)<br>   |![App-Setup-Policies-Mobile-more-Apps.PNG](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>O que é necessário saber sobre a experiência de equipes móvel?

Os clientes móveis equipes (iOS e Android) atualmente não há suporte para aplicativos de pessoais. Dependendo de aplicativos definidos na política, aplicativos vinculados ao cliente de desktop do equipes podem não aparecer nos clientes móveis equipes. Pessoais bots ainda aparecerão no bate-papo em clientes móveis. 

Com os clientes móveis de equipes, os usuários verão apps equipes de núcleo como atividade, Chat e equipes e você pode fixar alguns aplicativos primários da Microsoft, como planejador e desloca.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Podem usuários alterar a ordem dos aplicativos fixados através de uma diretiva?

Atualmente, os usuários podem alterar a ordem dos seus aplicativos fixados em clientes móveis de equipes, mas não nos clientes de área de trabalho ou web equipes. 

### <a name="custom-teams-apps"></a>Aplicativos personalizados de equipes

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-through-appsource-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Minha organização criado um aplicativo personalizado de equipes e publicado por meio de AppSource mas ícone do aplicativo não será exibido como esperado quando o aplicativo é vinculado à barra de aplicativos em equipes. Como corrigi-lo? 

Certifique-se de que você siga as diretrizes de logotipo antes de enviar o aplicativo. Para saber mais, consulte a [lista de verificação para envio de painel do vendedor](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist). 

 ## <a name="related-topics"></a>Tópicos relacionados
- [Publicar um aplicativo para o catálogo de aplicativos do locatário do cliente equipes](tenant-apps-catalog-teams.md)
