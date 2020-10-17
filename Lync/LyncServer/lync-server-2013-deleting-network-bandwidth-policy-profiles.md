---
title: 'Lync Server 2013: excluir perfis de política de largura de banda de rede'
description: 'Lync Server 2013: excluindo perfis de política de largura de banda de rede.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f460d9620158d1857dae41e0033f6d36078868
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552657"
---
# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="49a80-103">Excluindo perfis de política de largura de banda de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-103">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49a80-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="49a80-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="49a80-105">Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades.</span><span class="sxs-lookup"><span data-stu-id="49a80-105">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="49a80-106">No Microsoft Lync Server 2013, somente as modalidades de áudio e vídeo podem ser atribuídas a limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="49a80-106">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="49a80-107">Você pode configurar os limites gerais de banda e os limites de sessão.</span><span class="sxs-lookup"><span data-stu-id="49a80-107">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="49a80-108">Você pode usar o painel de controle do Lync Server para criar, modificar ou excluir um perfil de contêiner para essas políticas.</span><span class="sxs-lookup"><span data-stu-id="49a80-108">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="49a80-109">Use os seguintes procedimentos para excluir um perfil de política de largura de banda de rede.</span><span class="sxs-lookup"><span data-stu-id="49a80-109">Use the following procedures to delete a network bandwidth policy profiles.</span></span> <span data-ttu-id="49a80-110">Para obter detalhes sobre como criar ou modificar um perfil de política de largura de banda de rede, consulte [criando ou modificando perfis de política de largura de banda no Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="49a80-110">For details on creating or modifying a network bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="49a80-111">Para excluir um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="49a80-111">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="49a80-112">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="49a80-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49a80-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49a80-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="49a80-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="49a80-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="49a80-115">Na barra de navegação à esquerda, clique em **Configuração de rede** e, em seguida, clique em **Política de largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="49a80-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="49a80-116">Na página **Política de largura de banda**, clique no perfil de política de largura de banda que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="49a80-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="49a80-p103">Você pode excluir mais de um perfil por vez. Para isso, pressione CTRL e selecione vários perfis mantendo a tecla CTRL pressionada. Ou, para selecionar perfis, clique em <STRONG>Selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="49a80-p103">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="49a80-120">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="49a80-120">On the **Edit** menu, click **Delete**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="49a80-121">Você não pode excluir um perfil de política de largura de banda que esteja associado a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="49a80-121">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="49a80-122">É preciso primeiro remover a associação com o site antes de poder excluir o perfil.</span><span class="sxs-lookup"><span data-stu-id="49a80-122">You must first remove the association with the network site before you can delete the profile.</span></span> <span data-ttu-id="49a80-123">Para obter detalhes sobre como modificar o site de rede, consulte <A href="lync-server-2013-creating-or-modifying-network-sites.md">criando ou modificando sites de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="49a80-123">For details about how to modify the network site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49a80-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="49a80-124">See Also</span></span>


[<span data-ttu-id="49a80-125">Criando ou modificando perfis de política de largura de banda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-125">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="49a80-126">Exibindo informações de perfil da política de largura de banda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-126">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[<span data-ttu-id="49a80-127">Configurar o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-127">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="49a80-128">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="49a80-128">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

