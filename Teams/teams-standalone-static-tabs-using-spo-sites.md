---
title: Criar um aplicativo de portal de intranet do teams ' a partir de um site ou página do SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Pegue um site ou uma página existente do SharePoint Online e crie uma guia estática autônoma que pode ser usada como um portal da intranet para a sua organização.
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106628"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="6b544-103">Criar um aplicativo de portal de intranet do teams ' a partir de um site ou página do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6b544-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="6b544-104">Use as etapas neste artigo para criar um aplicativo autônomo e estático dentro do teams que está vinculado ao site de intranet da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6b544-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="6b544-105">Um *aplicativo pessoal do teams* do seu site de intranet do SharePoint é criado e será exibido como uma guia dentro do teams.</span><span class="sxs-lookup"><span data-stu-id="6b544-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="6b544-106">Esta guia pode conter informações importantes para todos os usuários do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6b544-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="6b544-107">É uma maneira rápida e conveniente para os usuários do teams acessarem atualizações apenas em uma guia clique em ausente.</span><span class="sxs-lookup"><span data-stu-id="6b544-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="6b544-108">Lembre-se de que o processo mostrado **deve usar** um site *moderno* do SharePoint ou uma página para funcionar.</span><span class="sxs-lookup"><span data-stu-id="6b544-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="6b544-109">Este processo não está disponível para sites ou páginas *clássicas* .</span><span class="sxs-lookup"><span data-stu-id="6b544-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b544-110">Certifique-se de que o carregamento lado a lado dos aplicativos da equipe esteja habilitado para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="6b544-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="6b544-111">Dependendo de onde você estiver no processo de migração do portal de administração do Teams, talvez seja necessário habilitá-lo em Teams > administrador ou em configurações do administrador > > serviços e suplementos > Microsoft Teams > aplicativos > aplicativos externos, na versão anterior do portal!</span><span class="sxs-lookup"><span data-stu-id="6b544-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span> 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="6b544-112">Usar o app Studio para criar seu aplicativo autônomo do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6b544-112">Use App Studio to create your standalone SharePoint Online app</span></span>
<span data-ttu-id="6b544-113">' ' ' Antes de começar:</span><span class="sxs-lookup"><span data-stu-id="6b544-113">''' Before you begin:</span></span>
1. <span data-ttu-id="6b544-114">Você precisará saber a URL de um site de equipe ou de comunicação moderna do SharePoint Online ou uma página.</span><span class="sxs-lookup"><span data-stu-id="6b544-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="6b544-115">Esses sites sempre terão o */Teams/* ou o */sites/* em seus caminhos.</span><span class="sxs-lookup"><span data-stu-id="6b544-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="6b544-116">Você precisará saber o subdomínio do seu locatário, que será usado no espaço reservado **{{subdomain}}**.</span><span class="sxs-lookup"><span data-stu-id="6b544-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="6b544-117">Este artigo usará o espaço reservado **{{SiteUrl}}** para você que seja a *URL* do site ou da página que você escolheu.</span><span class="sxs-lookup"><span data-stu-id="6b544-117">This article will use **{{siteUrl}}** placeholder for your the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="6b544-118">Exemplos de *URLs*: https://contoso.sharepoint.com/teams/Contoso *ou*   https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="6b544-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span> 
4. <span data-ttu-id="6b544-119">Além disso, **{{sitePath}}** será usado para denotar o *caminho* da URL (ex:/Teams/contoso).</span><span class="sxs-lookup"><span data-stu-id="6b544-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="6b544-120">*Caminhos*de exemplo:/Teams/Contoso *ou* /sites/contoso</span><span class="sxs-lookup"><span data-stu-id="6b544-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span> 

<span data-ttu-id="6b544-121">Comece seguindo as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="6b544-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="6b544-122">Acesse a loja do teams.</span><span class="sxs-lookup"><span data-stu-id="6b544-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="6b544-123">Instalar ou abrir o app Studio.</span><span class="sxs-lookup"><span data-stu-id="6b544-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="6b544-124">Clique em **abrir**, ao lado da opção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6b544-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="6b544-125">Com o app Studio aberto, clique em **Editor de manifestos**.</span><span class="sxs-lookup"><span data-stu-id="6b544-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="6b544-126">**Crie um novo aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="6b544-126">**Create a new app**.</span></span>

6. <span data-ttu-id="6b544-127">Preencha todos os **detalhes do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="6b544-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="6b544-128">Clique nas **guias** em recursos.</span><span class="sxs-lookup"><span data-stu-id="6b544-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="6b544-129">Clique em **Adicionar** na guia pessoal.</span><span class="sxs-lookup"><span data-stu-id="6b544-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="6b544-130">Preencha o **nome** e escolha **uma nova ID de entidade exclusiva**.</span><span class="sxs-lookup"><span data-stu-id="6b544-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="6b544-131">Preencha o **contentURL e a URL do site**.</span><span class="sxs-lookup"><span data-stu-id="6b544-131">Fill in the **contentURL and Website URL**.</span></span> 

