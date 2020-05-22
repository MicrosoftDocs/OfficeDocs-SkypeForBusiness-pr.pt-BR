---
title: Criar um 'aplicativo Portal da Intranet' do Teams a partir de um site ou página do SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: Use um site ou uma página existente do SharePoint Online e crie uma guia estática independente que possa ser usada como um portal da Intranet para a sua organização.
localization_priority: Priority
ms.openlocfilehash: 4777b744d76415f45718cb274f402556e1e28240
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326578"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="5cf16-103">Criar um 'aplicativo Portal da Intranet' do Teams a partir de um site ou página do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5cf16-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="5cf16-104">Use as etapas deste artigo para criar um aplicativo autônomo e estático dentro do Teams vinculado ao site da intranet da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5cf16-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="5cf16-105">Um *Aplicativo pessoal do Teams* do seu site da intranet do SharePoint é criado e aparecerá como uma guia dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="5cf16-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="5cf16-106">Esta guia pode conter informações importantes para todos os usuários do Teams.</span><span class="sxs-lookup"><span data-stu-id="5cf16-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="5cf16-107">É uma maneira rápida e conveniente para que os usuários do Teams acessem atualizações com apenas um clique.</span><span class="sxs-lookup"><span data-stu-id="5cf16-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="5cf16-108">Lembre-se de que o processo mostrado **deve usar** um site ou página do SharePoint *moderno* para funcionar.</span><span class="sxs-lookup"><span data-stu-id="5cf16-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="5cf16-109">Este processo não está disponível para sites ou páginas *clássicos*.</span><span class="sxs-lookup"><span data-stu-id="5cf16-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5cf16-110">Verifique se o carregamento lateral dos aplicativos do Teams está ativado para o locatário.</span><span class="sxs-lookup"><span data-stu-id="5cf16-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="5cf16-111">Dependendo de onde você estiver no processo de migração do portal de administração do Teams, talvez seja necessário habilitá-lo em Teams > Administrador, ou em Administrador > Configurações > Serviços e suplementos > Microsoft Teams > Aplicativos > Aplicativos externos, na versão anterior do portal!</span><span class="sxs-lookup"><span data-stu-id="5cf16-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="5cf16-112">Use o App Studio para criar seu aplicativo autônomo do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5cf16-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="5cf16-113">Antes de começar:</span><span class="sxs-lookup"><span data-stu-id="5cf16-113">Before you begin:</span></span>

