---
title: 'Lync Server 2013: Adicionar sites de filial a sua topologia'
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
ms.openlocfilehash: 2df1871956b33b3781128e2b62af13bdd875d10b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="cf789-102">Adicionar sites de filial a sua topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf789-102">Add branch sites to your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf789-103">_**Tópico da última modificação:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="cf789-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="cf789-104">Os sites de filiais representam filiais físicas conectadas a seus escritórios principais por meio de um link de WAN.</span><span class="sxs-lookup"><span data-stu-id="cf789-104">Branch sites represent physical branch offices that are connected to your main offices over a WAN link.</span></span> <span data-ttu-id="cf789-105">Para adicionar um site de ramificação à sua topologia do Lync, execute este procedimento no site central.</span><span class="sxs-lookup"><span data-stu-id="cf789-105">To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="cf789-106">Para adicionar sites de filiais à sua topologia</span><span class="sxs-lookup"><span data-stu-id="cf789-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="cf789-107">Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server**e, em seguida, clique em **Construtor de topologia do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cf789-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="cf789-108">Na árvore de console, expanda o site central, clique com o botão direito do mouse em **sites de ramificação**e clique em **novo site de filial**.</span><span class="sxs-lookup"><span data-stu-id="cf789-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="cf789-109">Na caixa de diálogo **definir novo site de filial** , clique em **nome**e digite o nome do site de filial.</span><span class="sxs-lookup"><span data-stu-id="cf789-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="cf789-110">Adicionais Clique em **Descrição**e digite uma descrição significativa para o site da filial.</span><span class="sxs-lookup"><span data-stu-id="cf789-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="cf789-111">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="cf789-111">Click **Next**.</span></span>

6.  <span data-ttu-id="cf789-112">Adicionais Na caixa de diálogo próximo **definir novo site de filiais** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cf789-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="cf789-113">Clique em **cidade**e digite o nome da cidade na qual o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="cf789-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="cf789-114">Clique em **estado/região**e, em seguida, digite o nome do Estado ou da região em que o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="cf789-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="cf789-115">Clique em **código do país**e, em seguida, digite o código de chamada de dois dígitos para o país/região no qual o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="cf789-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="cf789-116">Clique em **Avançar**e, em seguida, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cf789-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="cf789-117">Se você estiver usando um aplicativo ou um aplicativo de ramificação sobreviventes neste site, certifique-se de que a caixa de seleção **abrir o assistente para uso futuro quando este assistente for fechado** estiver marcada, clique em **concluir**e siga as instruções no assistente que é aberta.</span><span class="sxs-lookup"><span data-stu-id="cf789-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="cf789-118">Para saber mais sobre os itens do assistente, confira [definir um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="cf789-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="cf789-119">Se você não estiver usando um aplicativo ou aplicativo de ramificação sobreviventes neste site, desmarque a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="cf789-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="cf789-120">Repita as etapas anteriores para cada site de ramificação que você deseja adicionar à topologia.</span><span class="sxs-lookup"><span data-stu-id="cf789-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="cf789-121">**Próxima etapa:**</span><span class="sxs-lookup"><span data-stu-id="cf789-121">**Next step:**</span></span>

<span data-ttu-id="cf789-122">Para aplicativos ou aparelhos de ramificação sobreviventes: [definir um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="cf789-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="cf789-123">Para conectividade PSTN não resiliente: [defina um gateway PSTN para um site de filial no Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)ou [Configure um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="cf789-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

