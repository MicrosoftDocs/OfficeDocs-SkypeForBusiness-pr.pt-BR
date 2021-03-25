---
title: Habilitar ou desabilitar a conferência discada no Skype for Business Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Resumo: Saiba como usar o Painel de Controle ou o Shell de Gerenciamento para habilitar ou desabilitar a conferência discada no Skype for Business Server.'
ms.openlocfilehash: ade7753f480856d68535daadda40eac6296a5d6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119460"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="77dd0-103">Habilitar ou desabilitar a conferência discada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="77dd0-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="77dd0-104">**Resumo:** Saiba como usar o Painel de Controle ou o Shell de Gerenciamento para habilitar ou desabilitar a conferência discada no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="77dd0-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="77dd0-105">Você pode habilitar a conferência discada usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="77dd0-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="77dd0-106">Habilitar ou desabilitar a conferência discada usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="77dd0-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="77dd0-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="77dd0-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="77dd0-108">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="77dd0-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="77dd0-109">Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**</span><span class="sxs-lookup"><span data-stu-id="77dd0-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="77dd0-110">Na lista de políticas de conferência, selecione a política que deseja ativar na conferência discada, clique em **Editar** e, então, em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="77dd0-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="77dd0-p101">Para permitir que os usuários participen por conexão discada, marque a caixa de verificação **Ativar a conferência via conexão discada PSTN**. Por padrão, os usuários podem discar para reuniões utilizando a 	Rede Telefônica Pública Comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="77dd0-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="77dd0-113">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="77dd0-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="77dd0-114">Habilitar ou desabilitar a conferência discada usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="77dd0-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="77dd0-115">Para habilitar ou desabilitar a conferência discada, use o cmdlet **Set-CsConferencingPolicy** com o parâmetro EnableDialInConferencing da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="77dd0-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="77dd0-116">Para obter mais informações, [consulte Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="77dd0-116">For more information, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
