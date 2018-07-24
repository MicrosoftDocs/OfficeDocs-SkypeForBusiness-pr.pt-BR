---
title: Modificar configurações de reunião no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumo: Saiba como modificar configurações de reunião no Skype para Business Server.'
ms.openlocfilehash: b4b8307711fcf7b120c867debe5ab3e2978f6ef7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978964"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="51afb-103">Modificar configurações de reunião no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="51afb-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="51afb-104">**Resumo:** Saiba como modificar configurações de reunião no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="51afb-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="51afb-105">Você pode modificar configurações de reunião usando o Skype para painel de controle do Business Server ou usando Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="51afb-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="51afb-106">Modificar configurações de reunião usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="51afb-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="51afb-107">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="51afb-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="51afb-108">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="51afb-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="51afb-109">Na barra de navegação à esquerda, clique em **Conferência**e em **Configuração da reunião**.</span><span class="sxs-lookup"><span data-stu-id="51afb-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="51afb-110">Na lista de configurações da reunião, clique na configuração que deseja alterar, em **Editar** e, em seguida, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="51afb-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="51afb-111">Em **Editar configuração da reunião**, modifique qualquer definição da configuração, exceto o nome da configuração, que não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="51afb-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="51afb-112">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="51afb-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="51afb-113">Modificar configurações de reunião usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="51afb-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="51afb-114">Para modificar as definições de configuração de reunião, use o cmdlet **Set-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="51afb-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="51afb-p101">O comando mostrado no exemplo a seguir modifica as definições de configuração de reuniões atribuídas ao site de Redmond (-Identity site:Redmond). Neste caso, o valor da propriedade DesignateAsPresenter é definido como Everyone:</span><span class="sxs-lookup"><span data-stu-id="51afb-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="51afb-117">Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="51afb-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

