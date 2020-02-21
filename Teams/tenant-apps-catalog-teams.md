---
title: Publicar aplicativos no catálogo de aplicativos do Microsoft Teams locatário
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Orientação para a publicação de aplicativos no catálogo de aplicativos do Microsoft Teams locatário.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161610"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a><span data-ttu-id="ebed9-103">Publicar aplicativos no catálogo de aplicativos do Microsoft Teams locatário</span><span class="sxs-lookup"><span data-stu-id="ebed9-103">Publish apps in the Microsoft Teams tenant app catalog</span></span>
=======================================================

<span data-ttu-id="ebed9-104">Você pode usar o catálogo de aplicativos do Microsoft Teams locatário para testar e distribuir aplicativos de linha de negócios para sua organização.</span><span class="sxs-lookup"><span data-stu-id="ebed9-104">You can use the Microsoft Teams tenant app catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="ebed9-105">O catálogo de aplicativos do locatário do teams permite a distribuição de aplicativos de linha de negócios que foram criados especificamente para a sua organização e que você depende de realizar funções comerciais essenciais.</span><span class="sxs-lookup"><span data-stu-id="ebed9-105">The Teams tenant app catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="ebed9-106">Para publicar aplicativos para sua organização, entre no cliente do Microsoft Teams usando uma conta com a função de administrador global ou administrador do teams Service e siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="ebed9-106">To publish apps for your organization, sign in to the Teams client using an account with either the global admin or teams service admin role and then follow the steps below.</span></span>

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a><span data-ttu-id="ebed9-107">Publicar um aplicativo no catálogo de aplicativos locatário do cliente da equipe</span><span class="sxs-lookup"><span data-stu-id="ebed9-107">Publish an app in the tenant app catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="ebed9-108">Estas etapas descrevem como publicar um aplicativo usando o cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="ebed9-108">These steps describe how to publish an app by using the Teams client.</span></span> <span data-ttu-id="ebed9-109">Você também pode publicar um aplicativo na página **gerenciar aplicativos** no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ebed9-109">You can also publish an app on the **Manage apps** page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ebed9-110">Para saber mais, consulte [gerenciar aplicativos no Microsoft Teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="ebed9-110">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="ebed9-111">Obter um pacote de aplicativos do teams</span><span class="sxs-lookup"><span data-stu-id="ebed9-111">Get a Teams app package</span></span>

<span data-ttu-id="ebed9-112">Um pacote do aplicativo Teams é criado usando o [Teams app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="ebed9-112">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="ebed9-113">Depois que tiver o pacote do aplicativo, você poderá adicioná-lo ao catálogo de aplicativos do locatário.</span><span class="sxs-lookup"><span data-stu-id="ebed9-113">Once you have the app package, you can add it to the tenant app catalog.</span></span> <span data-ttu-id="ebed9-114">Embora todos os usuários em sua organização possam ver o catálogo de aplicativos, apenas administradores globais e administradores de serviços de equipe podem publicá-los e gerenciá-los.</span><span class="sxs-lookup"><span data-stu-id="ebed9-114">While all users in your organization can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-app-catalog"></a><span data-ttu-id="ebed9-115">Vá para o catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="ebed9-115">Go to the tenant app catalog</span></span>

<span data-ttu-id="ebed9-116">Inicie o Teams e entre usando suas credenciais de administrador de serviço global ou Teams.</span><span class="sxs-lookup"><span data-stu-id="ebed9-116">Start Teams and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="ebed9-117">Selecione **aplicativos** no lado esquerdo do aplicativo e, em seguida, selecione a nova seção chamada para sua organização específica (neste exemplo, contoso).</span><span class="sxs-lookup"><span data-stu-id="ebed9-117">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="ebed9-118">Os usuários em sua organização podem exibir os aplicativos no catálogo e instalá-los para as equipes das quais eles são membros.</span><span class="sxs-lookup"><span data-stu-id="ebed9-118">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a><span data-ttu-id="ebed9-120">Adicionar um aplicativo ao catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="ebed9-120">Add an app to the tenant app catalog</span></span>

1. <span data-ttu-id="ebed9-121">Na página **aplicativos** , selecione **carregar um** > carregamento de aplicativo personalizado**para contoso**.</span><span class="sxs-lookup"><span data-stu-id="ebed9-121">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="ebed9-123">(Você também pode escolher **carregar para mim ou minhas equipes**, que é chamado de *Sideload*.</span><span class="sxs-lookup"><span data-stu-id="ebed9-123">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="ebed9-124">O Sideload torna o aplicativo disponível somente para suas equipes ou para as equipes que você selecionar.)</span><span class="sxs-lookup"><span data-stu-id="ebed9-124">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="ebed9-125">Navegue até o pacote do aplicativo e selecione-o e, em seguida, clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="ebed9-125">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image03.png)

<span data-ttu-id="ebed9-127">Quando você voltar ao catálogo de aplicativos do locatário, o novo aplicativo empresarial estará lá.</span><span class="sxs-lookup"><span data-stu-id="ebed9-127">When you go back to your tenant app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="ebed9-128">Lembre-se, somente você e os membros da sua organização têm acesso a este catálogo de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ebed9-128">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-app-catalog"></a><span data-ttu-id="ebed9-129">Atualizar um aplicativo no catálogo de aplicativos locatário</span><span class="sxs-lookup"><span data-stu-id="ebed9-129">Update an app in the tenant app catalog</span></span>

1. <span data-ttu-id="ebed9-130">Em seu catálogo de aplicativos locatário, selecione "**...**"</span><span class="sxs-lookup"><span data-stu-id="ebed9-130">From your tenant app catalog, select “**…**”</span></span> <span data-ttu-id="ebed9-131">no canto superior direito do aplicativo que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="ebed9-131">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="ebed9-132">Navegue até o pacote do aplicativo atualizado e selecione-o e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="ebed9-132">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image04.png)

