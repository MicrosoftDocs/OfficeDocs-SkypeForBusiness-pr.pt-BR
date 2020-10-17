---
title: 'Lync Server 2013: excluindo links de região de rede'
description: 'Lync Server 2013: excluindo links de região de rede.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a17c1ec64460e0f7cb447597f94aadd7fd2a9ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545327"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="c08ed-103">Excluindo links de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c08ed-103">Deleting network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c08ed-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c08ed-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c08ed-105">Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c08ed-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="c08ed-106">Regiões dentro de uma rede são vinculadas por conectividade de WAN física.</span><span class="sxs-lookup"><span data-stu-id="c08ed-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="c08ed-107">Você pode usar o painel de controle do Lync Server para excluir um link existente entre duas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="c08ed-107">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="c08ed-108">Para obter detalhes sobre como criar ou modificar um link de região de rede, confira [Configurando links de região de rede no Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="c08ed-108">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="c08ed-109">Para excluir um link de região de rede</span><span class="sxs-lookup"><span data-stu-id="c08ed-109">To delete a network region link</span></span>

1.  <span data-ttu-id="c08ed-110">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c08ed-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c08ed-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c08ed-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c08ed-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c08ed-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c08ed-113">Na barra de navegação esquerda, clique em **Configuração da rede** e em **Link da região**.</span><span class="sxs-lookup"><span data-stu-id="c08ed-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="c08ed-114">Na página **link de região** , clique no link de região que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="c08ed-114">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c08ed-115">Você pode excluir mais de um link de região por vez.</span><span class="sxs-lookup"><span data-stu-id="c08ed-115">You can delete more than one region link at a time.</span></span> <span data-ttu-id="c08ed-116">Para fazer isso, pressione CTRL e selecione vários links de região mantendo pressionada a tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="c08ed-116">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="c08ed-117">Ou, para selecionar todos os links de região, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c08ed-117">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="c08ed-118">No menu **Editar** , selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="c08ed-118">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="c08ed-119">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c08ed-119">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c08ed-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="c08ed-120">See Also</span></span>


[<span data-ttu-id="c08ed-121">Configurando links de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c08ed-121">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

