---
title: Excluir configurações de reunião no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Resumo: Saiba como excluir configurações de reunião no Skype para Business Server.'
ms.openlocfilehash: 47cde99751c90b71a52b70a0bde9aaf15acf0154
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222755"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9ad0d-103">Excluir configurações de reunião no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="9ad0d-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9ad0d-104">**Resumo:** Saiba como excluir configurações de reunião no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ad0d-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9ad0d-105">Você pode excluir configurações de reunião usando o Skype para painel de controle do Business Server ou usando Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="9ad0d-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="9ad0d-p101">Você pode excluir uma configuração de site ou de usuário, mas não a configuração global. Se você tentar excluir a configuração global, ela será automaticamente redefinida para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="9ad0d-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9ad0d-108">Excluir configurações de reunião usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="9ad0d-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9ad0d-109">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9ad0d-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="9ad0d-110">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="9ad0d-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9ad0d-111">Na barra de navegação à esquerda, clique em **Conferência** e em **Configuração da reunião**.</span><span class="sxs-lookup"><span data-stu-id="9ad0d-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="9ad0d-112">Na lista de configuração de reunião, clique na configuração de site ou pool que deseja excluir, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="9ad0d-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9ad0d-113">Excluir configurações de reunião usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="9ad0d-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9ad0d-114">Para excluir as configurações de reunião, use o cmdlet **Remove-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9ad0d-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="9ad0d-115">O comando a seguir remove as definições de configuração de reunião aplicadas ao site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="9ad0d-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="9ad0d-116">O próximo comando remove todas as definições de configuração de reunião aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="9ad0d-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="9ad0d-117">Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9ad0d-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

