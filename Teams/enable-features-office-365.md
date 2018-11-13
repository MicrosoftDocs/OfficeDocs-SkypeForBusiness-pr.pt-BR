---
title: Gerenciar recursos de Teams da Microsoft em sua organização do Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como ativar ou desativar apps Teams da Microsoft em sua organização do Office 365, incluindo guias, conectores, bots ou qualquer combinação dos três.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: f975ed755c66fe644c7097e218dc3be14e7c3165
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295902"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="63844-103">Gerenciar recursos de Teams da Microsoft em sua organização do Office 365</span><span class="sxs-lookup"><span data-stu-id="63844-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="63844-104">Todas as definições de equipes em breve serão migradas para o novo Teams Microsoft & Skype para Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="63844-104">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="63844-105">O único recurso de equipes que é gerenciado no Centro de administração do Office 365 é Apps.</span><span class="sxs-lookup"><span data-stu-id="63844-105">The only Teams feature that is managed in the Office 365 admin center is Apps.</span></span> 

<span data-ttu-id="63844-106">A menos que esteja especificado, o valor padrão das opções é Ativado.</span><span class="sxs-lookup"><span data-stu-id="63844-106">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="63844-107">Para gerenciar as configurações de administração no Teams, vá para o Centro de administração do Office 365 e abra **Configurações** > **Serviços e suplementos** e escolha **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="63844-107">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="63844-108">Se você tiver entrado como administrador do Office 365, este link deverá direcioná-lo corretamente:</span><span class="sxs-lookup"><span data-stu-id="63844-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="63844-109">Configurações de todo o locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="63844-109">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="63844-110">Nas **configurações de todo o locatário**, você pode ativar ou desativar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="63844-110">In **Tenant-wide settings**, you can turn on or turn off Apps.</span></span>

<span data-ttu-id="63844-111">Para editar as **Configurações de todo o locatário** do Microsoft Teams, acesse o Centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="63844-111">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="63844-112">Escolha **Configurações** > **Serviços e complementos** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="63844-112">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

## <a name="apps"></a><span data-ttu-id="63844-113">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="63844-113">Apps</span></span>

<span data-ttu-id="63844-114">Os aplicativos consistem em guias, conectores, bots ou qualquer combinação dos três, fornecidos por um serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="63844-114">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="63844-115">Existem políticas de administração do Teams que podem ser configuradas no Centro de administração do Office 365 para controlar quais aplicativos externos de terceiros são permitidos.</span><span class="sxs-lookup"><span data-stu-id="63844-115">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="63844-116">Essas diretivas permitem especificar quais aplicativos são permitidos e não permitidos, novo comportamento de aplicativo externo, e se os aplicativos do lado do carregamento é permitido.</span><span class="sxs-lookup"><span data-stu-id="63844-116">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="63844-117">Em **Aplicativos**, você pode definir estas configurações para a sua organização:</span><span class="sxs-lookup"><span data-stu-id="63844-117">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![Captura de tela da seção de aplicativos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="63844-119">**Allow external apps in Microsoft Teams** (Permitir aplicativos externos no Microsoft Teams): quando essa opção está ativada, os usuários podem adicionar guias e bots disponíveis para o locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="63844-119">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![Captura de tela do controle de permissão de aplicativos externos na seção Aplicativos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="63844-121">**Enable new external apps by default** (Habilitar novos aplicativos externos por padrão): quando essa opção está ativada, os usuários podem ativar novos aplicativos assim que eles são adicionados ao catálogo de aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="63844-121">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="63844-122">Desative essa opção para poder controlar os novos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="63844-122">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="63844-123">Obviamente, se você desativá-la, precisará lembrar de revisar os novos aplicativos periodicamente para que sua organização não perca novos aplicativos bacanas.</span><span class="sxs-lookup"><span data-stu-id="63844-123">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="63844-124">**Allow sideloading of external apps** (Permitir o sideload de aplicativos externos): quando essa opção está ativada, os usuários podem instalar e habilitar bots e guias personalizados.</span><span class="sxs-lookup"><span data-stu-id="63844-124">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="63844-125">Para saber mais, leia [Configurações de administração para aplicativos no Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="63844-125">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

