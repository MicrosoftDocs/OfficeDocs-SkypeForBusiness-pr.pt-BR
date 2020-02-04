---
title: 'Lync Server 2013: excluindo sub-redes de rede'
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
ms.openlocfilehash: 0c87ca1cfd91344d8f8cbb0b320c70def47bf5ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="0c041-102">Excluindo sub-redes de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c041-102">Deleting network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c041-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0c041-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0c041-104">Você pode usar o procedimento a seguir para excluir uma sub-rede.</span><span class="sxs-lookup"><span data-stu-id="0c041-104">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="0c041-105">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="0c041-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="0c041-106">Para obter detalhes sobre como criar ou modificar sub-redes de rede, consulte [criar ou modificar sub-redes de rede no Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="0c041-106">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="0c041-107">Na maioria das implantações do Microsoft Lync Server 2013 em que o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="0c041-107">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="0c041-108">Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0c041-108">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="0c041-109">Em seguida, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Import-CSV**do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c041-109">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="0c041-110">Ao usar esses cmdlets juntos, você pode ler as configurações de sub-rede a partir de um arquivo de valores separados por vírgulas (. csv) e criar várias sub-redes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="0c041-110">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="0c041-111">Para obter exemplos de como criar sub-redes a partir de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="0c041-111">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="0c041-112">Para excluir uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="0c041-112">To delete a network subnet</span></span>

1.  <span data-ttu-id="0c041-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="0c041-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0c041-114">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0c041-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0c041-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0c041-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0c041-116">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="0c041-116">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="0c041-117">Na página **sub-rede** , clique na sub-rede que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="0c041-117">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0c041-118">Você pode excluir mais de uma sub-rede de cada vez.</span><span class="sxs-lookup"><span data-stu-id="0c041-118">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="0c041-119">Para fazer isso, pressione CTRL e selecione várias sub-redes enquanto mantém a tecla CTRL pressionada.</span><span class="sxs-lookup"><span data-stu-id="0c041-119">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="0c041-120">Ou, para selecionar todas as sub-redes, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="0c041-120">Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="0c041-121">No menu **Editar** , clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="0c041-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="0c041-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c041-122">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c041-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="0c041-123">See Also</span></span>


[<span data-ttu-id="0c041-124">Criar ou modificar sub-redes de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c041-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

