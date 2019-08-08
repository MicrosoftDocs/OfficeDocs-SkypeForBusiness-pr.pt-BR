---
title: Habilitar o controle de admissão de chamadas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilite o controle de admissão de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: a1a2259c754af0275e473e6c0d175039450cecf7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240492"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="cad91-103">Habilitar o controle de admissão de chamadas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cad91-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="cad91-104">Habilite o controle de admissão de chamadas no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cad91-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="cad91-105">Após definir as configurações de rede para a implantação do serviço de controle de admissão de chamadas, habilite o CAC para que as políticas de largura de banda entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="cad91-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="cad91-106">Para habilitar o controle de admissão de chamadas usando o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cad91-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="cad91-107">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="cad91-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="cad91-p101">Execute o cmdlet Set-CsNetworkConfiguration para ativar o CAC na rede. Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="cad91-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="cad91-110">Se você deseja desativar o CAC na rede, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cad91-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="cad91-111">Para habilitar o controle de admissão de chamadas usando o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cad91-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cad91-112">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cad91-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="cad91-113">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="cad91-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="cad91-114">Clique no botão de navegação **Global**.</span><span class="sxs-lookup"><span data-stu-id="cad91-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="cad91-115">Clique em **Global** na lista e selecione **Exibir detalhes** no menu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cad91-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="cad91-116">Na página **Editar Configurações Globais**, marque a caixa de seleção **Ativar controle de admissão de chamada**.</span><span class="sxs-lookup"><span data-stu-id="cad91-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cad91-117">Se você deseja desativar o controle de admissão de chamada durante a implantação, desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="cad91-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="cad91-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="cad91-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="cad91-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="cad91-119">See also</span></span>

[<span data-ttu-id="cad91-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="cad91-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="cad91-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="cad91-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="cad91-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="cad91-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
