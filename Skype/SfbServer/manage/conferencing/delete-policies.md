---
title: Excluir políticas de conferência do Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Resumo: Saiba como excluir políticas de conferência do Skype para Business Server.'
ms.openlocfilehash: 534dc52e730051b82c7f5edcb1bd2564be7dde2f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919434"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="b0d7d-103">Excluir políticas de conferência do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b0d7d-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="b0d7d-104">**Resumo:** Aprenda a excluir políticas de conferência do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b0d7d-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="b0d7d-105">Você pode excluir diretivas de conferência usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="b0d7d-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b0d7d-106">Excluir diretivas de conferência usando o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="b0d7d-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b0d7d-107">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b0d7d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b0d7d-108">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="b0d7d-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b0d7d-109">Na barra de navegação esquerda, clique em **Conferência** e, então, clique em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="b0d7d-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="b0d7d-110">Na lista de políticas de conferência, clique na política de site ou usuário que deseja excluir, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b0d7d-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b0d7d-111">Excluir diretivas de conferência usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="b0d7d-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b0d7d-112">Para excluir as políticas de conferência, use o cmdlet **Remove-CsConferencingPolicy**:</span><span class="sxs-lookup"><span data-stu-id="b0d7d-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="b0d7d-113">O comando a seguir remove a política de conferência com a identidade RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="b0d7d-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="b0d7d-114">O comando a seguir exclui todas as políticas de conferência que permitem que os usuários externos registrem a conferência:</span><span class="sxs-lookup"><span data-stu-id="b0d7d-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="b0d7d-115">Para obter mais informações, incluindo a sintaxe completa e uma lista de parâmetros, consulte [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b0d7d-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

