---
title: Excluir configurações de reunião no Skype for Business Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Resumo: saiba como excluir as configurações de reunião no Skype for Business Server.'
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119490"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d509c-103">Excluir configurações de reunião no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d509c-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d509c-104">**Resumo:** Saiba como excluir as configurações de reunião no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d509c-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="d509c-105">Você pode excluir as configurações de reunião usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d509c-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="d509c-106">Você pode excluir uma configuração de site ou usuário, mas não pode excluir a configuração global.</span><span class="sxs-lookup"><span data-stu-id="d509c-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="d509c-107">Se você tentar excluir a configuração global, ela será redefinida automaticamente para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="d509c-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d509c-108">Excluir configurações de reunião usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d509c-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d509c-109">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d509c-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d509c-110">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d509c-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d509c-111">Na barra de navegação esquerda, clique **em Conferência** e em **Configuração de Reunião.**</span><span class="sxs-lookup"><span data-stu-id="d509c-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="d509c-112">Na lista de configurações de reunião, clique na configuração do site ou pool que você deseja excluir, clique em **Editar** e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d509c-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d509c-113">Excluir configurações de reunião usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d509c-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d509c-114">Para excluir as configurações de reunião, use o cmdlet **Remove-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="d509c-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="d509c-115">O comando a seguir remove as configurações de reunião aplicadas ao site redmond:</span><span class="sxs-lookup"><span data-stu-id="d509c-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="d509c-116">O próximo comando remove todas as configurações de reunião aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="d509c-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="d509c-117">Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d509c-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
