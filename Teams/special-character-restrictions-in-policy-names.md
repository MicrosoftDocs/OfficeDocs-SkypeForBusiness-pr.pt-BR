---
title: Quais são as restrições de caractere especial nas políticas de equipes?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Consulte quais problemas que existem com caracteres especiais nos nomes de políticas e o que você pode fazer para corrigi-lo.
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192160"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="2955b-103">Quais são as restrições de caractere especial nas políticas de equipes?</span><span class="sxs-lookup"><span data-stu-id="2955b-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="2955b-104">**Embora você possa usar caracteres especiais nos nomes de políticas que você criou em equipes, é altamente recomendável que você não.**</span><span class="sxs-lookup"><span data-stu-id="2955b-104">**Although you can use special characters in the names of policies you created in Teams, we strongly recommend that you don't.**</span></span>

<span data-ttu-id="2955b-105">Nomes de política que você criar para reuniões, chat e prescense e outras coisas em equipes podem ter caracteres especiais, como @, #, $.</span><span class="sxs-lookup"><span data-stu-id="2955b-105">Policy names that you create for meetings, chat and prescense, and other things in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="2955b-106">No entanto, se você estiver buscando fazer alterações para o nome no Microsoft Teams e Skype para centro de administração de negócios, você não conseguirá.</span><span class="sxs-lookup"><span data-stu-id="2955b-106">However, if you are wanting to make changes to the name in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="2955b-107">Você deve usar o Windows PowerShell e o cmdlet diretiva correta para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="2955b-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="2955b-108">Por exemplo, se você tiver uma política de reunião com caracteres especiais e você deseja alterar o nome ou remova os caracteres especiais do nome, você precisará usar o cmdlet Set-CsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="2955b-108">For example, if you have a meeting policy with special characters and you want to change the name or remove the special characters from the name, you will need to use the Set-CsMeetingPolicy cmdlet.</span></span> 

<span data-ttu-id="2955b-109">Aqui está uma lista dos cmdlets de política que você pode precisar fazer isso:</span><span class="sxs-lookup"><span data-stu-id="2955b-109">Here is a list of the policy cmdlets that you may need to do this:</span></span>
1. <span data-ttu-id="2955b-110">Set-CsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="2955b-110">Set-CsMeetingPolicy</span></span>
2. <span data-ttu-id="2955b-111">Set-CsAppPolicy</span><span class="sxs-lookup"><span data-stu-id="2955b-111">Set-CsAppPolicy</span></span>
3. <span data-ttu-id="2955b-112">Set-\*</span><span class="sxs-lookup"><span data-stu-id="2955b-112">Set-\*</span></span>