<span data-ttu-id="ebed9-134">O aplicativo será revisado para a versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="ebed9-134">The app will be revised to version 2.0.</span></span> <span data-ttu-id="ebed9-135">Você também pode excluir o aplicativo de toda a sua empresa neste menu.</span><span class="sxs-lookup"><span data-stu-id="ebed9-135">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a><span data-ttu-id="ebed9-136">Usar o centro de administração do Microsoft Teams para gerenciar o catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="ebed9-136">Use the Microsoft Teams admin center to manage the tenant app catalog</span></span>

<span data-ttu-id="ebed9-137">Se você tiver aplicativos que precisem de correções de bugs, pode desativar temporariamente aplicativos para usuários em uma política de permissão de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ebed9-137">If you have apps that need bug fixes, you can temporarily disable apps for users in an app permission policy.</span></span>

1. <span data-ttu-id="ebed9-138">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para > **políticas de permissão**de **aplicativos do teams**.</span><span class="sxs-lookup"><span data-stu-id="ebed9-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="ebed9-139">Selecione a política de permissão do aplicativo que você deseja editar e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ebed9-139">Select the app permission policy that you want to edit, and then click **Edit**.</span></span>
3. <span data-ttu-id="ebed9-140">Em **aplicativos de locatário**, selecione **bloquear aplicativos específicos e permitir todos os outros**e, em seguida, adicione os aplicativos que você deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="ebed9-140">Under **Tenant apps**, select **Block specific apps and allow all others**, and then add the apps that you want to block.</span></span>

<span data-ttu-id="ebed9-141">Desabilitar um aplicativo impede que os usuários interajam com o aplicativo, sem excluir o aplicativo totalmente.</span><span class="sxs-lookup"><span data-stu-id="ebed9-141">Disabling an app blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="ebed9-142">Esses controles proporcionam flexibilidade e controle adicionais ao gerenciar aplicativos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ebed9-142">These controls give you additional flexibility and control when managing apps in your organization.</span></span>

<span data-ttu-id="ebed9-143">Para saber mais, consulte [gerenciar políticas de permissão do aplicativo no Microsoft Teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ebed9-143">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>