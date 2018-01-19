---
title: "Configurações de administração para aplicativos no Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Saiba como permitir e habilitar aplicativos no Microsoft Teams, incluindo o carregamento lateral de aplicativos externos.
ms.openlocfilehash: 4265866bb346da1aa773d337d02fc1c11149f579
ms.sourcegitcommit: ee1c79b6d6d73e5fc702fe55b9e5aee8a7aae793
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="75fb9-103">Configurações de administração para aplicativos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="75fb9-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="75fb9-104">Os aplicativos consistem em guias, conectores, bots ou qualquer combinação dos três, fornecidos por um serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="75fb9-104">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="75fb9-105">Existem políticas de administração que podem ser configuradas no Centro de administração do Office 365 para controlar quais aplicativos externos de terceiros são permitidos.</span><span class="sxs-lookup"><span data-stu-id="75fb9-105">There are Admin policies that can be configured in the Office 365 Admin Portal to control which external third-party apps are allowed.</span></span> <span data-ttu-id="75fb9-106">Essas políticas permitem especificar quais aplicativos são permitidos ou não, o comportamento do novo aplicativo externo e se o sideload de aplicativos é permitido.</span><span class="sxs-lookup"><span data-stu-id="75fb9-106">These policies let you specify which apps are allowed and disallowed, new external App behavior, as well as whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="75fb9-107">Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o Centro de administração do Office 365 e abra **Configurações** > **Serviços e complementos** e escolha **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="75fb9-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="75fb9-108">Se você tiver entrado como administrador do Office 365, este link deverá direcioná-lo corretamente:</span><span class="sxs-lookup"><span data-stu-id="75fb9-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> <span data-ttu-id="75fb9-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="75fb9-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span> 

<span data-ttu-id="75fb9-110">**Permitir aplicativos externos no Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="75fb9-110">**Allow external apps in Microsoft Teams**</span></span>

<span data-ttu-id="75fb9-111">Por padrão, a permissão de aplicativos externos no Microsoft Teams está habilitada para todos os aplicativos selecionados.</span><span class="sxs-lookup"><span data-stu-id="75fb9-111">By default, allow external apps in Microsoft Teams is enabled with all apps selected.</span></span> <span data-ttu-id="75fb9-112">Ao tornar essa política **“Desativada”**, todos os aplicativos externos de terceiros são desabilitados.</span><span class="sxs-lookup"><span data-stu-id="75fb9-112">When turning this policy to **“Off”**, then all external third-party apps are disabled.</span></span> <span data-ttu-id="75fb9-113">Você pode aumentar o nível de detalhes, permitir que aplicativos externos sejam habilitados e desmarcar individualmente os aplicativos que deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="75fb9-113">You can get more granular and allow external apps to be enabled and uncheck specific apps that you want to disable on an individual basis.</span></span>

<span data-ttu-id="75fb9-114">**Habilitar novos aplicativos externos por padrão**</span><span class="sxs-lookup"><span data-stu-id="75fb9-114">**Enable new external apps by default**</span></span>

<span data-ttu-id="75fb9-115">Sempre que novos aplicativos forem enviados ao catálogo de aplicativos do Teams, isso muda o controle de disponibilidade para os usuários neste locatário.</span><span class="sxs-lookup"><span data-stu-id="75fb9-115">Whenever new apps are submitted to the Teams App Catalog, this switch controls whether they are available for users in this tenant.</span></span> <span data-ttu-id="75fb9-116">Por padrão, essa política está definida como **“Ativada”**, o que permite que os usuários tenham acesso aos aplicativos assim que forem adicionados ao catálogo de aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="75fb9-116">By default, this policy is set to **“On”** which allows users to have access to apps as soon as they are added to the Team’s app catalog.</span></span> <span data-ttu-id="75fb9-117">Se preferir validar os aplicativos antes de permitir sua utilização no Teams, defina essa política como **Desativada.**</span><span class="sxs-lookup"><span data-stu-id="75fb9-117">If you would prefer to validate apps before allowing them to be utilized in Teams, then set this policy to **Off.**</span></span> <span data-ttu-id="75fb9-118">Apenas lembre-se de que, se definir essa política como **“Desativada”,** você deve avaliar regularmente os aplicativos adicionados recentemente para garantir que seus usuários se beneficiem das últimas inovações e inclusões de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="75fb9-118">Just remember, if you set this to **"Off",** you should evaluate newly added apps on a regular basis to make sure your users benefit from the latest innovations and additions of apps.</span></span>

<span data-ttu-id="75fb9-119">**Permitir o carregamento lateral de aplicativos externos**</span><span class="sxs-lookup"><span data-stu-id="75fb9-119">**Allow side-loading of external apps**</span></span>

<span data-ttu-id="75fb9-120">Apenas os proprietários do Teams e os membros aos quais foram concedidas permissões podem fazer o carregamento lateral de aplicativos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="75fb9-120">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams.</span></span> <span data-ttu-id="75fb9-121">Alguns dos benefícios de fazer o carregamento lateral de aplicativos no Microsoft Teams são:</span><span class="sxs-lookup"><span data-stu-id="75fb9-121">Some benefits of side-loading apps into Microsoft Teams are:</span></span>

-   <span data-ttu-id="75fb9-122">Capacidade de testar os aplicativos antes de enviá-los à Microsoft</span><span class="sxs-lookup"><span data-stu-id="75fb9-122">Ability to test apps prior to submitting to Microsoft</span></span>

-   <span data-ttu-id="75fb9-123">Oferecer aplicativos diretamente aos usuários dentro da sua organização, sem a necessidade de enviar para a Office Store.</span><span class="sxs-lookup"><span data-stu-id="75fb9-123">Provide apps directly to users within your organization without having to submit to the Office Store.</span></span>

<span data-ttu-id="75fb9-124">Para saber mais sobre o carregamento lateral de aplicativos no Microsoft Teams, acesse: [Carregamento lateral de aplicativos em uma equipe](https://go.microsoft.com/fwlink/?linkid=854631).</span><span class="sxs-lookup"><span data-stu-id="75fb9-124">To learn more about side loading apps into Microsoft Teams, visit: [Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631).</span></span>

![Captura de tela da seção de Aplicativos das configurações do Microsoft Teams.](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
