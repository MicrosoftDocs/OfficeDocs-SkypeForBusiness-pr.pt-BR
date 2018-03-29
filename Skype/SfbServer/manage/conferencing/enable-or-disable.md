---
title: Habilitar ou desabilitar a conferência discada no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Resumo: Saiba como usar o painel de controle ou o Shell de gerenciamento para habilitar ou desabilitar conferência discada no Skype para Business Server 2015.'
ms.openlocfilehash: 6441e548ce944cdd8786178ed7b80b0af7d625f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server-2015"></a><span data-ttu-id="0b745-103">Habilitar ou desabilitar a conferência discada no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0b745-103">Enable or disable dial-in conferencing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0b745-104">**Resumo:** Saiba como usar o painel de controle ou o Shell de gerenciamento para habilitar ou desabilitar conferência discada no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0b745-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0b745-105">Você pode habilitar a conferência discada usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0b745-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0b745-106">Habilitar ou desabilitar conferência discada usando Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="0b745-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0b745-107">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="0b745-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="0b745-108">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0b745-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0b745-109">Na barra de navegação esquerda, clique em **Conferência** e, então, clique em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="0b745-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="0b745-110">Na lista de políticas de conferência, selecione a política que deseja ativar na conferência discada, clique em **Editar** e, então, em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="0b745-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="0b745-p101">Para permitir que os usuários participem por conexão discada, marque a caixa de verificação **Ativar a conferência via conexão discada PSTN**. Por padrão, os usuários podem discar para reuniões utilizando a Rede Telefônica Pública Comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="0b745-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="0b745-113">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0b745-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0b745-114">Habilitar ou desabilitar conferência discada usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="0b745-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0b745-115">Para ativar ou desativar a conferência discada, use o cmdlet **Set-Cs ConferencingPolicy** com o parâmetro EnableDialInConferencing da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="0b745-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="0b745-116">Para obter mais informações, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0b745-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

