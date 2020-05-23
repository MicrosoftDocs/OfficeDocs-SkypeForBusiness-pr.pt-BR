---
title: Gerenciar políticas de configuração de aplicativo no Microsoft Teams
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
description: Saiba como usar e gerenciar políticas de configuração de aplicativos no Microsoft Teams para usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: b4c6fe9551374139e8220543cb83f262a2a5195a
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350055"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gerenciar políticas de configuração de aplicativo no Microsoft Teams

> [!NOTE]
> Se você ativou a configuração do aplicativo de toda a organização, **permita a interação com aplicativos personalizados**, talvez você não veja as políticas de configuração do aplicativo ainda no centro de administração do Microsoft Teams. Ele está sendo implantado e estará disponível em breve em sua organização.

Como administrador, é possível usar as políticas de configuração de aplicativos para fazer o seguinte:

- Personalize o Teams para destacar os aplicativos mais importantes para os usuários. Você escolhe os aplicativos para fixar e define a ordem em que eles aparecem. A fixação de aplicativos permite mostrar os aplicativos que os usuários da sua organização precisam, inclusive aqueles criados por terceiros ou por desenvolvedores da sua organização.
- Controle se os usuários podem fixar aplicativos no Teams.
- Instale aplicativos em nome dos usuários **(na visualização)**. Você escolhe quais aplicativos são instalados por padrão para os usuários quando eles iniciam o Teams. Lembre-se de que os usuários ainda poderão instalar os próprios aplicativos se a [política de permissão do aplicativo](teams-app-permission-policies.md) atribuída a ele permitir.

Os aplicativos do são fixados na barra do aplicativo. Esta é a barra do lado do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams (iOS e Android).

|Cliente de desktop Teams  |Cliente móvel do teams |
|---------|---------|
|![Captura de tela mostrando o cliente de desktop Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Captura de tela mostrando o cliente móvel do teams](media/app-setup-policies-mobile-app-bar.png)      |

Para ver seus aplicativos pré-instalados, na barra de aplicativos, os usuários clicam em **... Mais aplicativos** na área de trabalho da equipe e nos clientes Web e passe o dedo para cima nos clientes móveis.

Você gerencia as políticas de configuração do aplicativo no centro de administração do Microsoft Teams. Você pode usar a política global (padrão para toda a organização) ou criar políticas personalizadas e atribuí-las aos usuários. Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

Você pode editar as configurações na política global para incluir os aplicativos desejados. Se você quiser personalizar o Microsoft Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas. Se for atribuída uma política personalizada a um usuário, essa política se aplicará ao usuário. Se um usuário não estiver atribuído a uma política personalizada, a política global se aplicará ao usuário.

![Captura de tela mostrando a página de políticas de configuração de aplicativos](media/app-setup-policies.png)

> [!NOTE]
> Se você tiver equipes para educação, é importante saber que o aplicativo de atribuições está fixado por padrão na política global, ainda que, no momento, você não a veja listado na política global. Será o quarto aplicativo na lista de aplicativos fixos em clientes do teams.

## <a name="create-a-custom-app-setup-policy"></a>Criar uma política de configuração de aplicativo personalizada

Você pode usar o centro de administração do Microsoft Teams para criar uma política personalizada.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de configuração de **aplicativos do teams**  >  **Setup policies**.
2. Clique em **Adicionar**.
    ![Captura de tela mostrando a página Adicionar políticas de configuração de aplicativos](media/app-setup-policies-add.png)
