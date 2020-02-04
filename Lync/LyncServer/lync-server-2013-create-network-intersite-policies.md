---
title: 'Lync Server 2013: criar políticas entre sites de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655cde30a3d798d57520c57e3882b2162010888c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="52883-102">Criar políticas entre sites de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52883-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52883-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="52883-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="52883-104">Uma *política* entre sites de rede define limitações de largura de banda entre sites que têm links diretos de WAN entre eles.</span><span class="sxs-lookup"><span data-stu-id="52883-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="52883-105">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="52883-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="52883-106">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="52883-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="52883-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="52883-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="52883-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="52883-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="52883-109">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="52883-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52883-110">Uma política entre sites de rede será necessária <EM>somente</EM> se houver um link cruzado direto entre dois sites de rede.</span><span class="sxs-lookup"><span data-stu-id="52883-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="52883-111">Na região América do Norte da topologia de exemplo, existe um link direto entre os sites Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="52883-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="52883-112">Esses dois sites exigem uma política entre sites que aplica um perfil de política de largura de banda apropriado.</span><span class="sxs-lookup"><span data-stu-id="52883-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="52883-113">O exemplo a seguir aplica o\_perfil do link de 20 MB.</span><span class="sxs-lookup"><span data-stu-id="52883-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="52883-114">Para criar uma política entre sites de rede</span><span class="sxs-lookup"><span data-stu-id="52883-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="52883-115">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="52883-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="52883-116">Execute o cmdlet New-CsNetworkInterSitePolicy para criar políticas entre sites de rede e aplicar um perfil de política de largura de banda apropriado para dois sites que têm um link cruzado direto.</span><span class="sxs-lookup"><span data-stu-id="52883-116">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="52883-117">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="52883-117">For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="52883-118">Repita a etapa 2 conforme necessário para criar políticas entre sites de rede para todos os pares de sites de rede que têm um link cruzado direto.</span><span class="sxs-lookup"><span data-stu-id="52883-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

