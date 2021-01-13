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
description: O controle de chamada remota era um recurso em versões anteriores do Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server. No Skype for Business Server, esse recurso foi substituído pelo Telefonar via Trabalho. Nas versões de cliente do Skype for Business Server 2015 e no futuro, o controle de chamada remota não está mais disponível para configuração no cliente e foi removido para uso.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813511"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="40895-105">Planejar o controle de chamada remota no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="40895-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="40895-106">O controle de chamada remota era um recurso em versões anteriores do Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40895-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="40895-107">No Skype for Business Server, esse recurso foi substituído pelo Telefonar via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="40895-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="40895-108">*Nas versões de cliente do Skype for Business Server 2015 e no futuro, o controle de chamada remota não está mais disponível para configuração no cliente e foi removido para uso.*</span><span class="sxs-lookup"><span data-stu-id="40895-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="40895-109">Os usuários de controle de chamada remota em sua organização que estão em servidores front-end executando o Lync Server podem continuar a usar o controle de chamada remota, mesmo se eles estão usando um cliente do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="40895-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="40895-110">No entanto, para todos os usuários que estão no Skype for Business Server, o controle de chamada remota não é suportado.</span><span class="sxs-lookup"><span data-stu-id="40895-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="40895-111">Consulte a tabela a seguir para combinações de servidor/cliente e se elas podem suportar o controle de chamada remota ou Telefonar via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="40895-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="40895-112">**Cliente Skype for Business com interface do usuário do Skype habilitada**</span><span class="sxs-lookup"><span data-stu-id="40895-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="40895-113">**Cliente Skype for Business com interface do usuário do Lync habilitada**</span><span class="sxs-lookup"><span data-stu-id="40895-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="40895-114">**Cliente Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="40895-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="40895-115">**Cliente Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="40895-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="40895-116">**Cliente do Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="40895-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="40895-117">Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="40895-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="40895-118">Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="40895-118">Call via Work</span></span>  <br/> |<span data-ttu-id="40895-119">1 </span><span class="sxs-lookup"><span data-stu-id="40895-119">1</span></span> <br/> |<span data-ttu-id="40895-120">Telefonar via Trabalho</span><span class="sxs-lookup"><span data-stu-id="40895-120">Call via Work</span></span>  <br/> |<span data-ttu-id="40895-121">1 </span><span class="sxs-lookup"><span data-stu-id="40895-121">1</span></span> <br/> |<span data-ttu-id="40895-122">1 </span><span class="sxs-lookup"><span data-stu-id="40895-122">1</span></span> <br/> |
| <span data-ttu-id="40895-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40895-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="40895-124">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="40895-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="40895-125">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="40895-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="40895-126">1 </span><span class="sxs-lookup"><span data-stu-id="40895-126">1</span></span> <br/> |<span data-ttu-id="40895-127">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="40895-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="40895-128">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="40895-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="40895-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="40895-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="40895-130">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="40895-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="40895-131">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="40895-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="40895-132">1 </span><span class="sxs-lookup"><span data-stu-id="40895-132">1</span></span> <br/> |<span data-ttu-id="40895-133">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="40895-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="40895-134">Controle de Chamada Remota</span><span class="sxs-lookup"><span data-stu-id="40895-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="40895-135">Nenhum dos recursos é suportado.</span><span class="sxs-lookup"><span data-stu-id="40895-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="40895-136">Para obter mais informações, [consulte Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) na documentação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40895-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="40895-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="40895-137">See also</span></span>

[<span data-ttu-id="40895-138">Planejar o Telefonar via Trabalho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40895-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="40895-139">Comparação de recursos do cliente de desktop para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="40895-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="40895-140">Fazer uma chamada do Skype for Business, mas usar seu telefone de mesa PBX para áudio</span><span class="sxs-lookup"><span data-stu-id="40895-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

