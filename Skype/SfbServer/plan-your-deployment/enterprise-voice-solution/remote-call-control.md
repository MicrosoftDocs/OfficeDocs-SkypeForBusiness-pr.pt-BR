---
title: Plano de controle de chamada remota no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: O controle de chamada remota foi um recurso nas versões anteriores do Lync Server que permitia aos usuários controlar os telefones PBX com o Lync Server. No Skype for Business Server, este recurso foi substituído por meio da chamada por meio do trabalho. Nas versões do cliente para o Skype for Business Server 2015 e encaminhadas, o controle de chamada remota não está mais disponível para ser configurado no cliente e foi removido para uso.
ms.openlocfilehash: 67010a0bc74ef46dcf204e3b2a905be87c182daf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802501"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="b1932-105">Plano de controle de chamada remota no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b1932-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="b1932-106">O controle de chamada remota foi um recurso nas versões anteriores do Lync Server que permitia aos usuários controlar os telefones PBX com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b1932-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="b1932-107">No Skype for Business Server, este recurso foi substituído por meio da chamada por meio do trabalho.</span><span class="sxs-lookup"><span data-stu-id="b1932-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="b1932-108">*Nas versões do cliente para o Skype for Business Server 2015 e encaminhadas, o controle de chamada remota não está mais disponível para ser configurado no cliente e foi removido para uso.*</span><span class="sxs-lookup"><span data-stu-id="b1932-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="b1932-109">Os usuários de controle de chamada remota em sua organização que são hospedados em servidores front-end que executam o Lync Server podem continuar a usar o controle de chamada remota, mesmo se estiverem usando um cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b1932-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="b1932-110">No entanto, para todos os usuários hospedados no Skype for Business Server, não há suporte para o controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="b1932-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="b1932-111">Consulte a tabela a seguir das combinações servidor/cliente e se elas podem suportar o controle de chamada remota ou Telefonar via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="b1932-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="b1932-112">**Cliente Skype for Business com interface do usuário do Skype habilitada**</span><span class="sxs-lookup"><span data-stu-id="b1932-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="b1932-113">**Interface do usuário do Skype for Business com interface do usuário do Lync habilitada**</span><span class="sxs-lookup"><span data-stu-id="b1932-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="b1932-114">**Cliente Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="b1932-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="b1932-115">**Cliente do Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="b1932-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="b1932-116">**Lync 2010 Client**</span><span class="sxs-lookup"><span data-stu-id="b1932-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b1932-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b1932-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="b1932-118">Chamada via Trabalho</span><span class="sxs-lookup"><span data-stu-id="b1932-118">Call via Work</span></span>  <br/> |<span data-ttu-id="b1932-119">1</span><span class="sxs-lookup"><span data-stu-id="b1932-119">1</span></span> <br/> |<span data-ttu-id="b1932-120">Chamada via Trabalho</span><span class="sxs-lookup"><span data-stu-id="b1932-120">Call via Work</span></span>  <br/> |<span data-ttu-id="b1932-121">1</span><span class="sxs-lookup"><span data-stu-id="b1932-121">1</span></span> <br/> |<span data-ttu-id="b1932-122">1</span><span class="sxs-lookup"><span data-stu-id="b1932-122">1</span></span> <br/> |
| <span data-ttu-id="b1932-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1932-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="b1932-124">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b1932-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1932-125">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b1932-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1932-126">um</span><span class="sxs-lookup"><span data-stu-id="b1932-126">1</span></span> <br/> |<span data-ttu-id="b1932-127">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b1932-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1932-128">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b1932-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="b1932-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b1932-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="b1932-130">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b1932-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1932-131">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b1932-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1932-132">um</span><span class="sxs-lookup"><span data-stu-id="b1932-132">1</span></span> <br/> |<span data-ttu-id="b1932-133">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b1932-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1932-134">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b1932-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="b1932-135">Não há suporte para nenhum recurso.</span><span class="sxs-lookup"><span data-stu-id="b1932-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="b1932-136">Para obter mais informações, consulte [controle de chamada remota](https://go.microsoft.com/fwlink/p/?LinkId=530208) na documentação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1932-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b1932-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="b1932-137">See also</span></span>

[<span data-ttu-id="b1932-138">Planejar a chamada por meio do trabalho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b1932-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="b1932-139">Comparação de recursos do cliente de desktop do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b1932-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="b1932-140">Fazer uma chamada no Skype for Business, mas usar seu telefone de mesa PBX para áudio</span><span class="sxs-lookup"><span data-stu-id="b1932-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

