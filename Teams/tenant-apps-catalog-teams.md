---
title: Publicar aplicativos no Catálogo de Aplicativos do Locatário do Microsoft Teams
author: ChuckEdmonson
ms.author: lolaj
manager: serdars
ms.date: 08/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Orientação para a publicação de aplicativos no catálogo de aplicativos do Microsoft equipes inquilino.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7e280d0e0034290232010897b34e0e30319bd51
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464208"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="629e7-103">Publicar aplicativos no Catálogo de Aplicativos do Locatário do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="629e7-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="629e7-104">Você pode usar o catálogo de aplicativos do Microsoft equipes locatário para testar e distribuir aplicativos de linha de negócios para sua organização.</span><span class="sxs-lookup"><span data-stu-id="629e7-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="629e7-105">O catálogo de aplicativos do inquilino de equipes permite que você distribuir seus aplicativos de linha de negócios que foram criados especificamente para sua organização e que você depende para concluem as funções essenciais aos negócios para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="629e7-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="629e7-106">Faça logon no seu cliente de equipes usando suas credenciais de administrador global e publicar aplicativos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="629e7-106">Sign in to your Teams client using your global admin credentials and publish apps for your organization.</span></span> 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="629e7-107">Publicar um aplicativo para o catálogo de aplicativos do locatário do cliente equipes</span><span class="sxs-lookup"><span data-stu-id="629e7-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

<span data-ttu-id="629e7-108">Observação: Você precisa estar conectado ao cliente Microsoft Teams usando suas credenciais de administrador global para publicar aplicativos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="629e7-108">NOTE: You need to be signed in to the Microsoft Teams client using your global admin credentials to publish apps for your organization.</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="629e7-109">Obtenha um pacote de aplicativos de equipes</span><span class="sxs-lookup"><span data-stu-id="629e7-109">Get a Teams app package</span></span>

<span data-ttu-id="629e7-110">Um pacote de aplicativos de equipes é criado usando o [Studio de App equipes](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="629e7-110">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="629e7-111">Depois que você tiver o pacote de aplicativos, você pode adicioná-lo ao catálogo de aplicativos do enterprise.</span><span class="sxs-lookup"><span data-stu-id="629e7-111">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="629e7-112">Enquanto todos os usuários no locatário, pode exibir o catálogo de aplicativos, atualmente apenas globais administradores têm a capacidade de publicar e gerenciá-lo.</span><span class="sxs-lookup"><span data-stu-id="629e7-112">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="629e7-113">(Eventualmente, equipes admins será capaz de fazer isso também.)</span><span class="sxs-lookup"><span data-stu-id="629e7-113">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="629e7-114">Vá para o catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="629e7-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="629e7-115">Inicialize o cliente Microsoft Teams e entrar usando suas credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="629e7-115">Launch the Microsoft Teams client and sign-in using your global admin credentials.</span></span> <span data-ttu-id="629e7-116">No Microsoft Teams Store, selecione nova seção denominada para sua organização específica (neste exemplo, Contoso).</span><span class="sxs-lookup"><span data-stu-id="629e7-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="629e7-117">Usuários em sua organização podem exibir aplicativos no catálogo e instalá-los para equipes dos quais eles são membros.</span><span class="sxs-lookup"><span data-stu-id="629e7-117">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="629e7-119">Adicionar um aplicativo para o catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="629e7-119">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="629e7-120">Do repositório, selecione **carregar um aplicativo personalizado** > **Carregar para a Contoso**.</span><span class="sxs-lookup"><span data-stu-id="629e7-120">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image02.png)

<span data-ttu-id="629e7-122">(Também é possível **Carregar para mim ou Minhas equipes**, que é chamado sideloading, que faz com que o aplicativo disponível somente para suas ou suas equipes selecionadas.)</span><span class="sxs-lookup"><span data-stu-id="629e7-122">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="629e7-123">Navegue até o pacote de aplicativos e selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="629e7-123">Navigate to the app package and select it.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image03.png)

<span data-ttu-id="629e7-125">Quando você voltar ao seu catálogo de aplicativos do inquilino, o novo aplicativo de empresa estará lá.</span><span class="sxs-lookup"><span data-stu-id="629e7-125">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="629e7-126">Lembre-se de que somente você e membros da sua organização têm acesso a esse catálogo de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="629e7-126">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="629e7-127">Atualizar um aplicativo no catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="629e7-127">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="629e7-128">No seu catálogo de aplicativos do inquilino, selecione "**…**"</span><span class="sxs-lookup"><span data-stu-id="629e7-128">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="629e7-129">na parte superior direita do aplicativo que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="629e7-129">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="629e7-130">Navegue até o pacote de aplicativos atualizados e selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="629e7-130">Navigate to the updated app package and select it.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image04.png)

<span data-ttu-id="629e7-132">O aplicativo será ser revisado para a versão 2.0.</span><span class="sxs-lookup"><span data-stu-id="629e7-132">The app will be revised to version 2.0.</span></span> <span data-ttu-id="629e7-133">Você também pode excluir o aplicativo para toda a sua empresa com esse menu.</span><span class="sxs-lookup"><span data-stu-id="629e7-133">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="629e7-134">Use o portal de administração do Office 365 para gerenciar o catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="629e7-134">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="629e7-135">Se você tiver aplicativos que precisam correções de erros, você pode desabilitar temporariamente aplicativos através do portal de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="629e7-135">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="629e7-136">Além das configurações anteriores, há agora uma seção dedicado aos aplicativos da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="629e7-136">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="629e7-137">Você pode escolher quais aplicativos que você deseja habilitar ou desabilitar.</span><span class="sxs-lookup"><span data-stu-id="629e7-137">You can choose which apps you want to enable or disable.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image05.png)

<span data-ttu-id="629e7-139">Isso impede que os usuários interajam com o aplicativo, sem excluir o aplicativo inteiramente.</span><span class="sxs-lookup"><span data-stu-id="629e7-139">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="629e7-140">Esses controles fornecer flexibilidade adicional de administradores e controlar quando a governança de aplicativos em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="629e7-140">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


