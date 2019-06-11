---
title: 'Lync Server 2013: Criando ou modificando regiões de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3ca5d44fd2278ffee8a3e9dd4494575cc64c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="1c702-102">Criando ou modificando regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c702-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c702-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1c702-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1c702-104">Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="1c702-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="1c702-105">Todas as regiões de rede devem estar associadas a um site central.</span><span class="sxs-lookup"><span data-stu-id="1c702-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="1c702-106">O site central é o site do Data Center no qual o serviço de política de largura de banda do controle de admissão de chamadas (CAC) está em execução.</span><span class="sxs-lookup"><span data-stu-id="1c702-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="1c702-107">Você pode usar o painel de controle do Lync Server para configurar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="1c702-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="1c702-108">As regiões de rede incluem configurações que determinam se caminhos alternativos pela Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="1c702-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="1c702-109">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="1c702-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="1c702-110">Use este tópico para criar e modificar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="1c702-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="1c702-111">Para obter detalhes sobre como excluir regiões de rede existentes, consulte [excluindo regiões de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="1c702-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="1c702-112">Para criar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="1c702-112">To create a network region</span></span>

1.  <span data-ttu-id="1c702-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1c702-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c702-114">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c702-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1c702-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1c702-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1c702-116">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="1c702-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="1c702-117">Na página **região** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="1c702-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="1c702-118">Na página **nova região** , digite um valor no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="1c702-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="1c702-119">Esse valor deve ser exclusivo na implantação do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c702-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="1c702-120">Na lista suspensa **site central** , selecione o site central para esta região de rede.</span><span class="sxs-lookup"><span data-stu-id="1c702-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="1c702-121">A caixa de seleção **habilitar caminho alternativo de áudio** está marcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="1c702-121">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="1c702-122">Esse campo determina se as chamadas de áudio serão roteadas por meio de um caminho alternativo se a largura de banda adequada não existir no caminho principal.</span><span class="sxs-lookup"><span data-stu-id="1c702-122">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="1c702-123">Desmarque essa caixa de seleção apenas se precisar desativar o Offload para a Internet.</span><span class="sxs-lookup"><span data-stu-id="1c702-123">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="1c702-124">Se qualquer uma de suas chamadas for chamada pela Internet, essa caixa de seleção deve ser marcada, independentemente das configurações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="1c702-124">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="1c702-125">A caixa de seleção **habilitar caminho alternativo de vídeo** está marcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="1c702-125">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="1c702-126">Esse campo determina se as chamadas com vídeo serão roteadas por meio de um caminho alternativo se a largura de banda adequada não existir no caminho principal.</span><span class="sxs-lookup"><span data-stu-id="1c702-126">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="1c702-127">Desmarque essa caixa de seleção apenas se precisar desativar o Offload para a Internet.</span><span class="sxs-lookup"><span data-stu-id="1c702-127">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="1c702-128">Se qualquer uma de suas chamadas for chamada pela Internet, essa caixa de seleção deve ser marcada, independentemente das configurações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="1c702-128">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="1c702-129">Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre essa região que não pode ser expressa apenas pelo nome.</span><span class="sxs-lookup"><span data-stu-id="1c702-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="1c702-130">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1c702-130">Click **Commit**.</span></span>

<span data-ttu-id="1c702-131">A tabela de **sites associados** não é usada para criar uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="1c702-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="1c702-132">Você associa um site com uma região quando cria ou modifica o site.</span><span class="sxs-lookup"><span data-stu-id="1c702-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="1c702-133">Para obter detalhes, consulte [criando ou modificando sites de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="1c702-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="1c702-134">Para modificar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="1c702-134">To modify a network region</span></span>

1.  <span data-ttu-id="1c702-135">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1c702-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c702-136">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c702-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1c702-137">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1c702-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1c702-138">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="1c702-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="1c702-139">Na página **região** , clique na região que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="1c702-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="1c702-140">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="1c702-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1c702-141">Na página **Editar região** , você pode modificar as configurações para habilitar e desabilitar caminhos alternativos de áudio e vídeo e alterar a descrição (para obter detalhes, consulte a seção "para criar uma região de rede" anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="1c702-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="1c702-142">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1c702-142">Click **Commit**.</span></span>

<span data-ttu-id="1c702-143">Não é possível modificar os **sites associados** nesta página.</span><span class="sxs-lookup"><span data-stu-id="1c702-143">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="1c702-144">A lista de sites associados é fornecida para referência para que você saiba quais sites serão afetados quando você modificar as configurações de região.</span><span class="sxs-lookup"><span data-stu-id="1c702-144">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c702-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="1c702-145">See Also</span></span>


[<span data-ttu-id="1c702-146">Excluindo regiões de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c702-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="1c702-147">Configurar regiões de rede para o CAC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c702-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="1c702-148">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="1c702-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="1c702-149">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="1c702-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="1c702-150">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="1c702-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="1c702-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="1c702-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

