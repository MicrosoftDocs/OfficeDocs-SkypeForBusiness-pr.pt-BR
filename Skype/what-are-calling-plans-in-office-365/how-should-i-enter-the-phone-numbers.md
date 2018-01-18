---
title: "Como deve inserir os números de telefone?"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom: Calling Plans
description: "Saiba como configurar os números de telefone quando transportá-las para Skype para negócios. "
ms.openlocfilehash: 1906fc98f47402ec740d71ff69b67b07392ae57d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="fefaa-103">Como deve inserir os números de telefone?</span><span class="sxs-lookup"><span data-stu-id="fefaa-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="fefaa-104">Quando você estiver portar números de telefone, você deverá inseri-los no formato correto.</span><span class="sxs-lookup"><span data-stu-id="fefaa-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fefaa-105">Cada número de telefone ou o intervalo de número de telefone deve ser inserido separadamente em cada linha.</span><span class="sxs-lookup"><span data-stu-id="fefaa-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="fefaa-106">Quando você estiver inserindo números de telefone único:</span><span class="sxs-lookup"><span data-stu-id="fefaa-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="fefaa-107">Todos os caracteres especiais serão ignorados (incluindo o traço "-").</span><span class="sxs-lookup"><span data-stu-id="fefaa-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="fefaa-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fefaa-108">For example:</span></span>
    
  - <span data-ttu-id="fefaa-109">Para um número de 10 dígitos: \*\* &amp; \\*(425\\*() (\\*&amp;4&amp;\\*()) (\\*250649\*\* será corrigido para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-109">For a 10-digit number: **&amp;\\*(425\\*()(\\*&amp;4&amp;\\*())(\\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="fefaa-110">Para um número de 11 dígitos: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** será corrigido para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="fefaa-111">Todas as marcas serão ignoradas se houver 10 ou 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="fefaa-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="fefaa-112">Por exemplo, ** \<div > 4255551234\</div >** será **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="fefaa-113">"-", espaço e parêntese serão ignorada.</span><span class="sxs-lookup"><span data-stu-id="fefaa-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="fefaa-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fefaa-114">For example:</span></span>
    
  - <span data-ttu-id="fefaa-115">Para um número de 10 dígitos: **(425) 555-6776** será corrigido para **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="fefaa-116">Para um número de 11 dígitos: **555-6776 1(425)** será corrigido para **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="fefaa-117">Todas as letras serão tratadas como caracteres especiais e ignoradas se não houver um número de telefone de 10 ou 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="fefaa-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="fefaa-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fefaa-118">For example:</span></span>
    
  - <span data-ttu-id="fefaa-119">Para um número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** será corrigido para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="fefaa-120">Para um número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** será corrigido para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="fefaa-121">Qualquer combinação dos caracteres especiais, mesmo em outros idiomas, será corrigida.</span><span class="sxs-lookup"><span data-stu-id="fefaa-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="fefaa-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fefaa-122">For example:</span></span> 
    
  - <span data-ttu-id="fefaa-123">Para um número de 10 dígitos:**中文4中文2ajj5\*() (\*(5() … 551345** será corrigido para **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="fefaa-124">Para um número de 11 dígitos:**中文4中文2$ a5\*() (\*(5() … 55 (.1345** será corrigido para **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="fefaa-125">Se qualquer números contiverem menos de 10 ou mais de 11 dígitos, eles serão realçados para o usuário corrigir:</span><span class="sxs-lookup"><span data-stu-id="fefaa-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="fefaa-126">\*\*5551245\* \* serão realçadas e precisa ser corrigido.</span><span class="sxs-lookup"><span data-stu-id="fefaa-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="fefaa-127">**1234567891011** será realçada e precisa ser corrigido.</span><span class="sxs-lookup"><span data-stu-id="fefaa-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="fefaa-128">Quaisquer números que são menos de 10 ou mais de 11 dígitos, com nenhum dos caracteres especiais serão realçados sem sendo corrigidas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fefaa-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="fefaa-129">Para um número de 7 dígitos sem caracteres especiais que é inserido: **123456abcdefg7** será realçada e precisa ser corrigido, mas as letras não ser ignoradas.</span><span class="sxs-lookup"><span data-stu-id="fefaa-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="fefaa-130">Para um número de 7 dígitos com caracteres especiais que é inserido: **12345!@#$%^&amp;\*() – @# $% ^&amp;\*() 7** será realçado para ser corrigido.</span><span class="sxs-lookup"><span data-stu-id="fefaa-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="fefaa-131">Os caracteres especiais não ser ignorados.</span><span class="sxs-lookup"><span data-stu-id="fefaa-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="fefaa-132">Quando você estiver inserindo um intervalo de números de telefone.</span><span class="sxs-lookup"><span data-stu-id="fefaa-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="fefaa-133">Apenas dois números de telefone são permitidos.</span><span class="sxs-lookup"><span data-stu-id="fefaa-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="fefaa-134">O menor número deve ser o primeiro número no intervalo.</span><span class="sxs-lookup"><span data-stu-id="fefaa-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="fefaa-135">Todos os caracteres especiais (exceto o traço "-") são tratados da mesma como números único.</span><span class="sxs-lookup"><span data-stu-id="fefaa-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="fefaa-136">Por exemplo, **(425) 555 0&amp;\\*(123-(1425) 5557899nm** será corrigido para **+ 14255550123 - +13202040659**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-136">For example, **(425)555 0&amp;\\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="fefaa-137">O "-" é usado para separar apenas dois números.</span><span class="sxs-lookup"><span data-stu-id="fefaa-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="fefaa-138">Isso não é suportado para incluir vários "-" no intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="fefaa-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="fefaa-139">Por exemplo, **(425) 555-0649-(425) 555-1115** deve ser inserido como **(425) 5550649 - for (425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="fefaa-140">**Para instruções passo a passo, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).**</span><span class="sxs-lookup"><span data-stu-id="fefaa-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).**</span></span>

 > [!NOTE]
> <span data-ttu-id="fefaa-141">Se você precisar fazer mais números de telefone que isso, por favor, [contate o suporte para produtos de negócios - ajuda de Admin](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="fefaa-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="fefaa-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fefaa-142">Related topics</span></span>
[<span data-ttu-id="fefaa-143">Transferindo perguntas comuns de números de telefone</span><span class="sxs-lookup"><span data-stu-id="fefaa-143">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="fefaa-144">Diferentes tipos de números de telefone usados para planos de chamada</span><span class="sxs-lookup"><span data-stu-id="fefaa-144">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="fefaa-145">Gerenciar números de telefone para sua organização</span><span class="sxs-lookup"><span data-stu-id="fefaa-145">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="fefaa-146">Termos e condições para chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="fefaa-146">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="fefaa-147">Skype for Business Online: Rótulo de aviso de isenção de responsabilidade de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="fefaa-147">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)