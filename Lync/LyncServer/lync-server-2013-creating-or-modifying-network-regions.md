---
title: 'Lync Server 2013: criar ou modificar regiões de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04f85e4546d8cfa3154c2fc5a87676ff0377795b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="a6f3b-102">Criar ou modificar regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f3b-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6f3b-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a6f3b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a6f3b-104">Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a6f3b-105">Cada região de rede deve ser associada com um local central.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="a6f3b-106">O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="a6f3b-107">Você pode usar o painel de controle do Lync Server para configurar as regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="a6f3b-108">As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="a6f3b-109">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="a6f3b-110">Use este tópico para criar e modificar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="a6f3b-111">Para obter detalhes sobre como excluir regiões de rede existentes, consulte [excluindo regiões de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="a6f3b-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="a6f3b-112">Para criar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="a6f3b-112">To create a network region</span></span>

1.  <span data-ttu-id="a6f3b-113">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6f3b-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a6f3b-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a6f3b-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a6f3b-116">Na barra de navegação à direita, clique em **Configuração de Rede** e clique em **Região**.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="a6f3b-117">Na página **Região**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="a6f3b-118">Na página **Nova Região**, digite um valor no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="a6f3b-119">Esse valor deve ser exclusivo na sua implantação do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="a6f3b-120">Na lista suspensa **Site central**, selecione o site central para essa região de rede.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="a6f3b-p104">A caixa de seleção **Habilitar caminho alternativo do áudio** está marcada por padrão. Esse campo determina se as chamadas de áudio serão roteadas por um caminho alternativo, caso a largura de banda adequada não exista no caminho primário. Desmarque essa caixa de seleção somente se precisar desativar o descarregamento para a Internet. Se qualquer uma de suas chamadas for uma chamada pela Internet, essa caixa de seleção deverá ser marcada, independente das configurações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-p104">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="a6f3b-p105">A caixa de seleção **Habilitar caminho alternativo do vídeo** está marcada por padrão. Esse campo determina se as chamadas de vídeo serão roteadas por um caminho alternativo, caso a largura de banda adequada não exista no caminho primário. Desmarque essa caixa de seleção somente se precisar desativar o descarregamento para a Internet. Se qualquer uma de suas chamadas for uma chamada pela Internet, essa caixa de seleção deverá ser marcada, independente das configurações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-p105">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="a6f3b-129">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre essa região que não podem ser expressas somente pelo nome.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="a6f3b-130">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-130">Click **Commit**.</span></span>

<span data-ttu-id="a6f3b-131">A tabela **Sites associados** não é usada para criar uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="a6f3b-132">Você associa um site a uma região quando cria ou modifica o site.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="a6f3b-133">Para obter detalhes, consulte [criando ou modificando sites de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="a6f3b-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="a6f3b-134">Para modificar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="a6f3b-134">To modify a network region</span></span>

1.  <span data-ttu-id="a6f3b-135">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6f3b-136">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a6f3b-137">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a6f3b-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a6f3b-138">Na barra de navegação à direita, clique em **Configuração de Rede** e clique em **Região**.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="a6f3b-139">Na página **Região**, clique na região que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="a6f3b-140">No menu **Editar**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a6f3b-141">Na página **Editar Região**, é possível modificar as configurações para habilitar e desabilitar caminhos alternativos de áudio e vídeo e alterar a descrição (para obter detalhes, consulte a seção "Para criar uma região de rede" acima neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="a6f3b-142">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-142">Click **Commit**.</span></span>

<span data-ttu-id="a6f3b-p108">Não é possível modificar os **Sites associados** nesta página. A lista de sites associados é fornecida para referência de modo que você fique ciente de quais sites serão afetados quando você modificar as configurações de região.</span><span class="sxs-lookup"><span data-stu-id="a6f3b-p108">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6f3b-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="a6f3b-145">See Also</span></span>


[<span data-ttu-id="a6f3b-146">Excluindo regiões de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f3b-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="a6f3b-147">Configurar regiões de rede para CAC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f3b-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="a6f3b-148">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a6f3b-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="a6f3b-149">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a6f3b-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="a6f3b-150">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a6f3b-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="a6f3b-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a6f3b-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

