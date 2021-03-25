---
title: Modificar configurações de reunião no Skype for Business Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumo: Saiba como modificar as configurações de reunião no Skype for Business Server.'
ms.openlocfilehash: 2f0d1220312ac810d26fdd4691492133e54db9b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119410"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="605ca-103">Modificar configurações de reunião no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="605ca-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="605ca-104">**Resumo:** Saiba como modificar as configurações de reunião no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="605ca-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="605ca-105">Você pode modificar as configurações de reunião usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="605ca-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="605ca-106">Modificar configurações de reunião usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="605ca-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="605ca-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="605ca-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="605ca-108">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="605ca-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="605ca-109">Na barra de navegação esquerda, clique **em Conferência** e em **Configuração de Reunião.**</span><span class="sxs-lookup"><span data-stu-id="605ca-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="605ca-110">Na lista de configurações de reunião, clique na configuração que você deseja alterar, clique em **Editar** e em **Mostrar detalhes.**</span><span class="sxs-lookup"><span data-stu-id="605ca-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="605ca-111">Em **Editar configuração de reunião**, modifique qualquer definição da configuração, exceto o nome da configuração, que não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="605ca-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="605ca-112">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="605ca-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="605ca-113">Modificar configurações de reunião usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="605ca-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="605ca-114">Para modificar as configurações de reunião, use o cmdlet **Set-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="605ca-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="605ca-115">O comando mostrado no exemplo a seguir modifica as configurações de reunião atribuídas ao site redmond (-Identity site:Redmond).</span><span class="sxs-lookup"><span data-stu-id="605ca-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="605ca-116">Nesse caso, o valor da propriedade DesignateAsPresenter é definido como Todos:</span><span class="sxs-lookup"><span data-stu-id="605ca-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="605ca-117">Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="605ca-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
