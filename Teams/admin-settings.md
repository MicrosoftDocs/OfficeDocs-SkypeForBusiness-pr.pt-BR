---
title: "Configurações de administração para aplicativos no Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Saiba como permitir e habilitar aplicativos no Microsoft Teams, incluindo o carregamento lateral de aplicativos externos.
ms.openlocfilehash: ca969e073cf35309b65aeedf93acda31d388629c
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2017
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="b80c9-103">Configurações de administração para aplicativos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b80c9-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="b80c9-104">Nesta seção, nos referimos a guias, conectores e bots, ou qualquer combinação desses recursos, fornecidos por um único serviço de terceiros, como os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b80c9-104">In this section, we refer to tabs, connectors, and bots, or any combination of these capabilities, provided by a single third-party service as Apps.</span></span> <span data-ttu-id="b80c9-105">Existem políticas de administração que podem ser configuradas no Portal de Administração do Office 365 para controlar quais aplicativos externos de terceiros serão permitidos.</span><span class="sxs-lookup"><span data-stu-id="b80c9-105">There are Admin policies that can be configured in the Office 365 Admin Portal to control which external third-party apps are allowed.</span></span> <span data-ttu-id="b80c9-106">Essas políticas permitem que você especifique quais aplicativos são permitidos ou não, o comportamento de um novo aplicativo externo, bem como se o carregamento lateral de aplicativos é permitido.</span><span class="sxs-lookup"><span data-stu-id="b80c9-106">These policies let you specify which apps are allowed and disallowed, new external App behavior, as well as whether side-loading apps is allowed.</span></span>

<span data-ttu-id="b80c9-107">**Permitir aplicativos externos no Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b80c9-107">**Allow external apps in Microsoft Teams**</span></span>

<span data-ttu-id="b80c9-108">Por padrão, a permissão de aplicativos externos no Microsoft Teams está habilitada para todos os aplicativos selecionados.</span><span class="sxs-lookup"><span data-stu-id="b80c9-108">By default, allow external apps in Microsoft Teams is enabled with all apps selected.</span></span> <span data-ttu-id="b80c9-109">Ao tornar essa política **“Desativada”**, todos os aplicativos externos de terceiros são desabilitados.</span><span class="sxs-lookup"><span data-stu-id="b80c9-109">When turning this policy to **“Off”**, then all external third-party apps are disabled.</span></span> <span data-ttu-id="b80c9-110">Você pode aumentar o nível de detalhes, permitir que aplicativos externos sejam habilitados e desmarcar individualmente os aplicativos que deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="b80c9-110">You can get more granular and allow external apps to be enabled and uncheck specific apps that you want to disable on an individual basis.</span></span>

<span data-ttu-id="b80c9-111">**Habilitar novos aplicativos externos por padrão**</span><span class="sxs-lookup"><span data-stu-id="b80c9-111">**Enable new external apps by default**</span></span>

<span data-ttu-id="b80c9-112">Sempre que novos aplicativos forem enviados ao catálogo de aplicativos do Teams, isso muda o controle de disponibilidade para os usuários neste locatário.</span><span class="sxs-lookup"><span data-stu-id="b80c9-112">Whenever new apps are submitted to the Teams App Catalog, this switch controls whether they are available for users in this tenant.</span></span> <span data-ttu-id="b80c9-113">Por padrão, essa política está definida como **“Ativada”**, o que permite que os usuários tenham acesso aos aplicativos assim que forem adicionados ao catálogo de aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="b80c9-113">By default, this policy is set to **“On”** which allows users to have access to apps as soon as they are added to the Team’s app catalog.</span></span> <span data-ttu-id="b80c9-114">Se preferir validar os aplicativos antes de permitir sua utilização no Teams, defina essa política como **Desativada.**</span><span class="sxs-lookup"><span data-stu-id="b80c9-114">If you would prefer to validate apps before allowing them to be utilized in Teams, then set this policy to **Off.**</span></span> <span data-ttu-id="b80c9-115">Apenas lembre-se de que, se definir essa política como **“Desativada”,** você deve avaliar regularmente os aplicativos adicionados recentemente para garantir que seus usuários se beneficiem das últimas inovações e inclusões de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b80c9-115">Just remember, if you set this to **"Off",** you should evaluate newly added apps on a regular basis to make sure your users benefit from the latest innovations and additions of apps.</span></span>

<span data-ttu-id="b80c9-116">**Permitir o carregamento lateral de aplicativos externos**</span><span class="sxs-lookup"><span data-stu-id="b80c9-116">**Allow side-loading of external apps**</span></span>

<span data-ttu-id="b80c9-117">Apenas os proprietários do Teams e os membros aos quais foram concedidas permissões podem fazer o carregamento lateral de aplicativos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b80c9-117">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams.</span></span> <span data-ttu-id="b80c9-118">Alguns dos benefícios de fazer o carregamento lateral de aplicativos no Microsoft Teams são:</span><span class="sxs-lookup"><span data-stu-id="b80c9-118">Some benefits of side-loading apps into Microsoft Teams are:</span></span>

-   <span data-ttu-id="b80c9-119">Capacidade de testar os aplicativos antes de enviá-los à Microsoft</span><span class="sxs-lookup"><span data-stu-id="b80c9-119">Ability to test apps prior to submitting to Microsoft</span></span>

-   <span data-ttu-id="b80c9-120">Oferecer aplicativos diretamente aos usuários dentro da sua organização, sem a necessidade de enviar para a Office Store.</span><span class="sxs-lookup"><span data-stu-id="b80c9-120">Provide apps directly to users within your organization without having to submit to the Office Store.</span></span>

<span data-ttu-id="b80c9-121">Para saber mais sobre o carregamento lateral de aplicativos no Microsoft Teams, acesse: [Carregamento lateral de aplicativos em uma equipe](https://go.microsoft.com/fwlink/?linkid=854631).</span><span class="sxs-lookup"><span data-stu-id="b80c9-121">To learn more about side loading apps into Microsoft Teams, visit: [Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631).</span></span>

![Captura de tela da seção de Aplicativos das configurações do Microsoft Teams.](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
