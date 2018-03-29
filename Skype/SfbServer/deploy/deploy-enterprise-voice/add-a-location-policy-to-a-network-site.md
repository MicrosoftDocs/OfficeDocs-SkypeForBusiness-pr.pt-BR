---
title: Adicionar uma política de local a um site de rede no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Atribua políticas de localização E9-1-1 a sites de rede no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: bf2b8675ebaa14e98f8a362b3a0714037000de95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a><span data-ttu-id="19449-103">Adicionar uma política de local a um site de rede no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="19449-103">Add a location policy to a network site in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="19449-104">Atribua políticas de localização E9-1-1 a sites de rede no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="19449-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="19449-105">Os seguintes exemplos mostram como adicionar a política de local de **Redmond** definida no [criar políticas de local no Skype para Business Server 2015](create-location-policies.md) a um site de rede existente e como criar um novo site de rede que usa o local de **Redmond** política.</span><span class="sxs-lookup"><span data-stu-id="19449-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server 2015](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="19449-106">Para obter detalhes sobre como trabalhar com sites de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="19449-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="19449-107">**New-CsNetworkSite.**</span><span class="sxs-lookup"><span data-stu-id="19449-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="19449-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="19449-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="19449-109">**Set-CsNetworkSite.**</span><span class="sxs-lookup"><span data-stu-id="19449-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="19449-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="19449-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="19449-111">Para atribuir uma política de local a um site de rede existente</span><span class="sxs-lookup"><span data-stu-id="19449-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="19449-112">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="19449-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="19449-113">Execute os cmdlets a seguir para modificar um site de rede existente.</span><span class="sxs-lookup"><span data-stu-id="19449-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="19449-114">Atribua a política de Local marcada **Redmond** a um site de rede existente denominado **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="19449-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="19449-115">Para atribuir uma política de local a um novo site de rede</span><span class="sxs-lookup"><span data-stu-id="19449-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="19449-116">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="19449-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="19449-117">Execute o seguinte cmdlet para criar um novo site de rede.</span><span class="sxs-lookup"><span data-stu-id="19449-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="19449-118">Crie um novo site de rede na região de rede e atribua a política de local marcada **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="19449-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


