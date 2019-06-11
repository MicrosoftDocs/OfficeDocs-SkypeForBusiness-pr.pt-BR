---
title: 'Lync Server 2013: adicionar uma política de localização a um site de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9ee6b5ba89cef592e137104df9e80d9373b5f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="2c839-102">Adicionar uma política de localização a um site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c839-102">Add a location policy to a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c839-103">_**Tópico da última modificação:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="2c839-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="2c839-104">Os exemplos a seguir mostram como adicionar a política de localização **Redmond** definida em [Create Location Policies in the Lync Server 2013](lync-server-2013-create-location-policies.md) a um site de rede existente e como criar um novo site de rede que usa a política de localização de **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="2c839-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="2c839-105">Para obter detalhes sobre como trabalhar com sites de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="2c839-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="2c839-106">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="2c839-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="2c839-107">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="2c839-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="2c839-108">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="2c839-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="2c839-109">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="2c839-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="2c839-110">Para atribuir uma política de local a um site de rede existente</span><span class="sxs-lookup"><span data-stu-id="2c839-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="2c839-111">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c839-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2c839-112">Execute os cmdlets a seguir para modificar um site de rede existente.</span><span class="sxs-lookup"><span data-stu-id="2c839-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="2c839-113">Atribua a política de Local marcada **Redmond** a um site de rede existente denominado **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="2c839-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="2c839-114">Para atribuir uma política de local a um novo site de rede</span><span class="sxs-lookup"><span data-stu-id="2c839-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="2c839-115">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c839-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2c839-116">Execute o seguinte cmdlet para criar um novo site de rede.</span><span class="sxs-lookup"><span data-stu-id="2c839-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="2c839-117">Crie um novo site de rede na região de rede e atribua a política de local marcada **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="2c839-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

