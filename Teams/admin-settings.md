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
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.apppolicies.adminsettings
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69b14984ac9acca71a7729615cde2280b064ff9b
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2019
ms.locfileid: "30493561"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="8cc1a-103">Configurações de administração para aplicativos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cc1a-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="8cc1a-104">Aplicativos são guias, conectores, bots ou qualquer combinação destas três, fornecido pelo equipes (apps primários e também conhecido como aplicativos padrão) ou por um terceiro (também conhecido como aplicativos externos).</span><span class="sxs-lookup"><span data-stu-id="8cc1a-104">Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, and also known as default apps) or by a third-party (also known as external apps).</span></span> <span data-ttu-id="8cc1a-105">No Centro de administração do Microsoft 365, você pode habilitar e desabilitar aplicativos padrão e definir configurações para controlar aplicativos externos.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-105">In the Microsoft 365 admin center, you can enable and disable default apps and configure settings to control external apps.</span></span> <span data-ttu-id="8cc1a-106">Essas configurações permitem especificar quais aplicativos externos são permitidos e não permitidos, novo comportamento de aplicativo externo, e se os aplicativos do lado do carregamento é permitido.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-106">These settings let you specify which external apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

 <span data-ttu-id="8cc1a-107">Para gerenciar as configurações de administração para aplicativos em equipes, vá para o Centro de administração do Microsoft 365 e escolha **configurações** > **Serviços & complementos** > **Equipes da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-107">To manage admin settings for apps in Teams, go to the Microsoft 365 admin center and choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="8cc1a-108">Se você tiver entrado como administrador do Office 365, esse link deverá levá-lo corretamente ao local correto:</span><span class="sxs-lookup"><span data-stu-id="8cc1a-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="8cc1a-109">Para saber mais sobre as configurações do administrador de aplicativos, veja este vídeo:</span><span class="sxs-lookup"><span data-stu-id="8cc1a-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="8cc1a-110">Gerenciando a experiência de aplicativos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cc1a-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="8cc1a-111">Permitir aplicativos externos no Teams</span><span class="sxs-lookup"><span data-stu-id="8cc1a-111">Allow external apps in Teams</span></span>

<span data-ttu-id="8cc1a-112">Por padrão, a **permissão de aplicativos externos no Microsoft Teams** está habilitada para todos os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="8cc1a-113">Se você desativar essa configuração, todos os aplicativos de terceiros externos serão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-113">If you turn off this setting, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="8cc1a-114">Habilitar novos aplicativos externos por padrão</span><span class="sxs-lookup"><span data-stu-id="8cc1a-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="8cc1a-115">:trophy: Prática recomendada: Gerenciar aplicativos externos individualmente</span><span class="sxs-lookup"><span data-stu-id="8cc1a-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="8cc1a-116">Para ativar alguns aplicativos (e desativar outros), desative **Allow sideloading of external apps** (Permitir o sideload de aplicativos externos).</span><span class="sxs-lookup"><span data-stu-id="8cc1a-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="8cc1a-117">Em seguida, desative os aplicativos que você não quer que os usuários utilizem.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="8cc1a-118">Opcional: desative a opção **Enable new external apps by default** (Habilitar novos aplicativos externos por padrão) (se quiser controlar os novos aplicativos).</span><span class="sxs-lookup"><span data-stu-id="8cc1a-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="8cc1a-119">Aplicativos padrão, como as criadas pela Microsoft, não são afetados pela definição **habilitar novos aplicativos externos por padrão** .</span><span class="sxs-lookup"><span data-stu-id="8cc1a-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="8cc1a-120">Novos aplicativos estão habilitados por padrão quando lançada pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="8cc1a-121">Quando essa configuração é ativada, os usuários podem ativar novos aplicativos assim que são adicionados ao catálogo de aplicativos de equipes.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-121">When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="8cc1a-122">Para abrir o catálogo de aplicativos do Teams, clique em **Loja** na parte inferior do Teams e clique em **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="8cc1a-123">Se você quiser controlar quais aplicativos estão disponíveis, desative esta configuração.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-123">If you want to control which apps are available, turn off this setting.</span></span> <span data-ttu-id="8cc1a-124">Obviamente, se você desativá-la, precisará lembrar de revisar os novos aplicativos periodicamente para que sua organização não perca novos aplicativos bacanas.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="8cc1a-125">O sideload é a forma de adicionar um aplicativo ao Teams carregando um arquivo zip diretamente para uma equipe.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="8cc1a-126">O sideload permite testar um aplicativo durante seu desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="8cc1a-127">E também possibilita a criação de um aplicativo somente para uso interno, compartilhando-o com a sua equipe sem enviá-lo para o catálogo de aplicativos do Teams na Office Store.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="8cc1a-128">Apenas os proprietários de equipes ou os membros aos quais foram concedidas permissões podem fazer sideload de aplicativos no Teams.</span><span class="sxs-lookup"><span data-stu-id="8cc1a-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

<span data-ttu-id="8cc1a-129">![Captura de tela da seção de aplicativos externos expandida.] (media/teams-tenant-wide-settings-external-apps.png "Captura de tela da seção aplicativos externos expandida mostrando aplicativos externos")</span><span class="sxs-lookup"><span data-stu-id="8cc1a-129">![Screen shot of the expanded External Apps section.](media/teams-tenant-wide-settings-external-apps.png "Screen shot of the expanded External Apps section showing external apps")</span></span>

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="8cc1a-130">Criação e upload de pacotes de aplicativos</span><span class="sxs-lookup"><span data-stu-id="8cc1a-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="8cc1a-131">Para saber mais sobre os aplicativos, consulte [desenvolver aplicativos para equipes](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="8cc1a-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