3. Insira um nome e uma descrição para a política.
4. Ative ou desative **carregar aplicativos personalizados**, dependendo se você deseja permitir que os usuários carreguem aplicativos personalizados para o Microsoft Teams. Você não poderá alterar essa configuração se a opção **permitir que aplicativos de terceiros** estiverem desativados em [configurações de aplicativo de toda a organização](manage-apps.md#manage-org-wide-app-settings).
5. Ative ou desative **permitir a fixação do usuário**, dependendo se você deseja permitir que os usuários personalizem a barra de aplicativos fixando os aplicativos nela.
6. Para instalar aplicativos para usuários **(na visualização)**, faça o seguinte:

    1. Em **aplicativos instalados**, clique em **adicionar aplicativos**.
    2. No painel **adicionar aplicativos instalados** , procure os aplicativos que você deseja instalar automaticamente para os usuários quando eles iniciarem o Teams. Você também pode filtrar aplicativos por política de permissão do aplicativo. Depois de escolher a lista de aplicativos, clique em **Adicionar**.

        ![Captura de tela mostrando o painel Adicionar aplicativos instalados](media/app-setup-policies-add-installed-apps.png)

7. Para fixar aplicativos, faça o seguinte:

    1. Em **aplicativos fixos**, clique em **adicionar aplicativos**.
    2. No painel **adicionar aplicativos fixos** , procure os aplicativos que você deseja adicionar e, em seguida, clique em **Adicionar**. Você também pode filtrar aplicativos por política de permissão do aplicativo. Depois de escolher a lista de aplicativos a serem fixados, clique em **Adicionar**.

         ![Captura de tela mostrando o painel Adicionar aplicativos fixados](media/app-setup-policies-add-apps.png)

    3. Organize os aplicativos na ordem em que você deseja que eles apareçam no Teams e, em seguida, clique em **salvar**.

        ![Captura de tela mostrando a seção de aplicativos fixos](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Editar uma política de configuração de aplicativo

Você pode usar o centro de administração do Microsoft Teams para editar uma política, incluindo a política global (padrão de toda a organização) e políticas personalizadas que você criar.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de configuração de **aplicativos do teams**  >  **Setup policies**.
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Aqui, faça as alterações desejadas.
4. Clique em **Salvar**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Atribuir uma política de configuração de aplicativo personalizada aos usuários

Você pode usar o centro de administração do Microsoft Teams para atribuir uma política personalizada a usuários individuais ou o módulo do PowerShell do Skype for Business para atribuir uma política personalizada a usuários em um grupo, como um grupo de segurança ou grupo de distribuição.

### <a name="assign-a-custom-app-setup-policy-to-users"></a>Atribuir uma política de configuração de aplicativo personalizada aos usuários

Para atribuir uma política a um usuário:

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Em **política de configuração do aplicativo**, selecione a política de configuração do aplicativo que você deseja atribuir e clique em **aplicar**.

Para atribuir uma política a vários usuários de uma só vez:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e procure os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique no &#x2713; (marca de seleção) na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **aplicar**.  

Ou, você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de configuração de **aplicativos do teams**  >  **Setup policies**.
2. Escolha a política clicando à esquerda do nome da política.
3. Escolha **Gerenciar usuários**.
4. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Após terminar de adicionar usuários, selecione **salvar**.

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>Atribuir uma política de configuração de aplicativo personalizada a usuários em um grupo

Você pode querer atribuir uma política de configuração de aplicativo personalizada a vários usuários que você já tenha identificado. Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança. Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business. Para obter mais informações sobre como usar o PowerShell para gerenciar o Microsoft Teams, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).

Neste exemplo, atribuímos uma política de configuração de aplicativo personalizada chamada política de configuração de aplicativo de RH a todos os usuários no grupo de projetos de RH da Contoso Pharmaceuticals.  

> [!NOTE]
> Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenha o GroupObjectId do grupo específico.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Obter os membros do grupo especificado.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Atribua todos os usuários do grupo a uma política de configuração de aplicativo específica. Neste exemplo, a política de configuração de aplicativo de RH.
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.UserPrincipalName}
``` 
Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.

## <a name="faq"></a>Perguntas frequentes

### <a name="working-with-app-setup-policies"></a>Trabalhando com políticas de configuração de aplicativos

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quais são as políticas de configuração de aplicativos internas incluídas no centro de administração do Microsoft Teams?

- **Global (padrão para toda a organização)**: essa política padrão se aplica a todos os usuários da sua organização, a menos que você atribua outra política. Edite a política global para fixar aplicativos que são mais importantes para seus usuários.
- **FirstLineWorker**: esta política destina-se a trabalhadores de primeira mão. Você pode atribuí-lo a trabalhadores de primeira mão em sua organização. É importante saber que, assim como as políticas personalizadas que você cria, você precisa atribuir a política aos usuários para que as configurações sejam ativas. Para obter mais informações, acesse a seção [atribuir política de configuração de aplicativo personalizada a usuários](#assign-a-custom-app-setup-policy-to-users) deste artigo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Por que não consigo encontrar um aplicativo no painel Adicionar aplicativos fixos?

Nem todos os aplicativos podem ser fixados para o Microsoft Teams por meio de uma política de configuração de aplicativo. Alguns aplicativos podem não oferecer suporte a essa funcionalidade. Para localizar aplicativos que possam ser fixados, procure o aplicativo no painel **adicionar aplicativos fixos** . As guias que têm um escopo pessoal (guias estáticos) e bots podem ser fixadas ao cliente da área de trabalho do Teams e esses aplicativos estão disponíveis no painel **adicionar aplicativos fixos** .

Lembre-se de que a loja de aplicativos do teams lista todos os aplicativos do Teams, enquanto o painel **adicionar aplicativos fixos** inclui apenas os aplicativos que podem ser fixados ao Teams por meio de uma política. 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sou um administrador do Microsoft Teams para educação. O que preciso saber sobre as políticas de configuração de aplicativos no Teams for Education?

O aplicativo de chamada não está disponível no Teams for Education. Quando você cria uma nova política de configuração de aplicativo personalizada, o aplicativo de chamada é exibido na lista de aplicativos. No entanto, o aplicativo não está fixado a clientes do Teams e o Microsoft Teams para que os usuários de educação não vejam o aplicativo chamadas no Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Quantos aplicativos fixos podem ser adicionados a uma política?

No mínimo dois aplicativos devem ser fixados para os clientes móveis do Teams (iOS e Android). Se uma política tem menos de dois aplicativos, os clientes móveis não refletem as configurações de política e, em vez disso, continuarão a usar a configuração existente.

Não há limite quanto ao número de aplicativos fixos que você pode adicionar a uma política.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo leva para as alterações de política entrarem em vigor?

Depois de editar a política global ou atribuir uma política, pode demorar algumas horas para que as alterações entrem em vigor.

### <a name="user-experience"></a>Experiência do usuário

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Como os usuários podem ver todos os seus aplicativos fixos no Microsoft Teams?

Para exibir todos os aplicativos que estão fixos para um usuário, os usuários podem precisar fazer o seguinte, dependendo do número de aplicativos instalados e do tamanho da janela do cliente de suas equipes.

|Cliente de desktop Teams |Cliente móvel do teams |
|---------|---------|
|Na barra de aplicativos na lateral do Teams, clique em **... Mais aplicativos**.| Na barra do aplicativo, próxima à parte inferior do Teams, passe o dedo para cima.|
|![Captura de tela mostrando mais aplicativos no cliente da área de trabalho do teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Captura de tela mostrando mais aplicativos no cliente móvel do Microsoft Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>O que preciso saber sobre a experiência móvel do teams?

Atualmente, os clientes móveis do Teams (iOS e Android) não dão suporte a aplicativos pessoais com guias estáticas. Dependendo dos aplicativos definidos na política, os aplicativos fixos no cliente da área de trabalho do teams podem não aparecer nos clientes móveis do Microsoft Teams. Os bots pessoais ainda serão exibidos em chat em clientes móveis.

Com os clientes móveis do Microsoft Teams, os usuários verão aplicativos centrais do Teams, como atividade, chat e equipes, e você poderá fixar alguns aplicativos de terceiros da Microsoft, como turnos.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Os usuários podem alterar a ordem dos aplicativos fixos por meio de uma política?

Os usuários podem alterar a ordem dos aplicativos fixos na área de trabalho do Microsoft Teams e clientes móveis se a opção **permitir fixação do usuário** estiver ativada. Os usuários não podem alterar a ordem dos aplicativos fixos nos clientes Web do teams.

#### <a name="does-user-pinning-take-precedence"></a>A fixação do usuário tem prioridade?

Se a política de configuração do aplicativo atribuída ao usuário for alterada para bloquear a fixação do aplicativo do usuário, o Teams removerá todos os aplicativos fixados na barra de aplicativos. Se a política for alterada para permitir a fixação do aplicativo do usuário, os usuários deverão refixar os aplicativos anteriormente desafixados.

### <a name="custom-teams-apps"></a>Aplicativos personalizados do teams

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Minha organização construiu um aplicativo de equipes personalizado e o publicou, seja para AppSource ou o catálogo de aplicativos do locatário, mas o ícone do aplicativo não é exibido como esperado quando o aplicativo é fixado à barra de aplicativos no Teams. Como corrigir?

Certifique-se de seguir as diretrizes do logotipo antes de enviar o aplicativo. Para saber mais, consulte [a lista de verificação para envio do painel do vendedor](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview). 

 ## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de administração para aplicativos no Teams](admin-settings.md)
- [Atribuir políticas a seus usuários no Teams](assign-policies.md)
