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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: O Outlook na Web (Outlook Web App) no Office 365 oferece um cliente Web básico do Skype for Business na barra de navegação. Esse cliente básico está disponível para usuários Online cujo administrador não tiver configurado uma URL vanity para sua organização do Office 365. Desde que a conta do usuário está online e não tem uma URL vanity, eles ainda poderão ver a experiência do mesmo se sua organização tiver algumas contas de usuário que estão hospedados no local. Os usuários que têm usuário contas locais (quer eles tenham uma URL vanity ou não) ou são gerenciados pela Microsoft verá a experiência do Lync no Outlook web app.
ms.openlocfilehash: 0d98d2490510b54ec0aabd4fefb7ed4137b449b7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891033"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="9d5c0-106">Suporte para o Skype for Business Online no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="9d5c0-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="9d5c0-107">O Outlook na Web (Outlook Web App) no Office 365 oferece um cliente Web básico do Skype for Business na barra de navegação.</span><span class="sxs-lookup"><span data-stu-id="9d5c0-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="9d5c0-108">Esse cliente básico está disponível para usuários Online cujo administrador não tiver configurado uma URL vanity para sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9d5c0-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="9d5c0-109">Desde que a conta do usuário está online e não tem uma URL vanity, eles ainda poderão ver a experiência do mesmo se sua organização tiver algumas contas de usuário que estão hospedados no local.</span><span class="sxs-lookup"><span data-stu-id="9d5c0-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="9d5c0-110">Os usuários que têm usuário contas locais (quer eles tenham uma URL vanity ou não) ou são gerenciados pela Microsoft verá a experiência do Lync no Outlook web app.</span><span class="sxs-lookup"><span data-stu-id="9d5c0-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="9d5c0-111">A tabela a seguir resume as configurações diferentes que você pode ter e o cliente web que é usado.</span><span class="sxs-lookup"><span data-stu-id="9d5c0-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9d5c0-112">**A conta de usuário é hospedada no local**</span><span class="sxs-lookup"><span data-stu-id="9d5c0-112">**User account is located**</span></span> <br/> |<span data-ttu-id="9d5c0-113">**A URL intuitiva está configurada ou há uma organização dedicada**</span><span class="sxs-lookup"><span data-stu-id="9d5c0-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="9d5c0-114">**Experiência do Skype for Business ou do Lync?**</span><span class="sxs-lookup"><span data-stu-id="9d5c0-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="9d5c0-115">Online</span><span class="sxs-lookup"><span data-stu-id="9d5c0-115">Online</span></span>  <br/> |<span data-ttu-id="9d5c0-116">Não</span><span class="sxs-lookup"><span data-stu-id="9d5c0-116">No</span></span>  <br/> |<span data-ttu-id="9d5c0-117">Experiência do Skype for Business Web</span><span class="sxs-lookup"><span data-stu-id="9d5c0-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="9d5c0-118">Online</span><span class="sxs-lookup"><span data-stu-id="9d5c0-118">Online</span></span>  <br/> |<span data-ttu-id="9d5c0-119">Sim</span><span class="sxs-lookup"><span data-stu-id="9d5c0-119">Yes</span></span>  <br/> |<span data-ttu-id="9d5c0-120">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="9d5c0-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="9d5c0-121">Híbrido, mas hospedado online</span><span class="sxs-lookup"><span data-stu-id="9d5c0-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="9d5c0-122">Não</span><span class="sxs-lookup"><span data-stu-id="9d5c0-122">No</span></span>  <br/> |<span data-ttu-id="9d5c0-123">Experiência do Skype for Business Web</span><span class="sxs-lookup"><span data-stu-id="9d5c0-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="9d5c0-124">Híbrido, mas hospedado online</span><span class="sxs-lookup"><span data-stu-id="9d5c0-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="9d5c0-125">Sim</span><span class="sxs-lookup"><span data-stu-id="9d5c0-125">Yes</span></span>  <br/> |<span data-ttu-id="9d5c0-126">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="9d5c0-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="9d5c0-127">Híbrido, mas hospedado no local</span><span class="sxs-lookup"><span data-stu-id="9d5c0-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="9d5c0-128">Não</span><span class="sxs-lookup"><span data-stu-id="9d5c0-128">No</span></span>  <br/> |<span data-ttu-id="9d5c0-129">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="9d5c0-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="9d5c0-130">Híbrido, mas hospedado no local</span><span class="sxs-lookup"><span data-stu-id="9d5c0-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="9d5c0-131">Sim</span><span class="sxs-lookup"><span data-stu-id="9d5c0-131">Yes</span></span>  <br/> |<span data-ttu-id="9d5c0-132">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="9d5c0-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="9d5c0-133">Puro em prem</span><span class="sxs-lookup"><span data-stu-id="9d5c0-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="9d5c0-134">Não</span><span class="sxs-lookup"><span data-stu-id="9d5c0-134">No</span></span>  <br/> |<span data-ttu-id="9d5c0-135">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="9d5c0-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="9d5c0-136">Puro em prem</span><span class="sxs-lookup"><span data-stu-id="9d5c0-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="9d5c0-137">Sim</span><span class="sxs-lookup"><span data-stu-id="9d5c0-137">Yes</span></span>  <br/> |<span data-ttu-id="9d5c0-138">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="9d5c0-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="9d5c0-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9d5c0-139">Related topics</span></span>
[<span data-ttu-id="9d5c0-140">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9d5c0-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="9d5c0-141">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="9d5c0-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
