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
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205074"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="fefe0-103">Quais são as restrições de caractere especial nas políticas de equipes?</span><span class="sxs-lookup"><span data-stu-id="fefe0-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="fefe0-104">**Embora os caracteres especiais podem ser usados para criar políticas de equipes com o PowerShell, você será limitada no gerenciamento essas políticas.  Sendo assim, é altamente recomendável nomes de política não incluir caracteres especiais.**</span><span class="sxs-lookup"><span data-stu-id="fefe0-104">**Although special characters can be used for creating Teams policies with PowerShell, you will be limited in managing these policies .  As such, we strongly recommend policy names do not include special characters.**</span></span>

<span data-ttu-id="fefe0-105">Nomes de política que você criar usando o PowerShell para reuniões e bate-papo no equipes podem ter caracteres especiais, como @, #, $.</span><span class="sxs-lookup"><span data-stu-id="fefe0-105">Policy names that you create using PowerShell for meetings and chat in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="fefe0-106">No entanto, se você estiver buscando editar a política no Microsoft Teams e Skype para centro de administração de negócios, você não conseguirá.</span><span class="sxs-lookup"><span data-stu-id="fefe0-106">However, if you are wanting to edit the policy in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="fefe0-107">Você deve usar o Windows PowerShell e o cmdlet diretiva correta para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="fefe0-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="fefe0-108">Se você tiver um objeto de diretiva com caracteres especiais e você deseja remover os caracteres especiais para gerenciar melhor a política na Microsoft Teams e Skype para centro de administração de negócios, você precisará usar o abaixo procedimento.</span><span class="sxs-lookup"><span data-stu-id="fefe0-108">If you have a policy object with special characters and you want to remove the special characters in order to better manage the policy in the Microsoft Teams and Skype for Business admin center, you will need to use the below procedure.</span></span> 

<span data-ttu-id="fefe0-109">Observação: O procedimento organizado aqui usa o exemplo de uma política de mensagens.</span><span class="sxs-lookup"><span data-stu-id="fefe0-109">Note: The procedure articulated here uses the example of a Messaging policy.</span></span>  <span data-ttu-id="fefe0-110">O mesmo processo seria usado para outro tipo de política (por exemplo em reuniões) por subsituting os cmdlets relevantes.</span><span class="sxs-lookup"><span data-stu-id="fefe0-110">The same process would be used for another policy type (Meetings for example) by subsituting the relevant cmdlets.</span></span> 

<span data-ttu-id="fefe0-111">1). chamar Get-CSMessagingPolicy-identity < nome_da_diretiva_antiga > e capture a saída da política.</span><span class="sxs-lookup"><span data-stu-id="fefe0-111">1.) Call Get-CSMessagingPolicy -identity <old_policy_name> and capture the output of the policy.</span></span>
<span data-ttu-id="fefe0-112">2). chamar Set-CSMessagingPolicy-identity < nome_da_diretiva_nova > para criar uma nova política com a mesma configuração como a diretiva original, mas sem caracteres especiais no nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="fefe0-112">2.) Call Set-CSMessagingPolicy -identity <new_policy_name> to create a new policy with the same configuration as the original policy but without any special characters in the name.</span></span>
<span data-ttu-id="fefe0-113">3.) chamada Delete-CSMessagingPolicy-identity < nome_da_diretiva_antiga > para excluir a diretiva.</span><span class="sxs-lookup"><span data-stu-id="fefe0-113">3.) Call Delete-CSMessagingPolicy -identity <old_policy_name> to delete the policy.</span></span>  <span data-ttu-id="fefe0-114">Se este comando for bem-sucedido, você terminar e pode começar a atribuir usuários à nova diretiva usando o PowerShell ou o Microsoft Teams e Skype para centro de administração de negócios.</span><span class="sxs-lookup"><span data-stu-id="fefe0-114">If this command succeeds, you're done and can begin to assign users to the new policy using either PowerShell or the Microsoft Teams and Skype for Business admin center.</span></span>
<span data-ttu-id="fefe0-115">4.) se o comando acima não tiver êxito, é porque a diretiva old foi atribuída a um usuário.</span><span class="sxs-lookup"><span data-stu-id="fefe0-115">4.) If the above command does not succeed, it is because the old policy has been assigned to a user.</span></span>  <span data-ttu-id="fefe0-116">Executar retirar a atribuição de cmdlet para retirar a atribuição de política de usuário, atribua a nova política e execute dwlete novamente.</span><span class="sxs-lookup"><span data-stu-id="fefe0-116">Run unassign cmdlet to unassign the policy from user, assign new policy, then run dwlete again.</span></span>


