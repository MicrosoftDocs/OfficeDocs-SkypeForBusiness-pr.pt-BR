---
title: Publicar aplicativos no catálogo de aplicativos do Microsoft Teams locatário
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Orientação para a publicação de aplicativos no catálogo de aplicativos Microsoft Teams locatário.
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5affe464ac300d0084916ad8ec0044ca74f8fa6b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570075"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="37046-103">Publicar aplicativos no catálogo de aplicativos do Microsoft Teams locatário</span><span class="sxs-lookup"><span data-stu-id="37046-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="37046-104">Você pode usar o catálogo de aplicativos Microsoft Teams locatário para testar e distribuir aplicativos de linha de negócios para sua organização.</span><span class="sxs-lookup"><span data-stu-id="37046-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="37046-105">O catálogo de aplicativos de locatários do teams permite distribuir aplicativos de linha de negócios que foram criados especificamente para a sua organização e que você depende de realizar funções comerciais essenciais.</span><span class="sxs-lookup"><span data-stu-id="37046-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="37046-106">Para publicar aplicativos para sua organização, entre no cliente do Microsoft Teams usando uma conta com as funções de administrador global ou administrador do Team Service e siga as instruções abaixo.</span><span class="sxs-lookup"><span data-stu-id="37046-106">To publish apps for your organization, sign in to your Teams client using an account with the global admin or teams service admin roles and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="37046-107">Publicar um aplicativo no catálogo de aplicativos do locatário a partir do cliente do teams</span><span class="sxs-lookup"><span data-stu-id="37046-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="37046-108">Você precisa estar conectado ao cliente do Microsoft Teams com uma conta que tenha a função de administrador global de administrador ou Teams Service habilitada para publicar aplicativos para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="37046-108">You need to be signed in to the Microsoft Teams client with an account that has either the global admin or teams service admin role enabled to publish apps for your organization.</span></span> <span data-ttu-id="37046-109">Saiba mais sobre o [uso de funções de administrador para gerenciar o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="37046-109">Learn more about [using administrator roles to manage Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="37046-110">Obter um pacote de aplicativos do teams</span><span class="sxs-lookup"><span data-stu-id="37046-110">Get a Teams app package</span></span>

<span data-ttu-id="37046-111">Um pacote do aplicativo Teams é criado usando o [Teams app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="37046-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="37046-112">Depois que tiver o pacote do aplicativo, você poderá adicioná-lo ao catálogo de aplicativos da empresa.</span><span class="sxs-lookup"><span data-stu-id="37046-112">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="37046-113">Embora todos os usuários no locatário possam ver o catálogo de aplicativos, apenas administradores globais e administradores de serviço de equipe têm a capacidade de publicá-lo e gerenciá-lo.</span><span class="sxs-lookup"><span data-stu-id="37046-113">While all users in the tenant can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="37046-114">Vá para o catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="37046-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="37046-115">Inicie o cliente do Microsoft Teams e entre usando suas credenciais de administrador do serviço global ou Teams.</span><span class="sxs-lookup"><span data-stu-id="37046-115">Start the Microsoft Teams client and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="37046-116">Na loja do Microsoft Teams, selecione a nova seção nomeada para a sua organização específica (neste exemplo, contoso).</span><span class="sxs-lookup"><span data-stu-id="37046-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="37046-117">Os usuários em sua organização podem exibir os aplicativos no catálogo e instalá-los para as equipes das quais eles são membros.</span><span class="sxs-lookup"><span data-stu-id="37046-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="37046-119">Adicionar um aplicativo ao catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="37046-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="37046-120">Na loja, selecione **carregar um** > carregamento de aplicativo personalizado**para contoso**.</span><span class="sxs-lookup"><span data-stu-id="37046-120">From the store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="37046-122">(Você também pode escolher **carregar para mim ou minhas equipes**, que é chamado de *Sideload*.</span><span class="sxs-lookup"><span data-stu-id="37046-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="37046-123">O Sideload torna o aplicativo disponível somente para suas equipes ou para as equipes que você selecionar.)</span><span class="sxs-lookup"><span data-stu-id="37046-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="37046-124">Navegue até o pacote do aplicativo e selecione-o e, em seguida, clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="37046-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image03.png)

<span data-ttu-id="37046-126">Quando você voltar ao catálogo de aplicativos do locatário, o novo aplicativo empresarial estará lá.</span><span class="sxs-lookup"><span data-stu-id="37046-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="37046-127">Lembre-se, somente você e os membros da sua organização têm acesso a este catálogo de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="37046-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="37046-128">Atualizar um aplicativo no catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="37046-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="37046-129">Em seu catálogo de aplicativos do locatário, selecione "**...**"</span><span class="sxs-lookup"><span data-stu-id="37046-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="37046-130">no canto superior direito do aplicativo que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="37046-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="37046-131">Navegue até o pacote do aplicativo atualizado e selecione-o e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="37046-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image04.png)

<span data-ttu-id="37046-133">O aplicativo será revisado para a versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="37046-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="37046-134">Você também pode excluir o aplicativo de toda a sua empresa neste menu.</span><span class="sxs-lookup"><span data-stu-id="37046-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="37046-135">Usar o portal de administração do Office 365 para gerenciar o catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="37046-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="37046-136">Se você tiver aplicativos que precisem de correções de bugs, poderá desabilitar temporariamente os aplicativos por meio do portal de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="37046-136">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="37046-137">Selecione **configurações** > **Serviços & suplementos** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="37046-137">Select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="37046-138">Além das configurações anteriores, agora há uma seção dedicada aos aplicativos da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="37046-138">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="37046-139">Você pode escolher quais aplicativos deseja habilitar ou desabilitar.</span><span class="sxs-lookup"><span data-stu-id="37046-139">You can choose which apps you want to enable or disable.</span></span>

![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image05.png)

<span data-ttu-id="37046-141">Desabilitar um aplicativo impedirá que os usuários interajam com o aplicativo, sem excluir o aplicativo totalmente.</span><span class="sxs-lookup"><span data-stu-id="37046-141">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="37046-142">Esses controles proporcionam flexibilidade e controle adicionais ao gerenciar aplicativos em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="37046-142">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
