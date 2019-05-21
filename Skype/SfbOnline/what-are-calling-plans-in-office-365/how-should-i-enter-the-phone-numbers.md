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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Saiba como configurar números de telefone ao portá-los para o Skype for Business. '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280526"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="b627b-103">Como devo inserir os números de telefone?</span><span class="sxs-lookup"><span data-stu-id="b627b-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="b627b-104">Ao fazer a portabilidade de números de telefone, você deve inseri-los no formato correto.</span><span class="sxs-lookup"><span data-stu-id="b627b-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b627b-105">Cada número de telefone ou intervalo de números de telefone deve ser inserido separadamente em cada linha.</span><span class="sxs-lookup"><span data-stu-id="b627b-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="b627b-106">Quando estiver inserindo números de telefone simples:</span><span class="sxs-lookup"><span data-stu-id="b627b-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="b627b-107">Todos os caracteres especiais serão ignorados (incluindo o traço "-").</span><span class="sxs-lookup"><span data-stu-id="b627b-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="b627b-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b627b-108">For example:</span></span>
    
  - <span data-ttu-id="b627b-109">Para um número de 10 dígitos: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* será corrigido para **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="b627b-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="b627b-110">Para um número de 11 dígitos: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** será corrigido para **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="b627b-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="b627b-111">Todas as marcas serão ignoradas se houver 10 ou 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="b627b-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="b627b-112">Por exemplo, \*\* \<div> 4255551234\</div>\*\* será **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="b627b-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="b627b-113">"-", espaço e parênteses serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="b627b-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="b627b-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b627b-114">For example:</span></span>
    
  - <span data-ttu-id="b627b-115">Para um número de 10 dígitos: **(425) 555-6776** será corrigido para **+ 14255556776**.</span><span class="sxs-lookup"><span data-stu-id="b627b-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="b627b-116">Para um número de 11 dígitos: **1 (425) 555-6776** será corrigido para **+ 14255556776**.</span><span class="sxs-lookup"><span data-stu-id="b627b-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="b627b-117">Todas as letras serão tratadas como caracteres especiais e ignoradas se houver um número de telefone de 10 ou 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="b627b-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="b627b-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b627b-118">For example:</span></span>
    
  - <span data-ttu-id="b627b-119">Para um número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** será corrigido para **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="b627b-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="b627b-120">Para um número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** será corrigido para **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="b627b-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="b627b-121">Qualquer combinação de caracteres especiais, até mesmo em outros idiomas, será corrigida.</span><span class="sxs-lookup"><span data-stu-id="b627b-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="b627b-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b627b-122">For example:</span></span> 
    
  - <span data-ttu-id="b627b-123">Para um número de 10 dígitos:**中文 4 中文2ajj5\*() (\*(5 ()... o 551345** será corrigido para **+ 14555551345**.</span><span class="sxs-lookup"><span data-stu-id="b627b-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="b627b-124">Para um número de 11 dígitos:**中文 4 中文 2 $ a5\*() (\*(5 ()... 55 (. 1345** será corrigido para **+ 14555551345**.</span><span class="sxs-lookup"><span data-stu-id="b627b-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="b627b-125">Se algum número contiver menos de 10 dígitos ou mais de 11 dígitos, ele será realçado para que o usuário corrija:</span><span class="sxs-lookup"><span data-stu-id="b627b-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="b627b-126">\*\*5551245\* \* será realçado e precisará ser corrigido.</span><span class="sxs-lookup"><span data-stu-id="b627b-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="b627b-127">**1234567891011** será realçado e precisará ser corrigido.</span><span class="sxs-lookup"><span data-stu-id="b627b-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="b627b-128">Todos os números com menos de 10 dígitos ou mais de 11 dígitos, com qualquer caractere especial, serão realçados sem serem corrigidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b627b-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="b627b-129">Para um número de 7 dígitos sem caracteres especiais inseridos: **123456abcdefg7** será realçado e precisará ser corrigido, mas as letras não serão ignoradas.</span><span class="sxs-lookup"><span data-stu-id="b627b-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="b627b-130">Para um número de 7 dígitos com caracteres especiais inseridos: **12345! @ # $% ^&amp;\*()--@ # $% ^&amp;\*() 7** será realçado para ser corrigido.</span><span class="sxs-lookup"><span data-stu-id="b627b-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="b627b-131">Os caracteres especiais não serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="b627b-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="b627b-132">Quando você estiver inserindo um intervalo de números de telefone.</span><span class="sxs-lookup"><span data-stu-id="b627b-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="b627b-133">Somente dois números de telefone são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b627b-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="b627b-134">O número menor deve ser o primeiro número no intervalo.</span><span class="sxs-lookup"><span data-stu-id="b627b-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="b627b-135">Todos os caracteres especiais (exceto o traço "-") são tratados da mesma forma que números únicos.</span><span class="sxs-lookup"><span data-stu-id="b627b-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="b627b-136">Por exemplo, **(425) 555 0&amp;\*(123-(1425) 5557899nm** será corrigido para **+ 14255550123-+ 13202040659**.</span><span class="sxs-lookup"><span data-stu-id="b627b-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="b627b-137">O "-" é usado apenas para separar os dois números.</span><span class="sxs-lookup"><span data-stu-id="b627b-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="b627b-138">Não há suporte para incluir vários "-" no intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="b627b-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="b627b-139">Por exemplo, **(425) 555-0649-(425) 555-1115** deve ser inserido como **(425) 5550649-(425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="b627b-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
  <span data-ttu-id="b627b-140">**Para obter instruções passo a passo completas, consulte [transferir números de telefone para o Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span><span class="sxs-lookup"><span data-stu-id="b627b-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

  > [!NOTE]
  > <span data-ttu-id="b627b-141">Se precisar de mais números de telefone, veja [Contatar o suporte de produtos para empresas - Ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="b627b-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="b627b-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b627b-142">Related topics</span></span>
[<span data-ttu-id="b627b-143">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="b627b-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="b627b-144">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="b627b-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="b627b-145">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="b627b-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="b627b-146">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="b627b-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="b627b-147">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="b627b-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 