---
title: Suporte para o Skype for Business Online no Outlook na Web
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: O Outlook na Web (Outlook Web App) no Office 365 oferece um cliente Web básico do Skype for Business na barra de navegação. Este cliente básico está disponível para usuários online cujo administrador não configurou uma URL intuitiva para a sua organização do Office 365. Desde que a conta do usuário esteja online e não tenha uma URL do intuitiva, ela ainda verá a experiência mesmo se a organização tiver algumas contas de usuário hospedadas no local. Os usuários que têm contas de usuário locais (sejam uma URL intuitiva ou não) ou são gerenciados pela Microsoft verão a experiência do Lync no Outlook Web App.
ms.openlocfilehash: 7eab3ce7c8d6ea8c1f004559ea92f64f554fb010
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692846"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="76e1a-106">Suporte para o Skype for Business Online no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="76e1a-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="76e1a-p102">O Outlook na Web (Outlook Web App) no Office 365 oferece um cliente Web básico do Skype for Business na barra de navegação. Este cliente básico está disponível para usuários online cujo administrador não configurou uma URL intuitiva para a sua organização do Office 365. Desde que a conta do usuário esteja online e não tenha uma URL do intuitiva, ela ainda verá a experiência mesmo se a organização tiver algumas contas de usuário hospedadas no local. Os usuários que têm contas de usuário locais (sejam uma URL intuitiva ou não) ou são gerenciados pela Microsoft verão a experiência do Lync no Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="76e1a-p102">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar. This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization. As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises. Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="76e1a-111">A tabela a seguir resume as diferentes configurações que você pode ter e o cliente Web que é usado.</span><span class="sxs-lookup"><span data-stu-id="76e1a-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="76e1a-112">**A conta de usuário é hospedada no local**</span><span class="sxs-lookup"><span data-stu-id="76e1a-112">**User account is located**</span></span> <br/> |<span data-ttu-id="76e1a-113">**A URL intuitiva está configurada ou há uma organização dedicada**</span><span class="sxs-lookup"><span data-stu-id="76e1a-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="76e1a-114">**Experiência do Skype for Business ou do Lync?**</span><span class="sxs-lookup"><span data-stu-id="76e1a-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="76e1a-115">Online</span><span class="sxs-lookup"><span data-stu-id="76e1a-115">Online</span></span>  <br/> |<span data-ttu-id="76e1a-116">Não</span><span class="sxs-lookup"><span data-stu-id="76e1a-116">No</span></span>  <br/> |<span data-ttu-id="76e1a-117">Experiência do Skype for Business Web</span><span class="sxs-lookup"><span data-stu-id="76e1a-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="76e1a-118">Online</span><span class="sxs-lookup"><span data-stu-id="76e1a-118">Online</span></span>  <br/> |<span data-ttu-id="76e1a-119">Sim</span><span class="sxs-lookup"><span data-stu-id="76e1a-119">Yes</span></span>  <br/> |<span data-ttu-id="76e1a-120">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="76e1a-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="76e1a-121">Híbrido, mas hospedado online</span><span class="sxs-lookup"><span data-stu-id="76e1a-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="76e1a-122">Não</span><span class="sxs-lookup"><span data-stu-id="76e1a-122">No</span></span>  <br/> |<span data-ttu-id="76e1a-123">Experiência do Skype for Business Web</span><span class="sxs-lookup"><span data-stu-id="76e1a-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="76e1a-124">Híbrido, mas hospedado online</span><span class="sxs-lookup"><span data-stu-id="76e1a-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="76e1a-125">Sim</span><span class="sxs-lookup"><span data-stu-id="76e1a-125">Yes</span></span>  <br/> |<span data-ttu-id="76e1a-126">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="76e1a-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="76e1a-127">Híbrido, mas hospedado no local</span><span class="sxs-lookup"><span data-stu-id="76e1a-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="76e1a-128">Não</span><span class="sxs-lookup"><span data-stu-id="76e1a-128">No</span></span>  <br/> |<span data-ttu-id="76e1a-129">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="76e1a-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="76e1a-130">Híbrido, mas hospedado no local</span><span class="sxs-lookup"><span data-stu-id="76e1a-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="76e1a-131">Sim</span><span class="sxs-lookup"><span data-stu-id="76e1a-131">Yes</span></span>  <br/> |<span data-ttu-id="76e1a-132">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="76e1a-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="76e1a-133">Puro no local</span><span class="sxs-lookup"><span data-stu-id="76e1a-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="76e1a-134">Não</span><span class="sxs-lookup"><span data-stu-id="76e1a-134">No</span></span>  <br/> |<span data-ttu-id="76e1a-135">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="76e1a-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="76e1a-136">Puro no local</span><span class="sxs-lookup"><span data-stu-id="76e1a-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="76e1a-137">Sim</span><span class="sxs-lookup"><span data-stu-id="76e1a-137">Yes</span></span>  <br/> |<span data-ttu-id="76e1a-138">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="76e1a-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="76e1a-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="76e1a-139">Related topics</span></span>
[<span data-ttu-id="76e1a-140">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="76e1a-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="76e1a-141">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="76e1a-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
