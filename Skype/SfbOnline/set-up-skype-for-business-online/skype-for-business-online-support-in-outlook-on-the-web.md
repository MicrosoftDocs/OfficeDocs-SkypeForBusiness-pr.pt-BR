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
description: Outlook na Web (Outlook Web App) em Microsoft 365 ou Office 365 oferece um cliente Web básico Skype for Business da barra de navegação. Esse cliente básico está disponível para usuários online cujo administrador não configurou uma URL de vaidade para seus Microsoft 365 e Office 365. Enquanto a conta do usuário estiver online e não tiver uma URL de vaidade, ele ainda verá a experiência, mesmo que sua organização tenha algumas contas de usuário que estão no local. Os usuários que têm contas de usuário no local (quer tenham uma URL falsa ou não) ou sejam gerenciados pela Microsoft verão a experiência do Lync no aplicativo Outlook Web.
ms.openlocfilehash: aa6f82f6647db1816c630486bee0d415d05b3b77
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239566"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="cfb36-106">Suporte para o Skype for Business Online no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="cfb36-106">Skype for Business Online support in Outlook on the web</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="cfb36-107">Outlook na Web (Outlook Web App) em Microsoft 365 ou Office 365 oferece um cliente Web básico Skype for Business da barra de navegação.</span><span class="sxs-lookup"><span data-stu-id="cfb36-107">Outlook on the web (Outlook Web App) in Microsoft 365 or Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="cfb36-108">Esse cliente básico está disponível para usuários online cujo administrador não configurou uma URL de vaidade para seus Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="cfb36-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 and Office 365.</span></span> <span data-ttu-id="cfb36-109">Enquanto a conta do usuário estiver online e não tiver uma URL de vaidade, ele ainda verá a experiência, mesmo que sua organização tenha algumas contas de usuário que estão no local.</span><span class="sxs-lookup"><span data-stu-id="cfb36-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="cfb36-110">Os usuários que têm contas de usuário no local (quer tenham uma URL falsa ou não) ou sejam gerenciados pela Microsoft verão a experiência do Lync no aplicativo Outlook Web.</span><span class="sxs-lookup"><span data-stu-id="cfb36-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="cfb36-111">A tabela a seguir resume as diferentes configurações que você pode ter e o cliente Web usado.</span><span class="sxs-lookup"><span data-stu-id="cfb36-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="cfb36-112">**A conta de usuário é hospedada no local**</span><span class="sxs-lookup"><span data-stu-id="cfb36-112">**User account is located**</span></span> <br/> |<span data-ttu-id="cfb36-113">**A URL intuitiva está configurada ou há uma organização dedicada**</span><span class="sxs-lookup"><span data-stu-id="cfb36-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="cfb36-114">**Experiência do Skype for Business ou do Lync?**</span><span class="sxs-lookup"><span data-stu-id="cfb36-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="cfb36-115">Online</span><span class="sxs-lookup"><span data-stu-id="cfb36-115">Online</span></span>  <br/> |<span data-ttu-id="cfb36-116">Não</span><span class="sxs-lookup"><span data-stu-id="cfb36-116">No</span></span>  <br/> |<span data-ttu-id="cfb36-117">Experiência do Skype for Business Web</span><span class="sxs-lookup"><span data-stu-id="cfb36-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="cfb36-118">Online</span><span class="sxs-lookup"><span data-stu-id="cfb36-118">Online</span></span>  <br/> |<span data-ttu-id="cfb36-119">Sim</span><span class="sxs-lookup"><span data-stu-id="cfb36-119">Yes</span></span>  <br/> |<span data-ttu-id="cfb36-120">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="cfb36-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="cfb36-121">Híbrido, mas hospedado online</span><span class="sxs-lookup"><span data-stu-id="cfb36-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="cfb36-122">Não</span><span class="sxs-lookup"><span data-stu-id="cfb36-122">No</span></span>  <br/> |<span data-ttu-id="cfb36-123">Experiência do Skype for Business Web</span><span class="sxs-lookup"><span data-stu-id="cfb36-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="cfb36-124">Híbrido, mas hospedado online</span><span class="sxs-lookup"><span data-stu-id="cfb36-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="cfb36-125">Sim</span><span class="sxs-lookup"><span data-stu-id="cfb36-125">Yes</span></span>  <br/> |<span data-ttu-id="cfb36-126">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="cfb36-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="cfb36-127">Híbrido, mas hospedado no local</span><span class="sxs-lookup"><span data-stu-id="cfb36-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="cfb36-128">Não</span><span class="sxs-lookup"><span data-stu-id="cfb36-128">No</span></span>  <br/> |<span data-ttu-id="cfb36-129">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="cfb36-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="cfb36-130">Híbrido, mas hospedado no local</span><span class="sxs-lookup"><span data-stu-id="cfb36-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="cfb36-131">Sim</span><span class="sxs-lookup"><span data-stu-id="cfb36-131">Yes</span></span>  <br/> |<span data-ttu-id="cfb36-132">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="cfb36-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="cfb36-133">Puro em prem</span><span class="sxs-lookup"><span data-stu-id="cfb36-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="cfb36-134">Não</span><span class="sxs-lookup"><span data-stu-id="cfb36-134">No</span></span>  <br/> |<span data-ttu-id="cfb36-135">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="cfb36-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="cfb36-136">Puro em prem</span><span class="sxs-lookup"><span data-stu-id="cfb36-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="cfb36-137">Sim</span><span class="sxs-lookup"><span data-stu-id="cfb36-137">Yes</span></span>  <br/> |<span data-ttu-id="cfb36-138">Experiência do Lync Web</span><span class="sxs-lookup"><span data-stu-id="cfb36-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="cfb36-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cfb36-139">Related topics</span></span>
[<span data-ttu-id="cfb36-140">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cfb36-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="cfb36-141">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="cfb36-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
