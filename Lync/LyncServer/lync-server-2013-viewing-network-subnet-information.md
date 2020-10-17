---
title: 'Lync Server 2013: exibindo informações de sub-rede de rede'
description: 'Lync Server 2013: exibindo informações de sub-rede de rede.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 313135c43318817391d54f2fa3e73dd318f7a11f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546147"
---
# <a name="viewing-network-subnet-information-in-lync-server-2013"></a><span data-ttu-id="8c625-103">Exibindo informações de sub-rede de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c625-103">Viewing network subnet information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c625-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8c625-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8c625-105">Você pode utilizar o seguinte procedimento para visualizar uma sub-rede da rede.</span><span class="sxs-lookup"><span data-stu-id="8c625-105">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="8c625-106">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="8c625-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="8c625-107">Para obter detalhes sobre como criar ou modificar sub-redes de rede, consulte [create or Modify Network sub-redes in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="8c625-107">For details about creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<div>

## <a name="to-view-a-network-subnet"></a><span data-ttu-id="8c625-108">Para visualizar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="8c625-108">To view a network subnet</span></span>

1.  <span data-ttu-id="8c625-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8c625-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8c625-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c625-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8c625-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8c625-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8c625-112">Na barra de navegação à esquerda, clique em **Configuração de rede** e, então, em **Sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="8c625-112">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="8c625-113">Na página de **Sub-rede**, clique na sub-rede que deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="8c625-113">On the **Subnet** page, click the subnet that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c625-114">Você só pode visualizar uma sub-rede por vez.</span><span class="sxs-lookup"><span data-stu-id="8c625-114">You can only view one subnet at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="8c625-115">No menu **Editar**, clique em **Exibir detalhes…**.</span><span class="sxs-lookup"><span data-stu-id="8c625-115">On the **Edit** menu, click **Show details…**.</span></span>

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8c625-116">Exibindo informações de configuração de sub-rede de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c625-116">Viewing Network Subnet Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8c625-117">As informações de sub-rede de rede podem ser exibidas usando o Windows PowerShell e o cmdlet Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="8c625-117">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="8c625-118">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c625-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8c625-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="8c625-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-subnet-information"></a><span data-ttu-id="8c625-120">Para exibir informações de sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="8c625-120">To view network subnet information</span></span>

  - <span data-ttu-id="8c625-121">Para exibir informações sobre todas as suas sub-redes de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="8c625-121">To view information about all your network subnets, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="8c625-122">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="8c625-122">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

<span data-ttu-id="8c625-123">Para mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="8c625-123">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c625-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="8c625-124">See Also</span></span>


[<span data-ttu-id="8c625-125">Criar ou modificar sub-redes de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c625-125">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
[<span data-ttu-id="8c625-126">Excluindo sub-redes de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c625-126">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

