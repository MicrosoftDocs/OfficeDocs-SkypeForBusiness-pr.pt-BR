---
title: Gerenciar o Microsoft equipes privados App Store
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Diretrizes para o gerenciamento de aplicativos no Microsoft Teams privados app store.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6aaa763c423d7756808856706375f96f99224b9e
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2018
ms.locfileid: "19694885"
---
<a name="publish-apps-to-the-microsoft-teams-private-app-store"></a><span data-ttu-id="fdbff-103">Publicar aplicativos para o Microsoft equipes privados App Store</span><span class="sxs-lookup"><span data-stu-id="fdbff-103">Publish Apps to the Microsoft Teams Private App Store</span></span>
============================================

> [!IMPORTANT]
> <span data-ttu-id="fdbff-104">Esta página descreve um recurso de pré-lançamento e contém conteúdo preliminar que pode ser alterado substancialmente antes do lançamento.</span><span class="sxs-lookup"><span data-stu-id="fdbff-104">This page describes a pre-release feature and contains preliminary content that might change substantially before it is released.</span></span> <span data-ttu-id="fdbff-105">Qualquer capturas de tela são espaços reservados e podem parecer diferentes de que você vê.</span><span class="sxs-lookup"><span data-stu-id="fdbff-105">Any screenshots are placeholders and might look different than what you see.</span></span>

<span data-ttu-id="fdbff-106">Você pode usar o Microsoft Teams Private App Store para testar e distribuir aplicativos de linha de negócios para sua organização.</span><span class="sxs-lookup"><span data-stu-id="fdbff-106">You can use the Microsoft Teams Private App Store to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="fdbff-107">Microsoft Teams Private App Store permite que você distribuir seus aplicativos de linha de negócios que foram criados especificamente para sua organização e que você depende para concluem as funções essenciais aos negócios para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="fdbff-107">The Microsoft Teams Private App Store lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="fdbff-108">Há dois métodos para publicar aplicativos para equipes privados App Store:</span><span class="sxs-lookup"><span data-stu-id="fdbff-108">There are two methods to publish apps to the Teams Private App Store:</span></span>
- <span data-ttu-id="fdbff-109">Diretamente a partir do cliente de equipes</span><span class="sxs-lookup"><span data-stu-id="fdbff-109">Directly from the Teams client</span></span> 
- <span data-ttu-id="fdbff-110">Cmdlets que aproveitam APIs do Microsoft Graph (esse método não ainda disponível para visualização.)</span><span class="sxs-lookup"><span data-stu-id="fdbff-110">Cmdlets that leverage Microsoft Graph APIs (This method is not yet available for preview.)</span></span>

## <a name="publish-an-app-to-the-teams-private-app-store-from-the-teams-client"></a><span data-ttu-id="fdbff-111">Publicar um aplicativo para equipes privados App Store do cliente equipes</span><span class="sxs-lookup"><span data-stu-id="fdbff-111">Publish an App to the Teams Private App Store from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="fdbff-112">Obtenha um pacote de aplicativos de equipes</span><span class="sxs-lookup"><span data-stu-id="fdbff-112">Get a Teams app package</span></span>

<span data-ttu-id="fdbff-113">Um pacote de aplicativos de equipes é criado usando o [Studio de App equipes](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="fdbff-113">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="fdbff-114">Depois que você tiver o pacote de aplicativos, você pode adicioná-lo ao catálogo de aplicativos do enterprise.</span><span class="sxs-lookup"><span data-stu-id="fdbff-114">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="fdbff-115">Enquanto todos os usuários no inquilino podem exibir o catálogo de aplicativos, apenas administradores têm a capacidade de gerenciar a ele.</span><span class="sxs-lookup"><span data-stu-id="fdbff-115">While all users in the tenant can view the app catalog, only admins have the ability to manage it.</span></span>

### <a name="go-to-the-teams-private-app-store"></a><span data-ttu-id="fdbff-116">Vá para equipes privados App Store</span><span class="sxs-lookup"><span data-stu-id="fdbff-116">Go to the Teams Private App Store</span></span>

<span data-ttu-id="fdbff-117">No Microsoft Teams Store, selecione nova seção denominada para sua organização específica (neste exemplo, Contoso).</span><span class="sxs-lookup"><span data-stu-id="fdbff-117">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="fdbff-118">Usuários em sua organização podem exibir aplicativos no catálogo e instalá-los para equipes dos quais eles são membros.</span><span class="sxs-lookup"><span data-stu-id="fdbff-118">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-teams-private-app-store"></a><span data-ttu-id="fdbff-120">Adicionar um aplicativo para equipes privados App Store</span><span class="sxs-lookup"><span data-stu-id="fdbff-120">Add an app to the Teams Private App Store</span></span>

<span data-ttu-id="fdbff-121">Do repositório, selecione **carregar um aplicativo personalizado** > **Carregar para a Contoso**.</span><span class="sxs-lookup"><span data-stu-id="fdbff-121">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image02.png)

