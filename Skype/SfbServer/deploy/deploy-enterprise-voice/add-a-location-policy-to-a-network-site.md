---
title: Adicionar uma política de localização a um site de rede no Skype for Business Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Atribua políticas de localização E9-1-1 a sites de rede no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 4a74b1ee44d1e2f34a51d7859235e10649d0e2ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233864"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="3ea5c-103">Adicionar uma política de localização a um site de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3ea5c-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="3ea5c-104">Atribua políticas de localização E9-1-1 a sites de rede no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="3ea5c-105">Os exemplos a seguir mostram como adicionar a política de localização de **Redmond** definida em [criar políticas de localização no Skype for Business Server](create-location-policies.md) a um site de rede existente e como criar um novo site de rede que usa a política de localização de **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="3ea5c-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="3ea5c-106">Para obter detalhes sobre como trabalhar com sites de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="3ea5c-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="3ea5c-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="3ea5c-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="3ea5c-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="3ea5c-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="3ea5c-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="3ea5c-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="3ea5c-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="3ea5c-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="3ea5c-111">Para atribuir uma política de local a um site de rede existente</span><span class="sxs-lookup"><span data-stu-id="3ea5c-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="3ea5c-112">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3ea5c-113">Execute os cmdlets a seguir para modificar um site de rede existente.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="3ea5c-114">Atribua a política de Local marcada **Redmond** a um site de rede existente denominado **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="3ea5c-115">Para atribuir uma política de local a um novo site de rede</span><span class="sxs-lookup"><span data-stu-id="3ea5c-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="3ea5c-116">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3ea5c-117">Execute o seguinte cmdlet para criar um novo site de rede.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="3ea5c-118">Crie um novo site de rede na região de rede e atribua a política de local marcada **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


