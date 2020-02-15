---
title: Planejar o controle de chamada remota no Skype for Business
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
description: O controle de chamada remota era um recurso em versões anteriores do Lync Server, que permitia aos usuários controlar seus telefones PBX com o Lync Server. No Skype for Business Server, esse recurso foi substituído pela chamada via trabalho. Nas versões do cliente para o Skype for Business Server 2015 e em frente, o controle de chamada remota não está mais disponível para configurar no cliente e foi removido para uso.
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982796"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="5cc4e-105">Planejar o controle de chamada remota no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5cc4e-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="5cc4e-106">O controle de chamada remota era um recurso em versões anteriores do Lync Server, que permitia aos usuários controlar seus telefones PBX com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5cc4e-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="5cc4e-107">No Skype for Business Server, esse recurso foi substituído pela chamada via trabalho.</span><span class="sxs-lookup"><span data-stu-id="5cc4e-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="5cc4e-108">*Nas versões do cliente para o Skype for Business Server 2015 e em frente, o controle de chamada remota não está mais disponível para configurar no cliente e foi removido para uso.*</span><span class="sxs-lookup"><span data-stu-id="5cc4e-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="5cc4e-109">Os usuários de controle de chamada remota em sua organização hospedados em servidores front-end que executam o Lync Server podem continuar a usar o controle de chamada remota, mesmo que eles estejam usando um cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="5cc4e-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="5cc4e-110">No entanto, para qualquer usuário hospedado no Skype for Business Server, não há suporte para o controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="5cc4e-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="5cc4e-111">Consulte a tabela a seguir para combinações de servidor/cliente e se eles podem suportar o controle de chamada remota ou ligar via trabalho.</span><span class="sxs-lookup"><span data-stu-id="5cc4e-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="5cc4e-112">**Cliente Skype for Business com interface do usuário do Skype habilitada**</span><span class="sxs-lookup"><span data-stu-id="5cc4e-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="5cc4e-113">**Cliente Skype for Business com interface do usuário do Lync habilitado**</span><span class="sxs-lookup"><span data-stu-id="5cc4e-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="5cc4e-114">**Cliente 2016 do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="5cc4e-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="5cc4e-115">**Cliente do Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="5cc4e-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="5cc4e-116">**Cliente do Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="5cc4e-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5cc4e-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5cc4e-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="5cc4e-118">Ligar via trabalho</span><span class="sxs-lookup"><span data-stu-id="5cc4e-118">Call via Work</span></span>  <br/> |<span data-ttu-id="5cc4e-119">1 </span><span class="sxs-lookup"><span data-stu-id="5cc4e-119">1</span></span> <br/> |<span data-ttu-id="5cc4e-120">Ligar via trabalho</span><span class="sxs-lookup"><span data-stu-id="5cc4e-120">Call via Work</span></span>  <br/> |<span data-ttu-id="5cc4e-121">1 </span><span class="sxs-lookup"><span data-stu-id="5cc4e-121">1</span></span> <br/> |<span data-ttu-id="5cc4e-122">1 </span><span class="sxs-lookup"><span data-stu-id="5cc4e-122">1</span></span> <br/> |
| <span data-ttu-id="5cc4e-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cc4e-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="5cc4e-124">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="5cc4e-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="5cc4e-125">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="5cc4e-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="5cc4e-126">1 </span><span class="sxs-lookup"><span data-stu-id="5cc4e-126">1</span></span> <br/> |<span data-ttu-id="5cc4e-127">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="5cc4e-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="5cc4e-128">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="5cc4e-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="5cc4e-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5cc4e-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="5cc4e-130">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="5cc4e-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="5cc4e-131">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="5cc4e-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="5cc4e-132">1 </span><span class="sxs-lookup"><span data-stu-id="5cc4e-132">1</span></span> <br/> |<span data-ttu-id="5cc4e-133">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="5cc4e-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="5cc4e-134">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="5cc4e-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="5cc4e-135">Nenhum dos recursos tem suporte.</span><span class="sxs-lookup"><span data-stu-id="5cc4e-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="5cc4e-136">Para obter mais informações, consulte [controle de chamada remota](https://go.microsoft.com/fwlink/p/?LinkId=530208) na documentação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5cc4e-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5cc4e-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="5cc4e-137">See also</span></span>

[<span data-ttu-id="5cc4e-138">Planejar a chamada via trabalho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5cc4e-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="5cc4e-139">Comparação de recursos do cliente de desktop para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5cc4e-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="5cc4e-140">Fazer uma chamada do Skype for Business, mas usar seu telefone de mesa PBX para áudio</span><span class="sxs-lookup"><span data-stu-id="5cc4e-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

