---
title: Planejar o controle de chamada remota no Skype para negócios
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Controle de chamada remota era um recurso nas versões anteriores do Microsoft Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server. Skype para Business Server, esse recurso foi substituído com a chamada Via trabalho. Nas versões do cliente para Skype para Business Server 2015 e de chamada remoto, encaminhar de passando para o controle não está mais disponível para configurar no cliente e foi removido para uso.
ms.openlocfilehash: d2203840672bfc73cf478254b9d115fd0375c902
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21014540"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="b61cd-105">Planejar o controle de chamada remota no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="b61cd-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="b61cd-106">Controle de chamada remota era um recurso nas versões anteriores do Microsoft Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b61cd-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="b61cd-107">Skype para Business Server, esse recurso foi substituído com a chamada Via trabalho.</span><span class="sxs-lookup"><span data-stu-id="b61cd-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="b61cd-108">*Nas versões do cliente para Skype para Business Server 2015 e de chamada remoto, encaminhar de passando para o controle não está mais disponível para configurar no cliente e foi removido para uso.*</span><span class="sxs-lookup"><span data-stu-id="b61cd-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="b61cd-109">Usuários de controle de chamada remota em sua organização hospedados em servidores Front-End executando o Lync Server podem continuar a usar o controle de chamada remota, mesmo que estejam usando um Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="b61cd-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="b61cd-110">No entanto, para todos os usuários hospedagem no Skype para Business Server, o controle de chamada remota não é suportado.</span><span class="sxs-lookup"><span data-stu-id="b61cd-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="b61cd-111">Consulte a tabela a seguir das combinações servidor/cliente e se elas podem suportar o controle de chamada remota ou Telefonar via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="b61cd-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="b61cd-112">**Skype para negócios com Skype UI do cliente habilitado**</span><span class="sxs-lookup"><span data-stu-id="b61cd-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="b61cd-113">**Skype para negócios com Lync UI do cliente habilitado**</span><span class="sxs-lookup"><span data-stu-id="b61cd-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="b61cd-114">**Skype para Business 2016 Client**</span><span class="sxs-lookup"><span data-stu-id="b61cd-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="b61cd-115">**Cliente do Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="b61cd-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="b61cd-116">**Lync 2010 Client**</span><span class="sxs-lookup"><span data-stu-id="b61cd-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b61cd-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b61cd-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="b61cd-118">Chamada via Trabalho</span><span class="sxs-lookup"><span data-stu-id="b61cd-118">Call via Work</span></span>  <br/> |<span data-ttu-id="b61cd-119">1</span><span class="sxs-lookup"><span data-stu-id="b61cd-119">1</span></span> <br/> |<span data-ttu-id="b61cd-120">Chamada via Trabalho</span><span class="sxs-lookup"><span data-stu-id="b61cd-120">Call via Work</span></span>  <br/> |<span data-ttu-id="b61cd-121">1</span><span class="sxs-lookup"><span data-stu-id="b61cd-121">1</span></span> <br/> |<span data-ttu-id="b61cd-122">1</span><span class="sxs-lookup"><span data-stu-id="b61cd-122">1</span></span> <br/> |
| <span data-ttu-id="b61cd-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b61cd-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="b61cd-124">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b61cd-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b61cd-125">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b61cd-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b61cd-126">1</span><span class="sxs-lookup"><span data-stu-id="b61cd-126">1</span></span> <br/> |<span data-ttu-id="b61cd-127">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b61cd-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b61cd-128">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b61cd-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="b61cd-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b61cd-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="b61cd-130">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b61cd-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b61cd-131">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b61cd-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b61cd-132">1</span><span class="sxs-lookup"><span data-stu-id="b61cd-132">1</span></span> <br/> |<span data-ttu-id="b61cd-133">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b61cd-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b61cd-134">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="b61cd-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="b61cd-135">Nenhum recurso é suportado.</span><span class="sxs-lookup"><span data-stu-id="b61cd-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="b61cd-136">Para obter mais informações, consulte [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) na documentação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b61cd-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b61cd-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b61cd-137">See also</span></span>

[<span data-ttu-id="b61cd-138">Planejar para chamada Via trabalho no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b61cd-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="b61cd-139">Comparação de recursos do cliente de desktop do Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="b61cd-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="b61cd-140">Tornar um Skype para chamada de negócios, mas usar seu telefone de mesa PBX para áudio</span><span class="sxs-lookup"><span data-stu-id="b61cd-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

