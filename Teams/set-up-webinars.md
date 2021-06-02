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
ms.openlocfilehash: aafa7b57eea1228fa5565bb4d5e95304b42751a3
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718042"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="6fcd3-103">Configurar para webinars em Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6fcd3-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="6fcd3-104">Este artigo ajudará você a configurar sua organização para hospedar webinars.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="6fcd3-105">O que são webinars?</span><span class="sxs-lookup"><span data-stu-id="6fcd3-105">What are webinars?</span></span>

<span data-ttu-id="6fcd3-106">Webinars são reuniões estruturadas em que instrutores e participantes têm funções claras, geralmente usadas para fins de treinamento ou cenários de geração de leads de vendas e marketing.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-106">Webinars are structured meetings where instructors and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="6fcd3-107">Depois de configurar webinars em sua organização, os usuários podem agendar webinars e abrir o registro para os participantes.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="6fcd3-108">Ao contrário das reuniões tradicionais que incluem muitas discussões e atribuição de tarefas, os webinars são destinados a apresentações interativas e fornecem ferramentas para análise do participante.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="6fcd3-109">Permitir que os usuários agendem webinars usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fcd3-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="6fcd3-110">Você pode usar os seguintes atributos no cmdlet **set-CsTeamsMeetingPolicy Windows PowerShell set-CsTeamsMeetingPolicy** para configurar para webinars Teams.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="6fcd3-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="6fcd3-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="6fcd3-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="6fcd3-112">WhoCanRegister</span></span>
- <span data-ttu-id="6fcd3-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="6fcd3-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="6fcd3-114">Leia [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obter mais informações sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="6fcd3-115">Antes de executar esses cmdlets, você deve estar conectado ao Skype for Business PowerShell Online.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-115">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="6fcd3-116">Para obter mais informações, consulte [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="6fcd3-116">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="6fcd3-117">Permitir que os usuários agendem webinars</span><span class="sxs-lookup"><span data-stu-id="6fcd3-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="6fcd3-118">Para permitir que os usuários em sua organização agendem webinars, execute:</span><span class="sxs-lookup"><span data-stu-id="6fcd3-118">To allow users in your organization to schedule webinars, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```
### <a name="configure-who-can-register-for-webinars"></a><span data-ttu-id="6fcd3-119">Configurar quem pode se registrar para webinars</span><span class="sxs-lookup"><span data-stu-id="6fcd3-119">Configure who can register for webinars</span></span>

<span data-ttu-id="6fcd3-120">Você pode restringir o registro aos usuários somente em sua organização ou abri-lo para todos dentro e fora do locatário.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-120">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="6fcd3-121">Por padrão, **WhoCanRegister** está habilitado e definido como **Todos**.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-121">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="6fcd3-122">Se você quiser desativar o registro de reunião, de definir **AllowMeetingRegistration** como **False**.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-122">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fcd3-123">Lembre-se de **que AllowPrivateMeetingScheduling** deve ser definido como **True** para **AllowMeetingRegistration** funcionar.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-123">Keep in mind that **AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="6fcd3-124">Além disso, as Listas da Microsoft precisam ser configuradas SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-124">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="6fcd3-125">Para saber mais, confira [Configurações de controle para Listas da Microsoft.](/sharepoint/control-lists)</span><span class="sxs-lookup"><span data-stu-id="6fcd3-125">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

<span data-ttu-id="6fcd3-126">**Para permitir *que apenas* usuários em sua organização se registrem para webinars, execute:**</span><span class="sxs-lookup"><span data-stu-id="6fcd3-126">**To allow *only* users in your organization to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

<span data-ttu-id="6fcd3-127">Em seguida, execute:</span><span class="sxs-lookup"><span data-stu-id="6fcd3-127">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="6fcd3-128">**Para permitir que qualquer pessoa, incluindo usuários anônimos, registre-se para webinars, execute:**</span><span class="sxs-lookup"><span data-stu-id="6fcd3-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

<span data-ttu-id="6fcd3-129">Em seguida, execute:</span><span class="sxs-lookup"><span data-stu-id="6fcd3-129">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> <span data-ttu-id="6fcd3-130">Se a junção anônima estiver desligada nas configurações de reunião, os usuários anônimos não poderão ingressar em webinars.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-130">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="6fcd3-131">Para saber mais e habilitar essa configuração, consulte [Configurações de reunião em Teams](meeting-settings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6fcd3-131">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="6fcd3-132">Coletar participação na reunião</span><span class="sxs-lookup"><span data-stu-id="6fcd3-132">Collect meeting attendance</span></span>

<span data-ttu-id="6fcd3-133">Se você quiser que os organizadores analisem quem registrou e participou de webinars, você precisará ativar a **política AllowEngagementReport.**</span><span class="sxs-lookup"><span data-stu-id="6fcd3-133">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="6fcd3-134">Para fazer isso, execute o seguinte comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-134">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="6fcd3-135">Configurar configurações do webinar</span><span class="sxs-lookup"><span data-stu-id="6fcd3-135">Configure webinar settings</span></span>

<span data-ttu-id="6fcd3-136">Depois de habiligá-los para webinars, não é necessário mais gerenciamento de administradores.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-136">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="6fcd3-137">A política controla quais opções aparecem para organizadores do webinar.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-137">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6fcd3-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6fcd3-138">Related topics</span></span>

- [<span data-ttu-id="6fcd3-139">Políticas de reunião em Teams - Geral</span><span class="sxs-lookup"><span data-stu-id="6fcd3-139">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="6fcd3-140">Documentação set-CsTeamsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6fcd3-140">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
