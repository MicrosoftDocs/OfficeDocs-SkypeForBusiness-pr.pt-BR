---
title: Configurações de administração para aplicativos no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: Saiba como permitir e habilitar aplicativos no Microsoft Teams, incluindo o carregamento lateral de aplicativos externos.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14c4759505b83d0039fabcaa5eeb03b1530ddf1b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23853139"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="f040c-103">Configurações de administração para aplicativos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f040c-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f040c-104">Os aplicativos consistem em guias, conectores, bots ou qualquer combinação dos três, fornecidos por um serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="f040c-104">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="f040c-105">Existem políticas de administração do Teams que podem ser configuradas no Centro de administração do Office 365 para controlar quais aplicativos externos de terceiros são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f040c-105">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="f040c-106">Essas diretivas permitem especificar quais aplicativos são permitidos e não permitidos, novo comportamento de aplicativo externo, e se os aplicativos do lado do carregamento é permitido.</span><span class="sxs-lookup"><span data-stu-id="f040c-106">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="f040c-107">Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o Centro de administração do Office 365 e abra **Configurações** > **Serviços e complementos** e escolha **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f040c-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="f040c-108">Se você tiver entrado como administrador do Office 365, este link deverá direcioná-lo corretamente:</span><span class="sxs-lookup"><span data-stu-id="f040c-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="f040c-109">Para saber mais sobre as configurações do administrador de aplicativos, veja este vídeo:</span><span class="sxs-lookup"><span data-stu-id="f040c-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="f040c-110">Gerenciando a experiência de aplicativos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f040c-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="f040c-111">Permitir aplicativos externos no Teams</span><span class="sxs-lookup"><span data-stu-id="f040c-111">Allow external apps in Teams</span></span>

<span data-ttu-id="f040c-112">Por padrão, a **permissão de aplicativos externos no Microsoft Teams** está habilitada para todos os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f040c-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="f040c-113">Se você desativar essa opção, todos os aplicativos externos de terceiros serão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="f040c-113">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="f040c-114">Habilitar novos aplicativos externos por padrão</span><span class="sxs-lookup"><span data-stu-id="f040c-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="f040c-115">:trophy: Prática recomendada: Gerenciar aplicativos externos individualmente</span><span class="sxs-lookup"><span data-stu-id="f040c-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="f040c-116">Para ativar alguns aplicativos (e desativar outros), desative **Allow sideloading of external apps** (Permitir o sideload de aplicativos externos).</span><span class="sxs-lookup"><span data-stu-id="f040c-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="f040c-117">Em seguida, desative os aplicativos que você não quer que os usuários utilizem.</span><span class="sxs-lookup"><span data-stu-id="f040c-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="f040c-118">Opcional: desative a opção **Enable new external apps by default** (Habilitar novos aplicativos externos por padrão) (se quiser controlar os novos aplicativos).</span><span class="sxs-lookup"><span data-stu-id="f040c-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="f040c-119">Aplicativos padrão, como as criadas pela Microsoft, não são afetados pela definição **habilitar novos aplicativos externos por padrão** .</span><span class="sxs-lookup"><span data-stu-id="f040c-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="f040c-120">Novos aplicativos estão habilitados por padrão quando lançada pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f040c-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="f040c-121">Quando essa opção está ativada, os usuários podem ativar novos aplicativos assim que eles são adicionados ao catálogo de aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="f040c-121">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="f040c-122">Para abrir o catálogo de aplicativos do Teams, clique em **Loja** na parte inferior do Teams e clique em **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="f040c-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="f040c-123">Para controlar os aplicativos que estão disponíveis, desative essa opção.</span><span class="sxs-lookup"><span data-stu-id="f040c-123">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="f040c-124">Obviamente, se você desativá-la, precisará lembrar de revisar os novos aplicativos periodicamente para que sua organização não perca novos aplicativos bacanas.</span><span class="sxs-lookup"><span data-stu-id="f040c-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="f040c-125">O sideload é a forma de adicionar um aplicativo ao Teams carregando um arquivo zip diretamente para uma equipe.</span><span class="sxs-lookup"><span data-stu-id="f040c-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="f040c-126">O sideload permite testar um aplicativo durante seu desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="f040c-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="f040c-127">E também possibilita a criação de um aplicativo somente para uso interno, compartilhando-o com a sua equipe sem enviá-lo para o catálogo de aplicativos do Teams na Office Store.</span><span class="sxs-lookup"><span data-stu-id="f040c-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="f040c-128">Apenas os proprietários de equipes ou os membros aos quais foram concedidas permissões podem fazer sideload de aplicativos no Teams.</span><span class="sxs-lookup"><span data-stu-id="f040c-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![Captura de tela da seção Apps expandida nas configurações de todo o inquilino.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="f040c-130">Criação e upload de pacotes de aplicativos</span><span class="sxs-lookup"><span data-stu-id="f040c-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="f040c-131">Para saber mais sobre os aplicativos, consulte [desenvolver aplicativos para equipes](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="f040c-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



