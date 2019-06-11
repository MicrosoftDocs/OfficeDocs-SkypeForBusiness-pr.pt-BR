---
title: Adicionar Aparelho de Filial Persistente do Lync Server 2013 a sua topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83ae19b3683b725db64b2f598eb6fc3d182bac17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="242aa-102">Adicionar Aparelho de Filial Persistente do Lync Server 2013 a sua topologia</span><span class="sxs-lookup"><span data-stu-id="242aa-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="242aa-103">_**Tópico da última modificação:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="242aa-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="242aa-104">Microsoft Lync Server 2013 não é possível associar aparelhos de ramificação sobreviventes (SBA) a um pool de front-end do Microsoft Lync Server 2010 como um registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="242aa-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="242aa-105">O SBA deve estar associado a um pool de front-ends do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="242aa-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="242aa-106">Estas etapas pressupõem um Microsoft Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="242aa-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="242aa-107">Execute este procedimento no site central.</span><span class="sxs-lookup"><span data-stu-id="242aa-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="242aa-108">Para adicionar sites de filiais com o Microsoft Lync Server 2013 SBA à sua topologia</span><span class="sxs-lookup"><span data-stu-id="242aa-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="242aa-109">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="242aa-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="242aa-110">Na árvore de console, expanda o site central, expanda **sites**de ramificação e clique em **novo site de filial**.</span><span class="sxs-lookup"><span data-stu-id="242aa-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="242aa-111">Na caixa de diálogo **definir novo site de filial** , clique em **nome**e digite um nome para o novo site de filial.</span><span class="sxs-lookup"><span data-stu-id="242aa-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="242aa-112">Adicionais Clique em **Descrição**e digite uma descrição significativa para o site da filial.</span><span class="sxs-lookup"><span data-stu-id="242aa-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="242aa-113">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="242aa-113">Click **Next**.</span></span>

6.  <span data-ttu-id="242aa-114">Adicionais Na caixa de diálogo próximo **definir novo site** de filiais, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="242aa-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="242aa-115">Clique em **cidade**e digite o nome da cidade na qual o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="242aa-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="242aa-116">Clique em **estado/região**e, em seguida, digite o nome do Estado ou da região em que o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="242aa-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="242aa-117">Clique em **código do país**e, em seguida, digite o código de chamada de dois dígitos para o país/região no qual o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="242aa-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="242aa-118">Clique em **Avançar**e, em seguida, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="242aa-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="242aa-119">Se você estiver usando um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes neste site, certifique-se de que a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** esteja marcada.</span><span class="sxs-lookup"><span data-stu-id="242aa-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="242aa-120">Se você não estiver usando um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes neste site, desmarque a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** .</span><span class="sxs-lookup"><span data-stu-id="242aa-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="242aa-121">Clique em **concluir**e siga as instruções no assistente que é aberto.</span><span class="sxs-lookup"><span data-stu-id="242aa-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="242aa-122">Para saber mais sobre os itens do assistente, confira [definir um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="242aa-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="242aa-123">Repita as etapas anteriores para cada site de ramificação que você deseja adicionar à topologia.</span><span class="sxs-lookup"><span data-stu-id="242aa-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="242aa-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="242aa-124">See Also</span></span>


[<span data-ttu-id="242aa-125">Definir um Servidor ou Aparelho de Filial Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="242aa-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="242aa-126">Definir um gateway de PSTN para um site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="242aa-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="242aa-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="242aa-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="242aa-128">Configurar um tronco sem bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="242aa-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

