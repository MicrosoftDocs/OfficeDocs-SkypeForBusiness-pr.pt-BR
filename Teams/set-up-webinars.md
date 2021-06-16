---
title: Configurar para webinars em Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Saiba como gerenciar políticas do Webinar para Teams reuniões.
ms.openlocfilehash: 14452b0caeee33f90b59f6581b6fccf4d5e0311b
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926743"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="8b83f-103">Configurar para webinars em Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b83f-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="8b83f-104">Este artigo ajudará você a configurar sua organização para hospedar webinars.</span><span class="sxs-lookup"><span data-stu-id="8b83f-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="8b83f-105">O que são webinars?</span><span class="sxs-lookup"><span data-stu-id="8b83f-105">What are webinars?</span></span>

<span data-ttu-id="8b83f-106">Webinars são reuniões estruturadas em que apresentadores e participantes têm funções claras, geralmente usadas para fins de treinamento ou cenários de geração de leads de vendas e marketing.</span><span class="sxs-lookup"><span data-stu-id="8b83f-106">Webinars are structured meetings where presenters and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="8b83f-107">Depois de configurar webinars em sua organização, os usuários podem agendar webinars e abrir o registro para os participantes.</span><span class="sxs-lookup"><span data-stu-id="8b83f-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="8b83f-108">Ao contrário das reuniões tradicionais que incluem muitas discussões e atribuição de tarefas, os webinars são destinados a apresentações interativas e fornecem ferramentas para análise do participante.</span><span class="sxs-lookup"><span data-stu-id="8b83f-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="8b83f-109">Permitir que os usuários agendem webinars usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b83f-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="8b83f-110">Você pode usar os seguintes atributos no cmdlet **set-CsTeamsMeetingPolicy Windows PowerShell set-CsTeamsMeetingPolicy** para configurar para webinars Teams.</span><span class="sxs-lookup"><span data-stu-id="8b83f-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="8b83f-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="8b83f-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="8b83f-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="8b83f-112">WhoCanRegister</span></span>
- <span data-ttu-id="8b83f-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8b83f-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="8b83f-114">Leia [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obter mais informações sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8b83f-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="8b83f-115">Antes de executar esses cmdlets, você deve estar conectado ao Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b83f-115">Before you can run these cmdlets you must be connected to Microsoft Teams PowerShell.</span></span> <span data-ttu-id="8b83f-116">Para obter mais informações, consulte [Manage Teams with Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).</span><span class="sxs-lookup"><span data-stu-id="8b83f-116">For more information, see [Manage Teams with Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="8b83f-117">Permitir que os usuários agendem webinars</span><span class="sxs-lookup"><span data-stu-id="8b83f-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="8b83f-118">Você pode restringir o registro aos usuários somente em sua organização ou abri-lo para todos dentro e fora do locatário.</span><span class="sxs-lookup"><span data-stu-id="8b83f-118">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="8b83f-119">Por padrão, **WhoCanRegister** está habilitado e definido como **Todos**.</span><span class="sxs-lookup"><span data-stu-id="8b83f-119">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="8b83f-120">Se você quiser desativar o registro de reunião, de definir **AllowMeetingRegistration** como **False**.</span><span class="sxs-lookup"><span data-stu-id="8b83f-120">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b83f-121">**AllowPrivateMeetingScheduling** deve ser definido como **True** para **AllowMeetingRegistration** funcionar.</span><span class="sxs-lookup"><span data-stu-id="8b83f-121">**AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="8b83f-122">Além disso, as Listas da Microsoft precisam ser configuradas SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8b83f-122">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="8b83f-123">Para saber mais, confira [Configurações de controle para Listas da Microsoft.](/sharepoint/control-lists)</span><span class="sxs-lookup"><span data-stu-id="8b83f-123">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

1. <span data-ttu-id="8b83f-124">Ativar o registro de reunião</span><span class="sxs-lookup"><span data-stu-id="8b83f-124">Turn on meeting registration</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. <span data-ttu-id="8b83f-125">Ativar o agendamento de reuniões privadas</span><span class="sxs-lookup"><span data-stu-id="8b83f-125">Turn on private meeting scheduling</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. <span data-ttu-id="8b83f-126">Configurar quem pode se registrar para webinars</span><span class="sxs-lookup"><span data-stu-id="8b83f-126">Configure who can register for webinars</span></span>

<span data-ttu-id="8b83f-127">**Permitir *que apenas* usuários em sua organização se registrem em webinars**</span><span class="sxs-lookup"><span data-stu-id="8b83f-127">**Allow *only* users in your organization to register for webinars**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="8b83f-128">**Para permitir que qualquer pessoa, incluindo usuários anônimos, registre-se para webinars, execute:**</span><span class="sxs-lookup"><span data-stu-id="8b83f-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> <span data-ttu-id="8b83f-129">Se a junção anônima estiver desligada nas configurações de reunião, os usuários anônimos não poderão ingressar em webinars.</span><span class="sxs-lookup"><span data-stu-id="8b83f-129">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="8b83f-130">Para saber mais e habilitar essa configuração, consulte [Configurações de reunião em Teams](meeting-settings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8b83f-130">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="8b83f-131">Coletar participação na reunião</span><span class="sxs-lookup"><span data-stu-id="8b83f-131">Collect meeting attendance</span></span>

<span data-ttu-id="8b83f-132">Se você quiser que os organizadores analisem quem registrou e participou de webinars, você precisará ativar a **política AllowEngagementReport.**</span><span class="sxs-lookup"><span data-stu-id="8b83f-132">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="8b83f-133">Para fazer isso, execute o seguinte comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b83f-133">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="8b83f-134">Configurar configurações do webinar</span><span class="sxs-lookup"><span data-stu-id="8b83f-134">Configure webinar settings</span></span>

<span data-ttu-id="8b83f-135">Depois de habiligá-los para webinars, não é necessário mais gerenciamento de administradores.</span><span class="sxs-lookup"><span data-stu-id="8b83f-135">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="8b83f-136">A política controla quais opções aparecem para organizadores do webinar.</span><span class="sxs-lookup"><span data-stu-id="8b83f-136">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8b83f-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8b83f-137">Related topics</span></span>

- [<span data-ttu-id="8b83f-138">Políticas de reunião em Teams - Geral</span><span class="sxs-lookup"><span data-stu-id="8b83f-138">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="8b83f-139">Documentação set-CsTeamsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="8b83f-139">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
