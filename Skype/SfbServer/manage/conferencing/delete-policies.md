---
title: Excluir políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Resumo: Saiba como excluir políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119500"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="f611f-103">Excluir políticas de conferência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f611f-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="f611f-104">**Resumo:** Saiba como excluir políticas de conferência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f611f-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="f611f-105">Você pode excluir políticas de conferência usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f611f-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f611f-106">Excluir políticas de conferência usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f611f-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f611f-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f611f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="f611f-108">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f611f-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f611f-109">Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**</span><span class="sxs-lookup"><span data-stu-id="f611f-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="f611f-110">Na lista de políticas de conferência, clique no site ou na política de usuário que você deseja **excluir,** clique em **Editar** e clique em Excluir .</span><span class="sxs-lookup"><span data-stu-id="f611f-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f611f-111">Excluir políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f611f-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f611f-112">Para excluir políticas de conferência, use o cmdlet **Remove-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="f611f-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="f611f-113">O comando a seguir remove a política de conferência com a identidade RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="f611f-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="f611f-114">O próximo comando exclui todas as políticas de conferência que permitem que usuários externos gravem a conferência:</span><span class="sxs-lookup"><span data-stu-id="f611f-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="f611f-115">Para obter mais informações, incluindo sintaxe completa e uma lista de parâmetros, consulte [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f611f-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
