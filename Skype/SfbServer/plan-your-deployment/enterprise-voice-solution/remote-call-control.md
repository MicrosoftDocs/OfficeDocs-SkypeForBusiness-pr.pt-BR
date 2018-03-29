---
title: Planejamento de controle de chamada remota no Skype for Business 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Controle de chamada remota era um recurso nas versões anteriores do Microsoft Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server. Skype para Business Server, esse recurso foi substituído com a chamada Via trabalho. Nas versões do cliente para Skype para Business Server 2015 e de chamada remoto, encaminhar de passando para o controle não está mais disponível para configurar no cliente e foi removido para uso.
ms.openlocfilehash: 2db859ad33a697d5bca632ca9b6677a3a67bd103
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-remote-call-control-in-skype-for-business-2015"></a><span data-ttu-id="a621c-105">Planejamento de controle de chamada remota no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="a621c-105">Plan for remote call control in Skype for Business 2015</span></span>
 
<span data-ttu-id="a621c-106">Controle de chamada remota era um recurso nas versões anteriores do Microsoft Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a621c-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="a621c-107">Skype para Business Server, esse recurso foi substituído com a chamada Via trabalho.</span><span class="sxs-lookup"><span data-stu-id="a621c-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="a621c-108">*Nas versões do cliente para Skype para Business Server 2015 e de chamada remoto, encaminhar de passando para o controle não está mais disponível para configurar no cliente e foi removido para uso.*</span><span class="sxs-lookup"><span data-stu-id="a621c-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="a621c-109">Usuários de controle de chamada remota em sua organização hospedados em servidores Front-End executando o Lync Server podem continuar a usar o controle de chamada remota, mesmo que estejam usando um Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="a621c-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="a621c-110">No entanto, para todos os usuários hospedagem no Skype para Business Server, o controle de chamada remota não é suportado.</span><span class="sxs-lookup"><span data-stu-id="a621c-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="a621c-111">Consulte a tabela a seguir das combinações servidor/cliente e se elas podem suportar o controle de chamada remota ou Telefonar via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="a621c-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="a621c-112">**Skype para negócios 2015 cliente com Skype UI habilitado**</span><span class="sxs-lookup"><span data-stu-id="a621c-112">**Skype for Business 2015 Client With Skype UI enabled**</span></span>|<span data-ttu-id="a621c-113">**Skype para negócios 2015 With Lync UI do cliente habilitado**</span><span class="sxs-lookup"><span data-stu-id="a621c-113">**Skype for Business 2015 Client With Lync UI enabled**</span></span>|<span data-ttu-id="a621c-114">**Skype para Business 2016 Client**</span><span class="sxs-lookup"><span data-stu-id="a621c-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="a621c-115">**Cliente do Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="a621c-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="a621c-116">**Cliente do Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="a621c-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a621c-117">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a621c-117">Skype for Business Server 2015</span></span> <br/> |<span data-ttu-id="a621c-118">Chamada via Trabalho</span><span class="sxs-lookup"><span data-stu-id="a621c-118">Call via Work</span></span>  <br/> |<span data-ttu-id="a621c-119">1</span><span class="sxs-lookup"><span data-stu-id="a621c-119">1</span></span> <br/> |<span data-ttu-id="a621c-120">Chamada via Trabalho</span><span class="sxs-lookup"><span data-stu-id="a621c-120">Call via Work</span></span>  <br/> |<span data-ttu-id="a621c-121">1</span><span class="sxs-lookup"><span data-stu-id="a621c-121">1</span></span> <br/> |<span data-ttu-id="a621c-122">1</span><span class="sxs-lookup"><span data-stu-id="a621c-122">1</span></span> <br/> |
| <span data-ttu-id="a621c-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a621c-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="a621c-124">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="a621c-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a621c-125">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="a621c-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a621c-126">1</span><span class="sxs-lookup"><span data-stu-id="a621c-126">1</span></span> <br/> |<span data-ttu-id="a621c-127">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="a621c-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a621c-128">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="a621c-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="a621c-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a621c-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="a621c-130">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="a621c-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a621c-131">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="a621c-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a621c-132">1</span><span class="sxs-lookup"><span data-stu-id="a621c-132">1</span></span> <br/> |<span data-ttu-id="a621c-133">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="a621c-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="a621c-134">Controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="a621c-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="a621c-135">Nenhum recurso é suportado.</span><span class="sxs-lookup"><span data-stu-id="a621c-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="a621c-136">Para obter mais informações, consulte [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) na documentação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a621c-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a621c-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a621c-137">See also</span></span>

#### 

[<span data-ttu-id="a621c-138">Planejar para chamada Via trabalho no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a621c-138">Plan for Call Via Work in Skype for Business Server 2015</span></span>](call-via-work.md)
  
[<span data-ttu-id="a621c-139">Comparação de recursos do cliente de desktop do Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="a621c-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
#### 

[<span data-ttu-id="a621c-140">Tornar um Skype para chamada de negócios, mas usar seu telefone de mesa PBX para áudio</span><span class="sxs-lookup"><span data-stu-id="a621c-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