<span data-ttu-id="fdbff-123">(Também é possível **Carregar para mim ou Minhas equipes**, que é chamado sideloading, que faz com que o aplicativo disponível somente para suas ou suas equipes selecionadas.)</span><span class="sxs-lookup"><span data-stu-id="fdbff-123">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="fdbff-124">Navegue até o pacote de aplicativos e selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="fdbff-124">Navigate to the app package and select it.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image03.png)

<span data-ttu-id="fdbff-126">Quando você voltar ao seu catálogo de aplicativos, o novo aplicativo de empresa estará lá.</span><span class="sxs-lookup"><span data-stu-id="fdbff-126">When you go back to your app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="fdbff-127">Lembre-se de que somente você e membros da sua organização têm acesso a esse catálogo de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fdbff-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-teams-private-app-store"></a><span data-ttu-id="fdbff-128">Atualizar um aplicativo na App Store equipes privado</span><span class="sxs-lookup"><span data-stu-id="fdbff-128">Update an app in the Teams Private App Store</span></span>

1. <span data-ttu-id="fdbff-129">No seu catálogo de aplicativos, selecione "**…**"</span><span class="sxs-lookup"><span data-stu-id="fdbff-129">From your app catalog, select “**…**”</span></span> <span data-ttu-id="fdbff-130">na parte superior direita do aplicativo que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="fdbff-130">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="fdbff-131">Navegue até o pacote de aplicativos atualizados e selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="fdbff-131">Navigate to the updated app package and select it.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image04.png)

<span data-ttu-id="fdbff-133">O aplicativo será ser revisado para a versão 2.0.</span><span class="sxs-lookup"><span data-stu-id="fdbff-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="fdbff-134">Você também pode excluir o aplicativo para toda a sua empresa com esse menu.</span><span class="sxs-lookup"><span data-stu-id="fdbff-134">You also delete the app for your entire company from this menu.</span></span>

## <a name="manage-the-teams-private-app-store-by-using-cmdlets-and-microsoft-graph-apis"></a><span data-ttu-id="fdbff-135">Gerenciar equipes privados App Store usando cmdlets e APIs do Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="fdbff-135">Manage the Teams Private App Store by using cmdlets and Microsoft Graph APIs</span></span>

<span data-ttu-id="fdbff-136">Este método ainda não está disponível para visualização.</span><span class="sxs-lookup"><span data-stu-id="fdbff-136">This method is not yet available for preview.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-private-apps"></a><span data-ttu-id="fdbff-137">Usar o portal de administração do Office 365 para gerenciar aplicativos de privado</span><span class="sxs-lookup"><span data-stu-id="fdbff-137">Use the Office 365 admin portal to manage Private Apps</span></span>

<span data-ttu-id="fdbff-138">Se você tiver aplicativos que precisam correções de erros, você pode desabilitar temporariamente aplicativos através do portal de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdbff-138">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="fdbff-139">Além das configurações anteriores, há agora uma seção dedicado aos aplicativos da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="fdbff-139">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="fdbff-140">Você pode escolher quais aplicativos que você deseja habilitar ou desabilitar.</span><span class="sxs-lookup"><span data-stu-id="fdbff-140">You can choose which apps you want to enable or disable.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image05.png)

<span data-ttu-id="fdbff-142">Isso impede que os usuários interajam com o aplicativo, sem excluir o aplicativo inteiramente.</span><span class="sxs-lookup"><span data-stu-id="fdbff-142">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="fdbff-143">Esses controles fornecer flexibilidade adicional de administradores e controlar quando a governança de aplicativos em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="fdbff-143">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


