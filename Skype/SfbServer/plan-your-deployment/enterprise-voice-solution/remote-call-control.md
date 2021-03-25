---
title: Planejar o controle de chamada remota no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: O controle de chamada remota era um recurso em versões anteriores do Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server. No Skype for Business Server, esse recurso foi substituído por Call Via Work. Nas versões do cliente do Skype for Business Server 2015 e adiante, o controle de chamada remota não está mais disponível para configurar no cliente e foi removido para uso.
ms.openlocfilehash: 1ec6bb59b34505f17451be72baa44cdcc466c0d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114607"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="e78a4-105">Planejar o controle de chamada remota no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e78a4-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="e78a4-106">O controle de chamada remota era um recurso em versões anteriores do Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e78a4-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="e78a4-107">No Skype for Business Server, esse recurso foi substituído por Call Via Work.</span><span class="sxs-lookup"><span data-stu-id="e78a4-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="e78a4-108">*Nas versões do cliente do Skype for Business Server 2015 e adiante, o controle de chamada remota não está mais disponível para configurar no cliente e foi removido para uso.*</span><span class="sxs-lookup"><span data-stu-id="e78a4-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="e78a4-109">Os usuários do controle de chamadas remotas em sua organização que estão instalados em Servidores Front-End executando o Lync Server podem continuar a usar o controle de chamada remota, mesmo se eles estão usando um cliente do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e78a4-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="e78a4-110">No entanto, para todos os usuários que estão no Skype for Business Server, não há suporte para o controle de chamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="e78a4-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="e78a4-111">Consulte a tabela a seguir para combinações de servidor/cliente e se elas podem suportar o controle de chamada remota ou Chamada via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="e78a4-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="e78a4-112">**Cliente skype for business com interface do usuário do Skype habilitada**</span><span class="sxs-lookup"><span data-stu-id="e78a4-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="e78a4-113">**Cliente do Skype for Business com a interface do usuário do Lync habilitada**</span><span class="sxs-lookup"><span data-stu-id="e78a4-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="e78a4-114">**Cliente Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="e78a4-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="e78a4-115">**Cliente Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="e78a4-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="e78a4-116">**Cliente do Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="e78a4-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e78a4-117">Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e78a4-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="e78a4-118">Chamada via Trabalho</span><span class="sxs-lookup"><span data-stu-id="e78a4-118">Call via Work</span></span>  <br/> |<span data-ttu-id="e78a4-119">1</span><span class="sxs-lookup"><span data-stu-id="e78a4-119">1</span></span> <br/> |<span data-ttu-id="e78a4-120">Chamada via Trabalho</span><span class="sxs-lookup"><span data-stu-id="e78a4-120">Call via Work</span></span>  <br/> |<span data-ttu-id="e78a4-121">1</span><span class="sxs-lookup"><span data-stu-id="e78a4-121">1</span></span> <br/> |<span data-ttu-id="e78a4-122">1</span><span class="sxs-lookup"><span data-stu-id="e78a4-122">1</span></span> <br/> |
| <span data-ttu-id="e78a4-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e78a4-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="e78a4-124">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="e78a4-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e78a4-125">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="e78a4-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e78a4-126">1</span><span class="sxs-lookup"><span data-stu-id="e78a4-126">1</span></span> <br/> |<span data-ttu-id="e78a4-127">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="e78a4-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e78a4-128">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="e78a4-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="e78a4-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e78a4-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="e78a4-130">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="e78a4-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e78a4-131">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="e78a4-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e78a4-132">1</span><span class="sxs-lookup"><span data-stu-id="e78a4-132">1</span></span> <br/> |<span data-ttu-id="e78a4-133">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="e78a4-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e78a4-134">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="e78a4-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="e78a4-135">Nenhum dos recursos é suportado.</span><span class="sxs-lookup"><span data-stu-id="e78a4-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="e78a4-136">Para obter mais informações, consulte [Controle de Chamada Remota](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) na documentação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e78a4-136">For more information, see [Remote Call Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e78a4-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="e78a4-137">See also</span></span>

[<span data-ttu-id="e78a4-138">Planejar chamadas via trabalho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e78a4-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="e78a4-139">Comparação de recursos do cliente da área de trabalho do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e78a4-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="e78a4-140">Faça uma chamada do Skype for Business, mas use seu telefone de mesa PBX para áudio</span><span class="sxs-lookup"><span data-stu-id="e78a4-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)