---
title: 'Lync Server 2013: excluindo regiões de rede existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664eea747c9cea637b86377760f30c59bb21e7e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="128c8-102">Excluindo regiões de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="128c8-102">Deleting existing network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="128c8-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="128c8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="128c8-104">Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="128c8-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="128c8-105">Cada região de rede deve ser associada com um local central.</span><span class="sxs-lookup"><span data-stu-id="128c8-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="128c8-106">O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando.</span><span class="sxs-lookup"><span data-stu-id="128c8-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="128c8-107">Você pode usar o painel de controle do Lync Server para configurar as regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="128c8-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="128c8-108">As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="128c8-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="128c8-109">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="128c8-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="128c8-110">Use este tópico para excluir regiões de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="128c8-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="128c8-111">Para obter detalhes sobre como criar ou modificar regiões de rede existentes, consulte [criar ou modificar regiões de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="128c8-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="128c8-112">Para excluir uma região de rede</span><span class="sxs-lookup"><span data-stu-id="128c8-112">To delete a network region</span></span>

1.  <span data-ttu-id="128c8-113">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="128c8-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="128c8-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="128c8-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="128c8-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="128c8-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="128c8-116">Na barra de navegação à direita, clique em **Configuração de Rede** e clique em **Região**.</span><span class="sxs-lookup"><span data-stu-id="128c8-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="128c8-117">Na página **Região**, clique na região que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="128c8-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="128c8-p103">É possível excluir mais de uma região por vez. Para fazer isso, pressione CTRL e selecione várias regiões enquanto mantém pressionada a tecla CTRL. Ou, para selecionar todas as regiões, clique em <STRONG>Selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="128c8-p103">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="128c8-121">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="128c8-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="128c8-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="128c8-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="128c8-p104">Uma região de rede não pode ser removida se estiver associada a um site de rede. Se você quiser tentar remover uma região associada a um site, receberá uma mensagem de erro. Para ver se um região está associada a algum site, selecione a região e clique em <STRONG>Mostrar detalhes</STRONG> no menu <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="128c8-p104">A network region cannot be removed if it is associated with a network site. If you attempt to remove a region associated with a site you will receive an error message. To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="128c8-126">Confira Também</span><span class="sxs-lookup"><span data-stu-id="128c8-126">See Also</span></span>


[<span data-ttu-id="128c8-127">Criar ou modificar regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="128c8-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