1. <span data-ttu-id="5cf16-114">Você precisará saber a URL de um site ou página moderna de Comunicação ou de Equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5cf16-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="5cf16-115">Esses sites sempre terão */teams/* ou */sites/* em seus caminhos.</span><span class="sxs-lookup"><span data-stu-id="5cf16-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="5cf16-116">Você precisará conhecer o subdomínio de seu locatário, que será usado no espaço reservado **{{subdomínio}}**.</span><span class="sxs-lookup"><span data-stu-id="5cf16-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="5cf16-117">Este artigo usará **{{siteUrl}}** como um espaço reservado para a *URL* do site ou da página que você escolheu.</span><span class="sxs-lookup"><span data-stu-id="5cf16-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="5cf16-118">*URLs* de exemplo:   https://contoso.sharepoint.com/teams/Contoso   *ou* https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="5cf16-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span>
4. <span data-ttu-id="5cf16-119">Além disso, o **{{sitePath}}** será usado para indicar o *caminho* da URL (ex:/teams/Contoso).</span><span class="sxs-lookup"><span data-stu-id="5cf16-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="5cf16-120">Exemplos de *caminhos*: /teams/Contoso *ou* /sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="5cf16-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span>

<span data-ttu-id="5cf16-121">Comece seguindo as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="5cf16-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="5cf16-122">Vá para a Teams Store.</span><span class="sxs-lookup"><span data-stu-id="5cf16-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="5cf16-123">Instale ou abra o App Studio.</span><span class="sxs-lookup"><span data-stu-id="5cf16-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="5cf16-124">Clique em **Abrir**, ao lado da opção Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5cf16-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="5cf16-125">Com o App Studio aberto, clique em **Editor de manifesto**.</span><span class="sxs-lookup"><span data-stu-id="5cf16-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="5cf16-126">**Criar um novo aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="5cf16-126">**Create a new app**.</span></span>

6. <span data-ttu-id="5cf16-127">Preencha todos os **Detalhes do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="5cf16-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="5cf16-128">Clique nas **guias** em Recursos.</span><span class="sxs-lookup"><span data-stu-id="5cf16-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="5cf16-129">Clique em **Adicionar** na guia Pessoal.</span><span class="sxs-lookup"><span data-stu-id="5cf16-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="5cf16-130">Preencha o **Nome** e escolha **uma nova ID de Entidade exclusiva**.</span><span class="sxs-lookup"><span data-stu-id="5cf16-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="5cf16-131">Preencha a **contentURL e URL do site**.</span><span class="sxs-lookup"><span data-stu-id="5cf16-131">Fill in the **contentURL and Website URL**.</span></span>

- <span data-ttu-id="5cf16-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="5cf16-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="5cf16-133">**websiteUrl**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="5cf16-133">**websiteUrl**: {{siteUrl}}</span></span>

    <span data-ttu-id="5cf16-134">Exemplo de **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="5cf16-134">Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span>

11. <span data-ttu-id="5cf16-135">Navegue para **Domínios e permissões**.</span><span class="sxs-lookup"><span data-stu-id="5cf16-135">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="5cf16-136">Verifique se a seção de domínios válidos contém o nome do seu domínio do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5cf16-136">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="5cf16-137">Exemplo: contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="5cf16-137">Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="5cf16-138">Adicione as seguintes propriedades de **logon único** do aplicativo Web:</span><span class="sxs-lookup"><span data-stu-id="5cf16-138">Add the following web app **single sign-on** properties:</span></span>

     <span data-ttu-id="5cf16-139">Exemplo:  **ID de aplicativo AAD**: 00000003-0000-0ff1-ce00-000000000000  **URL do recurso**: {{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="5cf16-139">Example:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span></span>

    ![Logon único de aplicativo Web, com ID e URL.](media/personal-app.png)

13. <span data-ttu-id="5cf16-141">**Salve** essas propriedades e navegue para **Testar e distribuir**.</span><span class="sxs-lookup"><span data-stu-id="5cf16-141">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="5cf16-142">Instale o aplicativo para testá-lo pessoalmente.</span><span class="sxs-lookup"><span data-stu-id="5cf16-142">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5cf16-143">Se você não estiver usando o Teams App Studio, será necessário compactar o arquivo manifest.JSON que você acabou de criar, navegar até a App Store no Teams e clicar no link **carregar aplicativo personalizado** (na parte inferior direita da App Store).</span><span class="sxs-lookup"><span data-stu-id="5cf16-143">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="5cf16-144">Isso tornará o aplicativo disponível para você.</span><span class="sxs-lookup"><span data-stu-id="5cf16-144">This will make the app available to you.</span></span>

15. <span data-ttu-id="5cf16-145">Agora o aplicativo está disponível como uma guia estática para você carregar e visualizar no Teams.</span><span class="sxs-lookup"><span data-stu-id="5cf16-145">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="5cf16-146">Testar e exibir sua nova guia estática</span><span class="sxs-lookup"><span data-stu-id="5cf16-146">Test and view your new static tab</span></span>

<span data-ttu-id="5cf16-147">Para exibir a nova guia no Teams para área de trabalho, navegue até as reticências (**…**) no lado esquerdo da barra de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5cf16-147">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="5cf16-148">Encontre seu novo aplicativo, carregue-o e teste seu aplicativo autônomo no Teams.</span><span class="sxs-lookup"><span data-stu-id="5cf16-148">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="5cf16-149">Se você deseja disponibilizar o novo aplicativo no menu esquerdo em uma posição superior, você deve usar uma configuração de política de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5cf16-149">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="5cf16-150">Essa configuração pode ser encontrada na seção Administrador da equipe > Política do aplicativo > Adicionar um aplicativo afixado.</span><span class="sxs-lookup"><span data-stu-id="5cf16-150">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="5cf16-151">Quando você atribui a política a um usuário para teste, a alteração será exibida algumas horas depois.</span><span class="sxs-lookup"><span data-stu-id="5cf16-151">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="5cf16-152">Com isso em mente, decida onde o aplicativo deve aparecer o quanto antes para evitar atrasos.</span><span class="sxs-lookup"><span data-stu-id="5cf16-152">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="5cf16-153">Para exibir e testar o novo aplicativo em um dispositivo móvel, abra a gaveta de aplicativos tocando na divisa (**^**) acima da barra de guias, na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="5cf16-153">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="5cf16-154">Encontre seu aplicativo e navegue até ele no seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="5cf16-154">Find your app and navigate to it on your mobile device.</span></span>

> [!CAUTION]
> <span data-ttu-id="5cf16-155">No momento, o suporte para dispositivos móveis está em Visualização de desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="5cf16-155">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="5cf16-156">Para habilitar a Visualização de desenvolvedor, navegue até Configurações > Sobre e habilite o modo de Visualização de desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="5cf16-156">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="5cf16-157">Um arquivo Manifest.JSON de amostra</span><span class="sxs-lookup"><span data-stu-id="5cf16-157">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="5cf16-158">O arquivo        JSO que você gerar se parecerá com o mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="5cf16-158">The JSO        file you generate will look something like the one below.</span></span>

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

            "name": "Contoso Net",

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/",

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet",

            "scopes": [

                "personal"

            ]

        },

        {

            "entityId": "teamSiteTab",

            "name": "Team Contoso",

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/",

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso",

            "scopes": [

                "personal"

            ]

        }

    ],

    "permissions": [

        "identity",

        "messageTeamMembers"

    ],

    "validDomains": [

        "contoso.sharepoint.com"

    ],

    "webApplicationInfo": {

        "id": "00000003-0000-0ff1-ce00-000000000000",

        "resource": "https://contoso.sharepoint.com"

    }

}
```
