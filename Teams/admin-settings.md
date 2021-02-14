---
title: Configurações de administração para aplicativos no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Saiba mais sobre as políticas e configurações que você pode usar para gerenciar aplicativos para sua organização no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb824c7082679591b3fa39a1c8a4b13152e0cc75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532518"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="585c1-103">Configurações de administração para aplicativos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="585c1-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="585c1-104">Os aplicativos oferecem ferramentas de primeira qualidade para sua organização para obter mais informações sobre o Teams.</span><span class="sxs-lookup"><span data-stu-id="585c1-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="585c1-105">Esses aplicativos combinam a funcionalidade de guias, extensões de mensagens, conectores e bots fornecidos pela Microsoft, criado por terceiros ou por desenvolvedores em sua organização.</span><span class="sxs-lookup"><span data-stu-id="585c1-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="585c1-106">Você gerencia aplicativos para sua organização nos **aplicativos do Teams** no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="585c1-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="585c1-107">(Consulte [Usar funções de administrador do Teams para gerenciar o Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) para ler sobre como obter funções e permissões de administrador.) Por exemplo, você pode permitir ou bloquear aplicativos no nível da organização, definir políticas para controlar quais aplicativos estão disponíveis para os usuários do Teams e personalizar o Teams fixando os aplicativos mais importantes para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="585c1-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="585c1-108">Estamos constantemente melhorando a experiência do aplicativo no Teams e adicionando recursos e funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="585c1-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="585c1-109">Ao longo do tempo, criaremos recursos adicionais de gerenciamento de aplicativos, portanto, verifique novamente as informações mais atualizadas sobre políticas de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="585c1-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="585c1-110">Gerenciar aplicativos</span><span class="sxs-lookup"><span data-stu-id="585c1-110">Manage apps</span></span>

<span data-ttu-id="585c1-111">Use a **página Gerenciar aplicativos** para exibir e gerenciar todos os aplicativos do Teams no catálogo de aplicativos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="585c1-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="585c1-112">Você pode ver o status no nível da organização e as propriedades dos aplicativos, bloquear ou permitir aplicativos no nível da organização, carregar novos aplicativos personalizados para o catálogo de locatários e gerenciar configurações de aplicativos em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="585c1-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="585c1-113">A **página** Gerenciar aplicativos oferece uma exibição de todos os aplicativos disponíveis no catálogo de locatários, fornecendo as informações necessárias para decidir quais aplicativos permitir ou bloquear em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="585c1-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="585c1-114">Em seguida, [você](#app-permission-policies)pode usar políticas de permissão de [aplicativo,](#app-setup-policies)políticas de configuração de aplicativos e políticas e configurações personalizadas do aplicativo para configurar a experiência do aplicativo para usuários [específicos](#custom-app-policies-and-settings) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="585c1-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="585c1-115">Para saber mais, confira [Gerenciar aplicativos no Teams.](manage-apps.md)</span><span class="sxs-lookup"><span data-stu-id="585c1-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="585c1-116">Políticas de permissão do aplicativo</span><span class="sxs-lookup"><span data-stu-id="585c1-116">App permission policies</span></span>

<span data-ttu-id="585c1-117">Com as políticas de permissão do aplicativo, você pode controlar quais aplicativos estão disponíveis para usuários específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="585c1-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="585c1-118">Você pode permitir ou bloquear todos os aplicativos ou aplicativos específicos publicados pela Microsoft, terceiros e sua organização.</span><span class="sxs-lookup"><span data-stu-id="585c1-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="585c1-119">Por exemplo, você pode usar políticas de permissão de aplicativo para:</span><span class="sxs-lookup"><span data-stu-id="585c1-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="585c1-120">Roll out gradualmente new third-party or custom built apps to specific users.</span><span class="sxs-lookup"><span data-stu-id="585c1-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="585c1-121">Simplifique a experiência do usuário, especialmente quando você começa a lançar o Teams em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="585c1-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="585c1-122">Para saber mais, acesse [Gerenciar políticas de permissão do aplicativo no Teams.](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="585c1-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="585c1-123">Políticas de configuração de aplicativos</span><span class="sxs-lookup"><span data-stu-id="585c1-123">App setup policies</span></span>

<span data-ttu-id="585c1-124">As políticas de configuração de aplicativos permitem personalizar a experiência do aplicativo para os usuários.</span><span class="sxs-lookup"><span data-stu-id="585c1-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="585c1-125">Escolha os aplicativos que deseja fixar na barra de aplicativos nos clientes do Teams e na ordem em que eles aparecem, na Web, na área de trabalho e em clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="585c1-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="585c1-126">Veja alguns exemplos de como você pode usar políticas de configuração de aplicativos:</span><span class="sxs-lookup"><span data-stu-id="585c1-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="585c1-127">Impulsionar a conscientização e a adoção dos principais aplicativos.</span><span class="sxs-lookup"><span data-stu-id="585c1-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="585c1-128">Por exemplo, fixe um aplicativo personalizado de recrutamento e gerenciamento de talentos para os usuários em sua equipe de RH.</span><span class="sxs-lookup"><span data-stu-id="585c1-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="585c1-129">Fixe seletivamente os principais recursos do Teams, como Chat, Teams e Chamada.</span><span class="sxs-lookup"><span data-stu-id="585c1-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="585c1-130">Isso pode ajudar a garantir que os usuários sejam envolvidos em atividades específicas no Teams.</span><span class="sxs-lookup"><span data-stu-id="585c1-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="585c1-131">Para saber mais, confira Gerenciar [políticas de configuração de aplicativos no Teams.](teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="585c1-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="585c1-132">Configurações e políticas de aplicativos personalizados</span><span class="sxs-lookup"><span data-stu-id="585c1-132">Custom app policies and settings</span></span>

<span data-ttu-id="585c1-133">O Teams permite que os desenvolvedores em sua organização criem, testem e implantem aplicativos personalizados para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="585c1-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="585c1-134">Os aplicativos personalizados podem ser adicionados ao Teams carregando um pacote de aplicativos em um arquivo .zip diretamente em uma equipe ou no contexto pessoal.</span><span class="sxs-lookup"><span data-stu-id="585c1-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="585c1-135">Você pode usar políticas de configuração de aplicativos para controlar quem em sua organização pode carregar aplicativos personalizados.</span><span class="sxs-lookup"><span data-stu-id="585c1-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="585c1-136">Você também pode definir configurações de toda a organização para controlar se os usuários podem interagir com aplicativos personalizados específicos.</span><span class="sxs-lookup"><span data-stu-id="585c1-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="585c1-137">Para saber mais, vá para Gerenciar políticas e configurações de [aplicativos personalizadas no Teams.](teams-custom-app-policies-and-settings.md)</span><span class="sxs-lookup"><span data-stu-id="585c1-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
