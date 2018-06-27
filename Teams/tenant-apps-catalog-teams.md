---
title: Publicar aplicativos para o catálogo de aplicativos do locatário equipes da Microsoft
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Orientação para a publicação de aplicativos no catálogo de aplicativos do Microsoft equipes inquilino.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 298caf3cee6fe6af38f22ef9ac7dd85991fd6dba
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2018
ms.locfileid: "20050448"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="67624-103">Publicar aplicativos para o catálogo de aplicativos do locatário equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="67624-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

> [!IMPORTANT]
> <span data-ttu-id="67624-104">Esta página descreve um recurso de pré-lançamento e contém conteúdo preliminar que pode ser alterado substancialmente antes do lançamento.</span><span class="sxs-lookup"><span data-stu-id="67624-104">This page describes a pre-release feature and contains preliminary content that might change substantially before it is released.</span></span> <span data-ttu-id="67624-105">Qualquer capturas de tela são espaços reservados e podem parecer diferentes de que você vê.</span><span class="sxs-lookup"><span data-stu-id="67624-105">Any screenshots are placeholders and might look different than what you see.</span></span>

<span data-ttu-id="67624-106">Você pode usar o catálogo de aplicativos do Microsoft equipes locatário para testar e distribuir aplicativos de linha de negócios para sua organização.</span><span class="sxs-lookup"><span data-stu-id="67624-106">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="67624-107">O catálogo de aplicativos do inquilino de equipes permite que você distribuir seus aplicativos de linha de negócios que foram criados especificamente para sua organização e que você depende para concluem as funções essenciais aos negócios para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="67624-107">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="67624-108">Você pode publicar aplicativos para o catálogo de aplicativos do locatário equipes diretamente do cliente equipes.</span><span class="sxs-lookup"><span data-stu-id="67624-108">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="67624-109">Publicar um aplicativo para o catálogo de aplicativos do locatário do cliente equipes</span><span class="sxs-lookup"><span data-stu-id="67624-109">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="67624-110">Obtenha um pacote de aplicativos de equipes</span><span class="sxs-lookup"><span data-stu-id="67624-110">Get a Teams app package</span></span>

<span data-ttu-id="67624-111">Um pacote de aplicativos de equipes é criado usando o [Studio de App equipes](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="67624-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="67624-112">Depois que você tiver o pacote de aplicativos, você pode adicioná-lo ao catálogo de aplicativos do enterprise.</span><span class="sxs-lookup"><span data-stu-id="67624-112">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="67624-113">Enquanto todos os usuários no inquilino podem exibir o catálogo de aplicativos, apenas administradores têm a capacidade de gerenciar a ele.</span><span class="sxs-lookup"><span data-stu-id="67624-113">While all users in the tenant can view the app catalog, only admins have the ability to manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="67624-114">Vá para o catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="67624-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="67624-115">No Microsoft Teams Store, selecione nova seção denominada para sua organização específica (neste exemplo, Contoso).</span><span class="sxs-lookup"><span data-stu-id="67624-115">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="67624-116">Usuários em sua organização podem exibir aplicativos no catálogo e instalá-los para equipes dos quais eles são membros.</span><span class="sxs-lookup"><span data-stu-id="67624-116">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="67624-118">Adicionar um aplicativo para o catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="67624-118">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="67624-119">Do repositório, selecione **carregar um aplicativo personalizado** > **Carregar para a Contoso**.</span><span class="sxs-lookup"><span data-stu-id="67624-119">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image02.png)

<span data-ttu-id="67624-121">(Também é possível **Carregar para mim ou Minhas equipes**, que é chamado sideloading, que faz com que o aplicativo disponível somente para suas ou suas equipes selecionadas.)</span><span class="sxs-lookup"><span data-stu-id="67624-121">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="67624-122">Navegue até o pacote de aplicativos e selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="67624-122">Navigate to the app package and select it.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image03.png)

<span data-ttu-id="67624-124">Quando você voltar ao seu catálogo de aplicativos do inquilino, o novo aplicativo de empresa estará lá.</span><span class="sxs-lookup"><span data-stu-id="67624-124">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="67624-125">Lembre-se de que somente você e membros da sua organização têm acesso a esse catálogo de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="67624-125">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="67624-126">Atualizar um aplicativo no catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="67624-126">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="67624-127">No seu catálogo de aplicativos do inquilino, selecione "**…**"</span><span class="sxs-lookup"><span data-stu-id="67624-127">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="67624-128">na parte superior direita do aplicativo que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="67624-128">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="67624-129">Navegue até o pacote de aplicativos atualizados e selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="67624-129">Navigate to the updated app package and select it.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image04.png)

<span data-ttu-id="67624-131">O aplicativo será ser revisado para a versão 2.0.</span><span class="sxs-lookup"><span data-stu-id="67624-131">The app will be revised to version 2.0.</span></span> <span data-ttu-id="67624-132">Você também pode excluir o aplicativo para toda a sua empresa com esse menu.</span><span class="sxs-lookup"><span data-stu-id="67624-132">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="67624-133">Use o portal de administração do Office 365 para gerenciar o catálogo de aplicativos do locatário</span><span class="sxs-lookup"><span data-stu-id="67624-133">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="67624-134">Se você tiver aplicativos que precisam correções de erros, você pode desabilitar temporariamente aplicativos através do portal de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="67624-134">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="67624-135">Além das configurações anteriores, há agora uma seção dedicado aos aplicativos da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="67624-135">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="67624-136">Você pode escolher quais aplicativos que você deseja habilitar ou desabilitar.</span><span class="sxs-lookup"><span data-stu-id="67624-136">You can choose which apps you want to enable or disable.</span></span>

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image05.png)

<span data-ttu-id="67624-138">Isso impede que os usuários interajam com o aplicativo, sem excluir o aplicativo inteiramente.</span><span class="sxs-lookup"><span data-stu-id="67624-138">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="67624-139">Esses controles fornecer flexibilidade adicional de administradores e controlar quando a governança de aplicativos em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="67624-139">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


