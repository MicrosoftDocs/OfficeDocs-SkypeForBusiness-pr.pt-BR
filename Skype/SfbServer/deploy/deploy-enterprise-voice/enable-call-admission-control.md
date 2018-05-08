---
title: Habilitar o serviço de controle de admissão de chamadas no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilite o controle de admissão de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 321b7838a2a818a9791b72e3851312006eb8dc7e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="enable-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="63aef-103">Habilitar o serviço de controle de admissão de chamadas no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="63aef-103">Enable call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="63aef-104">Habilite o controle de admissão de chamada no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="63aef-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="63aef-105">Após definir as configurações de rede para a implantação do serviço de controle de admissão de chamadas, habilite o CAC para que as políticas de largura de banda entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="63aef-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="63aef-106">Para habilitar o controle de admissão de chamada usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="63aef-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="63aef-107">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="63aef-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="63aef-p101">Execute o cmdlet Set-CsNetworkConfiguration para ativar o CAC na rede. Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="63aef-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="63aef-110">Se você deseja desativar o CAC na rede, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="63aef-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="63aef-111">Para habilitar o controle de admissão de chamada usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="63aef-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="63aef-112">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="63aef-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="63aef-113">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="63aef-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="63aef-114">Clique no botão de navegação **Global**.</span><span class="sxs-lookup"><span data-stu-id="63aef-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="63aef-115">Clique em **Global** na lista e selecione **Exibir detalhes** no menu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="63aef-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="63aef-116">Na página **Editar Configurações Globais**, marque a caixa de seleção **Ativar controle de admissão de chamada**.</span><span class="sxs-lookup"><span data-stu-id="63aef-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="63aef-117">Se você deseja desativar o controle de admissão de chamada durante a implantação, desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="63aef-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="63aef-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="63aef-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="63aef-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="63aef-119">See also</span></span>

#### 

[<span data-ttu-id="63aef-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="63aef-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="63aef-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="63aef-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="63aef-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="63aef-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)

