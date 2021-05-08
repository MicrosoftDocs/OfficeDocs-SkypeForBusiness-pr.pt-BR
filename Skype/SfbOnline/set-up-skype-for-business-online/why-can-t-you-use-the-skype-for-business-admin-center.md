---
title: Por que não posso usar o centro de administração Skype for Business Online agora?
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- Setup
- ms.lync.lac.TenantInMigration
description: 'Saiba o que você pode ou não usar no centro de administração Skype for Business outros recursos quando seu serviço está sendo migrado para outro data center da Microsoft. '
ms.openlocfilehash: 725a60be96a2d61bcec6367e1a0a33f2bc5dcee6
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238912"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="438ac-103">Por que não posso usar o centro de administração Skype for Business Online agora?</span><span class="sxs-lookup"><span data-stu-id="438ac-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="438ac-104">[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?</span><span class="sxs-lookup"><span data-stu-id="438ac-104">[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?</span></span>

<span data-ttu-id="438ac-105">Sabemos que é frustrante quando você não consegue fazer seu trabalho, então explicaremos o que está acontecendo aqui e por que isso valerá a pena esperar.</span><span class="sxs-lookup"><span data-stu-id="438ac-105">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="438ac-106">Primeiro, aqui está a explicação técnica:</span><span class="sxs-lookup"><span data-stu-id="438ac-106">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="438ac-107">Estamos migrando seu serviço Skype for Business Online (ou seja, seus usuários e configurações organizacionais) para outro datacenter da Microsoft mais próximo de você.</span><span class="sxs-lookup"><span data-stu-id="438ac-107">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="438ac-108">Isso melhorará seu serviço e reduzirá a latência.</span><span class="sxs-lookup"><span data-stu-id="438ac-108">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="438ac-109">Para obter mais detalhes técnicos, consulte [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span><span class="sxs-lookup"><span data-stu-id="438ac-109">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="438ac-110">Ok, então o que isso significa?</span><span class="sxs-lookup"><span data-stu-id="438ac-110">OK, so what does that mean?</span></span>

<span data-ttu-id="438ac-111">Primeiro, vamos quebrar alguns termos.</span><span class="sxs-lookup"><span data-stu-id="438ac-111">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="438ac-112">**Data center** Esse é o local físico onde as informações do seu Microsoft 365 ou Office 365 são armazenadas, como seus arquivos e mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="438ac-112">**Data center** This is the physical location where the information from your Microsoft 365 or Office 365 is stored, such as your files and email messages.</span></span> <span data-ttu-id="438ac-113">Se você realmente deseja pesquisar o que são Microsoft 365 e Office 365 datacenters, confira[este artigo](https://www.microsoft.com/online/legal/v2/?docid=25).</span><span class="sxs-lookup"><span data-stu-id="438ac-113">If you really want to dig in to what Microsoft 365 and Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="438ac-114">**Migração** Isso é praticamente o mesmo que "mover".</span><span class="sxs-lookup"><span data-stu-id="438ac-114">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="438ac-115">Nesse caso, isso significa que estamos movendo seus usuários do Skype for Business Online e configurações de um datacenter para outro que está mais próximo de você para melhorar seu serviço.</span><span class="sxs-lookup"><span data-stu-id="438ac-115">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="438ac-116">**Latência** Esse é o tempo necessário para acessar o centro de administração Microsoft 365, fazer uma alteração nas configurações e salvar essas alterações.</span><span class="sxs-lookup"><span data-stu-id="438ac-116">**Latency** This is amount of time it takes you to access the Microsoft 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="438ac-117">**ID de correlação** Você pode ter visto isso listado na mensagem de onde acabou de chegar.</span><span class="sxs-lookup"><span data-stu-id="438ac-117">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="438ac-118">Essas informações são usadas pelos engenheiros de suporte da Microsoft para ajudá-lo a solucionar um erro.</span><span class="sxs-lookup"><span data-stu-id="438ac-118">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="438ac-119">Se você entrar em contato com o suporte da Microsoft, poderá ser solicitado a ID de Correlação.</span><span class="sxs-lookup"><span data-stu-id="438ac-119">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="438ac-120">Portanto, tudo isso significa que estamos no processo de mover todos os usuários do Skype for Business Online e configurações de serviço para outro local mais próximo de você.</span><span class="sxs-lookup"><span data-stu-id="438ac-120">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="438ac-121">Quanto mais próximo, melhor.</span><span class="sxs-lookup"><span data-stu-id="438ac-121">The closer the better.</span></span> <span data-ttu-id="438ac-122">A boa notícia é que, após esse curto período de tempo, seu serviço Skype for Business Online melhorará.</span><span class="sxs-lookup"><span data-stu-id="438ac-122">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Migração de serviço em Microsoft 365 ou Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="438ac-124">Quais Skype for Business recursos online ainda funcionarão?</span><span class="sxs-lookup"><span data-stu-id="438ac-124">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="438ac-125">Embora você não consiga acessar o centro de administração do Skype for Business Online, os seguintes recursos Skype for Business Online ainda funcionarão durante a migração:</span><span class="sxs-lookup"><span data-stu-id="438ac-125">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="438ac-126">Reuniões online</span><span class="sxs-lookup"><span data-stu-id="438ac-126">Online meetings</span></span>
    
- <span data-ttu-id="438ac-127">Informações de presença</span><span class="sxs-lookup"><span data-stu-id="438ac-127">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="438ac-128">Posso fazer outro trabalho?</span><span class="sxs-lookup"><span data-stu-id="438ac-128">Can I get other work done?</span></span>

<span data-ttu-id="438ac-129">Com certeza.</span><span class="sxs-lookup"><span data-stu-id="438ac-129">Sure.</span></span> <span data-ttu-id="438ac-130">Enquanto estamos migrando seu serviço Skype for Business Online, você ainda pode usar os outros centros de administração no Microsoft 365 (por exemplo, os centros de administração Microsoft 365 e Exchange de administração).</span><span class="sxs-lookup"><span data-stu-id="438ac-130">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Microsoft 365 (for example, the Microsoft 365 and Exchange admin centers).</span></span> <span data-ttu-id="438ac-131">No entanto, juntamente com o centro de administração do Skype for Business Online, você não poderá usar os cmdlets Skype for Business PowerShell remotos online durante a migração.</span><span class="sxs-lookup"><span data-stu-id="438ac-131">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="438ac-132">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="438ac-132">Related topics</span></span>
[<span data-ttu-id="438ac-133">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="438ac-133">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="438ac-134">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="438ac-134">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