- <span data-ttu-id="6b544-132">**contentUrl**: {{siteurl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="6b544-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="6b544-133">**web'iteUrl**: {{SiteUrl}} ' ' exemplo **contentURL**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="6b544-133">**web'iteUrl**: {{siteUrl}} ''   Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span> 

11. <span data-ttu-id="6b544-134">Navegue até **domínios e Permissi'ns**.</span><span class="sxs-lookup"><span data-stu-id="6b544-134">Navigate to **Domains and Permissi'ns**.</span></span> <span data-ttu-id="6b544-135">Verifique se a seção Domains válidos contém seu nome de domínio do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6b544-135">Make sure the valid domains section contains your SharePoint online domain name.</span></span>
<span data-ttu-id="6b544-136">' ' Exemplo: contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="6b544-136">'' Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="6b544-137">Adicione as seguintes propriedades de **logon único** do aplicativo Web: ' ' exemplo: ' ' ' ' **ID do aplicativo do AAD**: **URL do recurso**00000003-0000-0ff1-ce00-000000000000: {{subdomain}}. SharePoint. com ![' ' ' logon único do aplicativo Web, com ID e URL.](media/personal-app.png)</span><span class="sxs-lookup"><span data-stu-id="6b544-137">Add the following web app **single sign-on** properties:  ''  Example:''''  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com' '' ![Web app single sign-on, with ID and URL.](media/personal-app.png)</span></span>

13. <span data-ttu-id="6b544-138">**Salve** essas propriedades e navegue para **testar e distribuir**.</span><span class="sxs-lookup"><span data-stu-id="6b544-138">**Save** these properties and then navigate to **Test and distribute**.</span></span> 

14. <span data-ttu-id="6b544-139">Instale o aplicativo para testar o aplicativo pessoalmente.</span><span class="sxs-lookup"><span data-stu-id="6b544-139">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b544-140">Se você não estiver usando o Teams app Studio, será necessário. zip no manifesto. Arquivo JSON que você acabou de criar, navegue até a App Store no Teams e clique em carregar link do **aplicativo personalizado** (no canto inferior direito da App Store).</span><span class="sxs-lookup"><span data-stu-id="6b544-140">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="6b544-141">Isso fará com que o aplicativo seja disponibilizado para você.</span><span class="sxs-lookup"><span data-stu-id="6b544-141">This will make the app available to you.</span></span>

15. <span data-ttu-id="6b544-142">Agora o aplicativo está disponível como uma guia estática para você carregar e exibir no Teams.</span><span class="sxs-lookup"><span data-stu-id="6b544-142">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="6b544-143">Testar e exibir sua nova guia estática</span><span class="sxs-lookup"><span data-stu-id="6b544-143">Test and view your new static tab</span></span>

<span data-ttu-id="6b544-144">Para exibir a nova guia na área de trabalho do Teams, navegue até as reticências (**...**) no lado esquerdo da barra de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6b544-144">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="6b544-145">Encontre o novo aplicativo, carregue-o e teste o aplicativo autônomo no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6b544-145">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="6b544-146">Se você quiser disponibilizar o novo aplicativo no menu à esquerda em uma posição mais alta, você deve usar uma configuração de política de aplicativo para isso.</span><span class="sxs-lookup"><span data-stu-id="6b544-146">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="6b544-147">Essa configuração pode ser encontrada na seção administrador da equipe > política do aplicativo > adicionar um aplicativo fixo.</span><span class="sxs-lookup"><span data-stu-id="6b544-147">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="6b544-148">Quando você atribuir a política a um usuário para teste, a alteração será exibida em 24 horas depois.</span><span class="sxs-lookup"><span data-stu-id="6b544-148">When you assign the policy to a user for testing, the change will appear 24 hours later.</span></span> <span data-ttu-id="6b544-149">Com isso em mente, decida onde o aplicativo deve ser exibido da sua conveniência mais antiga para ajudar a evitar atrasos.</span><span class="sxs-lookup"><span data-stu-id="6b544-149">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="6b544-150">Para exibir e testar o novo aplicativo em um dispositivo móvel, abra a gaveta do aplicativo tocando na divisa (**^**) acima da barra de guias próxima à parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="6b544-150">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="6b544-151">Localize seu aplicativo e navegue para ele em seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="6b544-151">Find your app and navigate to it on your mobile device.</span></span>
        
> [!CAUTION]
> <span data-ttu-id="6b544-152">O suporte móvel está atualmente na visualização do desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="6b544-152">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="6b544-153">Para habilitar a visualização de desenvolvedor, navegue até configurações > e, em seguida, habilite o modo de visualização do desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="6b544-153">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="6b544-154">Um arquivo manifest. JSON de exemplo</span><span class="sxs-lookup"><span data-stu-id="6b544-154">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="6b544-155">O arquivo JSO que você gerar irá se parecer com o nome abaixo.</span><span class="sxs-lookup"><span data-stu-id="6b544-155">The JSO        file you generate will look something like the one below.</span></span>

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
''
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