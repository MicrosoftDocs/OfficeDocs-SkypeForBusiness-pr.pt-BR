---
title: 'Lync Server 2013: excluindo sub-redes de rede'
description: 'Lync Server 2013: excluindo sub-redes de rede.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6635ec99b68c4ceb10d1cda343fef35c951bf152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557877"
---
# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="b3ba1-103">Excluindo sub-redes de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3ba1-103">Deleting network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3ba1-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b3ba1-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b3ba1-105">É possível usar o seguinte procedimento para excluir uma subrede.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-105">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="b3ba1-106">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="b3ba1-107">Para obter detalhes sobre como criar ou modificar sub-redes de rede, consulte [create or Modify Network sub-redes in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="b3ba1-107">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="b3ba1-108">Na maioria das implantações do Microsoft Lync Server 2013 onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="b3ba1-109">Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="b3ba1-110">A partir daí, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Import-CSV**do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="b3ba1-111">Usando estes cmdlets em conjunto, é possível ler nas configurações de subrede de um arquivo de valores separados por vírgula (.csv) e criar várias subredes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="b3ba1-112">Para ver exemplos de como criar subredes de um arquivo .csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="b3ba1-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="b3ba1-113">Para excluir uma subrede</span><span class="sxs-lookup"><span data-stu-id="b3ba1-113">To delete a network subnet</span></span>

1.  <span data-ttu-id="b3ba1-114">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b3ba1-115">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b3ba1-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b3ba1-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b3ba1-117">Na barra de navegação à esquerda, clique em **Configuração da rede** e clique em **Sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="b3ba1-118">Na página **Subrede**, clique na subrede que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-118">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3ba1-p104">Você pode excluir mais de uma subrede simultaneamente. Para isso, pressione a tecla CTRL e selecione várias subredes mantendo a tecla CTRL pressionada. Em alternativa, para selecionar todas as subredes, clique em <STRONG>Selecionar todas</STRONG> no menu <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-p104">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="b3ba1-122">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-122">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="b3ba1-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3ba1-123">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3ba1-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="b3ba1-124">See Also</span></span>


[<span data-ttu-id="b3ba1-125">Criar ou modificar sub-redes de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3ba1-125">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

