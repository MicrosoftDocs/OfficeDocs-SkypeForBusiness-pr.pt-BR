---
title: Como devo inserir os números de telefone?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Saiba como configurar os números de telefone quando transportá-las para Skype para negócios. '
ms.openlocfilehash: 8d214ea7cf21ea713de28763f36b9995160fb395
ms.sourcegitcommit: c5940ef2674a00281604045baf8b2a320c4b189d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2018
ms.locfileid: "24958137"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="02ce8-103">Como devo inserir os números de telefone?</span><span class="sxs-lookup"><span data-stu-id="02ce8-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="02ce8-104">Quando você estiver portar números de telefone, você deverá inseri-los no formato correto.</span><span class="sxs-lookup"><span data-stu-id="02ce8-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="02ce8-105">Cada número de telefone ou o intervalo de número de telefone deve ser inserido separadamente em cada linha.</span><span class="sxs-lookup"><span data-stu-id="02ce8-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="02ce8-106">Quando você estiver inserindo números de telefone único:</span><span class="sxs-lookup"><span data-stu-id="02ce8-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="02ce8-107">Todos os caracteres especiais serão ignorados (incluindo o traço "-").</span><span class="sxs-lookup"><span data-stu-id="02ce8-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="02ce8-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="02ce8-108">For example:</span></span>
    
  - <span data-ttu-id="02ce8-109">Para um número de 10 dígitos: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* será corrigido para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="02ce8-110">Para um número de 11 dígitos: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** será corrigido para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="02ce8-111">Todas as marcas serão ignoradas se houver 10 ou 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="02ce8-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="02ce8-112">Por exemplo, \*\* \<div > 4255551234\</div >\*\* será **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="02ce8-113">"-", espaço e parêntese serão ignorada.</span><span class="sxs-lookup"><span data-stu-id="02ce8-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="02ce8-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="02ce8-114">For example:</span></span>
    
  - <span data-ttu-id="02ce8-115">Para um número de 10 dígitos: **(425) 555-6776** será corrigido para **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="02ce8-116">Para um número de 11 dígitos: **555-6776 1(425)** será corrigido para **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="02ce8-117">Todas as letras serão tratadas como caracteres especiais e ignoradas se não houver um número de telefone de 10 ou 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="02ce8-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="02ce8-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="02ce8-118">For example:</span></span>
    
  - <span data-ttu-id="02ce8-119">Para um número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** será corrigido para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="02ce8-120">Para um número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** será corrigido para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="02ce8-121">Qualquer combinação dos caracteres especiais, mesmo em outros idiomas, será corrigida.</span><span class="sxs-lookup"><span data-stu-id="02ce8-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="02ce8-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="02ce8-122">For example:</span></span> 
    
  - <span data-ttu-id="02ce8-123">Para um número de 10 dígitos:**中文4中文2ajj5\*() (\*(5() … 551345** será corrigido para **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="02ce8-124">Para um número de 11 dígitos:**中文4中文2$ a5\*() (\*(5() … 55 (.1345** será corrigido para **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="02ce8-125">Se qualquer números contiverem menos de 10 ou mais de 11 dígitos, eles serão realçados para o usuário corrigir:</span><span class="sxs-lookup"><span data-stu-id="02ce8-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="02ce8-126">\*\*5551245\* \* serão realçadas e precisa ser corrigido.</span><span class="sxs-lookup"><span data-stu-id="02ce8-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="02ce8-127">**1234567891011** será realçada e precisa ser corrigido.</span><span class="sxs-lookup"><span data-stu-id="02ce8-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="02ce8-128">Quaisquer números que são menos de 10 ou mais de 11 dígitos, com nenhum dos caracteres especiais serão realçados sem sendo corrigidas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="02ce8-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="02ce8-129">Para um número de 7 dígitos sem caracteres especiais que é inserido: **123456abcdefg7** será realçada e precisa ser corrigido, mas as letras não ser ignoradas.</span><span class="sxs-lookup"><span data-stu-id="02ce8-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="02ce8-130">Para um número de 7 dígitos com caracteres especiais que é inserido: **12345!@#$%^&amp;\*() – @# $% ^&amp;\*() 7** será realçado para ser corrigido.</span><span class="sxs-lookup"><span data-stu-id="02ce8-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="02ce8-131">Os caracteres especiais não ser ignorados.</span><span class="sxs-lookup"><span data-stu-id="02ce8-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="02ce8-132">Quando você estiver inserindo um intervalo de números de telefone.</span><span class="sxs-lookup"><span data-stu-id="02ce8-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="02ce8-133">Apenas dois números de telefone são permitidos.</span><span class="sxs-lookup"><span data-stu-id="02ce8-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="02ce8-134">O menor número deve ser o primeiro número no intervalo.</span><span class="sxs-lookup"><span data-stu-id="02ce8-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="02ce8-135">Todos os caracteres especiais (exceto o traço "-") são tratados da mesma como números único.</span><span class="sxs-lookup"><span data-stu-id="02ce8-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="02ce8-136">Por exemplo, **(425) 555 0&amp;\*(123-(1425) 5557899nm** será corrigido para **+ 14255550123 - +13202040659**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="02ce8-137">O "-" é usado para separar apenas dois números.</span><span class="sxs-lookup"><span data-stu-id="02ce8-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="02ce8-138">Isso não é suportado para incluir vários "-" no intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="02ce8-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="02ce8-139">Por exemplo, **(425) 555-0649-(425) 555-1115** deve ser inserido como **(425) 5550649 - for (425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="02ce8-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="02ce8-140">**Para instruções passo a passo, consulte [transferir os números de telefone para o Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span><span class="sxs-lookup"><span data-stu-id="02ce8-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

 > [!NOTE]
> <span data-ttu-id="02ce8-141">Se precisar de mais números de telefone, veja [Contatar o suporte de produtos para empresas - Ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="02ce8-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="02ce8-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="02ce8-142">Related topics</span></span>
[<span data-ttu-id="02ce8-143">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="02ce8-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="02ce8-144">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="02ce8-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="02ce8-145">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="02ce8-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="02ce8-146">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="02ce8-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="02ce8-147">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="02ce8-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 