---
title: Adicionar site de filial de dispositivo de filial persistente do Lync Server 2013 à sua topologia
description: Adicione o site de filial do aplicativo de filial persistente do Lync Server 2013 à sua topologia.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b50c03dd53c7637fcf0914db290b3e452b64b83
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572027"
---
# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="ccb19-103">Adicionar site de filial de dispositivo de filial persistente do Lync Server 2013 à sua topologia</span><span class="sxs-lookup"><span data-stu-id="ccb19-103">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccb19-104">_**Última modificação do tópico:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="ccb19-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="ccb19-105">Os aparelhos de ramificação persistentes do Microsoft Lync Server 2013 (SBA) não podem ser associados a um pool de front-ends do Microsoft Lync Server 2010 como um registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="ccb19-105">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="ccb19-106">O SBA deve ser associado a um pool de front-ends do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ccb19-106">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="ccb19-107">Estas etapas pressupõem um Microsoft Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="ccb19-107">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="ccb19-108">Execute este procedimento no local central.</span><span class="sxs-lookup"><span data-stu-id="ccb19-108">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="ccb19-109">Para adicionar sites de filiais com o Microsoft Lync Server 2013 SBA à sua topologia</span><span class="sxs-lookup"><span data-stu-id="ccb19-109">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="ccb19-110">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ccb19-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ccb19-111">Na árvore do console, expanda o site central, expanda **sites de filial**e clique em **novo site de filial**.</span><span class="sxs-lookup"><span data-stu-id="ccb19-111">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="ccb19-112">Na caixa de diálogo **definir novo site de filial** , clique em **nome**e digite um nome para o novo site de filial.</span><span class="sxs-lookup"><span data-stu-id="ccb19-112">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="ccb19-113">(Opcional) Clique em **Descrição** e digite uma descrição significativa para o site de filial.</span><span class="sxs-lookup"><span data-stu-id="ccb19-113">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="ccb19-114">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ccb19-114">Click **Next**.</span></span>

6.  <span data-ttu-id="ccb19-115">(Opcional) Na próxima caixa de diálogo **Definir Novo Site de Filial**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="ccb19-115">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="ccb19-116">Clique em **Cidade** e digite o nome da cidade na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="ccb19-116">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="ccb19-117">Clique em **Estado/Região** e digite o nome do estado ou região na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="ccb19-117">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="ccb19-118">Clique em **Código do País** e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="ccb19-118">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="ccb19-119">Clique em **Avançar** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="ccb19-119">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="ccb19-120">Se você estiver usando um aparelho de filial persistente ou servidor de filial persistente neste site, certifique-se de que a caixa de seleção **abrir o assistente de novo persistente quando este assistente for fechado** esteja marcada.</span><span class="sxs-lookup"><span data-stu-id="ccb19-120">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="ccb19-121">Se você não estiver usando um aparelho de filial persistente ou servidor de filial persistente neste site, desmarque a caixa de seleção **abrir o novo assistente persistente quando este assistente fechar** .</span><span class="sxs-lookup"><span data-stu-id="ccb19-121">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="ccb19-122">Clique em **concluir**e siga as instruções do assistente que são exibidas.</span><span class="sxs-lookup"><span data-stu-id="ccb19-122">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="ccb19-123">Para obter informações sobre itens de assistente, consulte [definir um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="ccb19-123">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="ccb19-124">Repita as etapas anteriores para cada site de filial que deseja adicionar à topologia.</span><span class="sxs-lookup"><span data-stu-id="ccb19-124">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ccb19-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="ccb19-125">See Also</span></span>


[<span data-ttu-id="ccb19-126">Definir um servidor ou aparelho de filial persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccb19-126">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="ccb19-127">Definir um gateway PSTN para um site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccb19-127">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="ccb19-128">Configurar um tronco com bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccb19-128">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="ccb19-129">Configurar um tronco sem bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccb19-129">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

