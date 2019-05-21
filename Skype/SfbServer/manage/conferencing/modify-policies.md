---
title: Modificar políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Resumo: saiba como modificar as políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: b2c192948f0119a70f031c1c2bbe5de8e776c2f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280408"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="3f58d-103">Modificar políticas de conferência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f58d-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="3f58d-104">**Resumo:** Saiba como modificar as políticas de conferência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f58d-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="3f58d-105">Você pode modificar as políticas de conferência usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f58d-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3f58d-106">Modificar políticas de conferência usando o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f58d-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3f58d-107">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3f58d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="3f58d-108">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f58d-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3f58d-109">Na barra de navegação esquerda, clique em **Conferência** e, em seguida, clique em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="3f58d-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="3f58d-110">Na lista de políticas de conferência, clique na política que deseja alterar, em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3f58d-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="3f58d-111">Em **Editar Política de Conferências**, modifique qualquer uma das configurações de política, exceto seu nome, que não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="3f58d-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="3f58d-112">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3f58d-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3f58d-113">Modificar políticas de conferência usando o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f58d-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3f58d-114">Para modificar as políticas de conferência, use o cmdlet **set-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="3f58d-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="3f58d-115">O seguinte exemplo modifica um valor de propriedade da política de conferência SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="3f58d-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="3f58d-116">O comando define o valor da propriedade AllowConferenceRecording como False:</span><span class="sxs-lookup"><span data-stu-id="3f58d-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="3f58d-117">Para obter mais informações, incluindo a sintaxe completa e uma lista de parâmetros, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3f58d-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

