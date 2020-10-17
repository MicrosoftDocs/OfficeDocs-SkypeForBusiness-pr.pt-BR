---
title: 'Lync Server 2013: adicionar sites de filial à sua topologia'
description: 'Lync Server 2013: adicionar sites de filial à sua topologia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c7a12373c6a60a2902ee451d39c99f756e2b2f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544567"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="c181e-103">Adicionar sites de filial à sua topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c181e-103">Add branch sites to your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c181e-104">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c181e-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c181e-p101">Os sites de filial representam os escritórios de filial físicos que estão conectados aos escritórios principais por um link WAN link. Para adicionar um site de filial à sua topologia do Lync, execute este procedimento no site central.</span><span class="sxs-lookup"><span data-stu-id="c181e-p101">Branch sites represent physical branch offices that are connected to your main offices over a WAN link. To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="c181e-107">Para adicionar sites de filiais à sua topologia</span><span class="sxs-lookup"><span data-stu-id="c181e-107">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="c181e-108">Clique em **Iniciar**, **Todos os programas**, **Microsoft Lync Server** e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c181e-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c181e-109">Na árvore do console, expanda o site central, clique com o botão direito do mouse em **Sites de filia** e clique em **Novo site de filial**.</span><span class="sxs-lookup"><span data-stu-id="c181e-109">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="c181e-110">Na caixa de diálogo **Definir Novo Site de Filial**, clique em **Nome** e digite o nome do site de filial.</span><span class="sxs-lookup"><span data-stu-id="c181e-110">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="c181e-111">(Opcional) Clique em **Descrição** e digite uma descrição significativa para o site de filial.</span><span class="sxs-lookup"><span data-stu-id="c181e-111">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="c181e-112">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c181e-112">Click **Next**.</span></span>

6.  <span data-ttu-id="c181e-113">(Opcional) Na próxima caixa de diálogo **Definir Novo Site de Filial**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c181e-113">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="c181e-114">Clique em **Cidade** e digite o nome da cidade na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="c181e-114">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="c181e-115">Clique em **Estado/Região** e digite o nome do estado ou região na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="c181e-115">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="c181e-116">Clique em **Código do País** e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="c181e-116">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="c181e-117">Clique em **Avançar** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c181e-117">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="c181e-118">Se você estiver usando um aparelho ou servidor de filial persistente neste site, certifique-se de que a caixa de seleção **abrir o novo assistente persistente quando este assistente for fechado** estiver marcada, clique em **concluir**e siga as instruções do assistente que é aberto.</span><span class="sxs-lookup"><span data-stu-id="c181e-118">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="c181e-119">Para obter informações sobre itens de assistente, consulte [definir um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="c181e-119">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="c181e-120">Se você não estiver usando um Aparelho de Filial Persistente ou Servidor nesse site, desmarque a caixa de seleção **Abrir o Novo Assistente Persistente quando este assistente fechar** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c181e-120">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="c181e-121">Repita as etapas anteriores para cada site de filial que deseja adicionar à topologia.</span><span class="sxs-lookup"><span data-stu-id="c181e-121">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="c181e-122">**Próxima etapa:**</span><span class="sxs-lookup"><span data-stu-id="c181e-122">**Next step:**</span></span>

<span data-ttu-id="c181e-123">Para servidores ou aplicativos de filial persistentes: [definir um servidor ou aparelho de filial persistente no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="c181e-123">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="c181e-124">Para conectividade PSTN não resiliente: [definir um gateway PSTN para um site de filial no Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)ou [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="c181e-124">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

