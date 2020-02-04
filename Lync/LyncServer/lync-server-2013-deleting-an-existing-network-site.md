---
title: 'Lync Server 2013: excluindo um site de rede existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c8e3828bccb84fcddb4404dd7228173c63ab8a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="28be7-102">Excluindo um site de rede existente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28be7-102">Deleting an existing network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28be7-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="28be7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="28be7-104">Sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou implantação 9-1-1 aprimorada.</span><span class="sxs-lookup"><span data-stu-id="28be7-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="28be7-105">Você pode usar o painel de controle do Lync Server 2013 para configurar sites e associá-los a regiões.</span><span class="sxs-lookup"><span data-stu-id="28be7-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="28be7-106">Por exemplo, uma região de rede para a América do Norte pode estar associada a sites de redes como Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="28be7-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="28be7-107">Um site de rede do CAC deve ser criado para cada site dentro de uma organização, mesmo que esse site não tenha limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="28be7-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="28be7-108">No painel de controle do Lync Server, você pode criar, modificar e excluir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="28be7-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="28be7-109">Use o procedimento a seguir para excluir um site de rede existente.</span><span class="sxs-lookup"><span data-stu-id="28be7-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="28be7-110">Para obter detalhes sobre como criar ou modificar sites de rede, consulte [criando ou modificando sites de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="28be7-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="28be7-111">Para excluir um site de rede</span><span class="sxs-lookup"><span data-stu-id="28be7-111">To delete a network site</span></span>

1.  <span data-ttu-id="28be7-112">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="28be7-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="28be7-113">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28be7-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="28be7-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="28be7-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="28be7-115">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **site**.</span><span class="sxs-lookup"><span data-stu-id="28be7-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="28be7-116">Na página do **site** , clique no site que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="28be7-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28be7-117">Você pode excluir mais de um site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="28be7-117">You can delete more than one site at a time.</span></span> <span data-ttu-id="28be7-118">Para fazer isso, pressione CTRL e selecione vários sites enquanto mantém a tecla CTRL pressionada.</span><span class="sxs-lookup"><span data-stu-id="28be7-118">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="28be7-119">Ou, para selecionar todos os sites, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="28be7-119">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="28be7-120">No menu **Editar** , clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="28be7-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="28be7-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="28be7-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="28be7-122">Você não pode remover um site de rede se ele estiver associado a uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="28be7-122">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="28be7-123">Se você tentar remover um site associado a uma sub-rede, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="28be7-123">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="28be7-124">Para ver se um site está associado a qualquer sub-rede, clique no site e, em seguida, clique em <STRONG>Mostrar detalhes</STRONG> no menu <STRONG>Editar</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="28be7-124">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

