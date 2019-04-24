---
title: Criar diretórios de conferência no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Resumo: Saiba como criar diretórios de conferência no Skype para Business Server.'
ms.openlocfilehash: 9e79ca7e1b2f896746db998cc53983c04c6724ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222748"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="854b4-103">Criar diretórios de conferência no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="854b4-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="854b4-104">**Resumo:** Aprenda a criar diretórios de conferência no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="854b4-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="854b4-105">Diretórios de conferência mantêm um mapeamento entre o ID de reunião alfanuméricos que um participante usa para ingressar em uma conferência ao usar o Skype para negócios e a ID de conferência apenas numérica que um participante de conferência discada usa para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="854b4-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="854b4-106">Criar um diretório de conferência</span><span class="sxs-lookup"><span data-stu-id="854b4-106">Create a conference directory</span></span>

<span data-ttu-id="854b4-107">Criar vários diretórios de conferência garantirá que os IDs de conferência sejam curtos até que uma quantidade significativa de conferências seja criada.</span><span class="sxs-lookup"><span data-stu-id="854b4-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="854b4-p101">Em uma organização com um número comum de conferências por usuário, recomendamos criar um diretório de conferência para cada 999 usuários no pool. Usando essa diretriz, os IDs podem ser geralmente mantidos pequenos. No entanto, assim que o número de diretórios de conferência (em todos os pools) ultrapassar 9, o tamanho do ID de conferência aumentará para suportar conferências adicionais.</span><span class="sxs-lookup"><span data-stu-id="854b4-p101">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline, the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="854b4-111">O formato de um ID de conferência é como segue:</span><span class="sxs-lookup"><span data-stu-id="854b4-111">The format of a conference ID is as follows:</span></span> 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="854b4-p102">Para criar um novo diretório de conferência, use o cmdlet **New-CsConferenceDirectory**. Por exemplo, o seguinte cria um diretório de conferência com a identidade 42, hospedado no pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="854b4-p102">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet. For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="854b4-114">Para obter mais informações, consulte [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="854b4-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  

