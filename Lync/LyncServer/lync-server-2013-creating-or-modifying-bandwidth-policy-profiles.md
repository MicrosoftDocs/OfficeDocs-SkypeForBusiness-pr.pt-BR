---
title: 'Lync Server 2013: Criando ou modificando perfis de política de largura de banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06019464d6d37c601c9077d36c81976d43b6e37c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="c6160-102">Criando ou modificando perfis de política de largura de banda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6160-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6160-103">_**Tópico da última modificação:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="c6160-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="c6160-104">Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir limitações de largura de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="c6160-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="c6160-105">No Microsoft Lync Server 2013, somente as modalidades de áudio e vídeo podem ter limitações de largura de banda atribuídas.</span><span class="sxs-lookup"><span data-stu-id="c6160-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="c6160-106">Você pode definir limitações gerais de largura de banda e limitações de sessão.</span><span class="sxs-lookup"><span data-stu-id="c6160-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="c6160-107">Você pode usar o painel de controle do Lync Server para criar, modificar ou excluir um perfil de contêiner para essas políticas.</span><span class="sxs-lookup"><span data-stu-id="c6160-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="c6160-108">Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede.</span><span class="sxs-lookup"><span data-stu-id="c6160-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="c6160-109">Use os procedimentos a seguir para criar ou modificar um perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c6160-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="c6160-110">Para excluir um perfil de política de largura de banda, consulte [excluindo perfis de política de largura de banda de rede no Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c6160-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="c6160-111">Para criar um novo perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="c6160-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="c6160-112">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c6160-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c6160-113">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6160-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c6160-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c6160-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c6160-115">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, em política de **largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="c6160-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="c6160-116">Na página **política de largura de banda** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="c6160-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="c6160-117">Em **novo perfil de política de largura de banda**, digite um nome no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="c6160-117">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="c6160-118">Esse nome deve ser exclusivo entre todos os perfis de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c6160-118">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="c6160-119">No campo **limite de áudio** , digite um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="c6160-119">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="c6160-120">Esse valor é a quantidade máxima de largura de banda a ser alocada para todas as conexões de áudio, expressa em Kbps.</span><span class="sxs-lookup"><span data-stu-id="c6160-120">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="c6160-121">Insira um valor numérico no campo **limite da sessão de áudio** .</span><span class="sxs-lookup"><span data-stu-id="c6160-121">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="c6160-122">Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de áudio individual, expressa em Kbps.</span><span class="sxs-lookup"><span data-stu-id="c6160-122">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="c6160-123">Esse valor deve ser 40 ou superior.</span><span class="sxs-lookup"><span data-stu-id="c6160-123">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="c6160-124">Insira um valor numérico no campo **limite de vídeo** .</span><span class="sxs-lookup"><span data-stu-id="c6160-124">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="c6160-125">Esse valor é a quantidade máxima de largura de banda a ser alocada para todas as conexões de vídeo, expressa em Kbps.</span><span class="sxs-lookup"><span data-stu-id="c6160-125">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="c6160-126">Insira um valor numérico no campo **limite da sessão de vídeo** .</span><span class="sxs-lookup"><span data-stu-id="c6160-126">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="c6160-127">Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de vídeo individual, expressa em Kbps.</span><span class="sxs-lookup"><span data-stu-id="c6160-127">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="c6160-128">Esse valor deve ser 100 ou superior.</span><span class="sxs-lookup"><span data-stu-id="c6160-128">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="c6160-129">Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre esse perfil de política de largura de banda que não pode ser expresso apenas com o nome.</span><span class="sxs-lookup"><span data-stu-id="c6160-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="c6160-130">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c6160-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6160-131">A criação de um novo perfil de política de largura de banda não impõe automaticamente restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c6160-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="c6160-132">Você deve primeiro associar o perfil de política a um site.</span><span class="sxs-lookup"><span data-stu-id="c6160-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="c6160-133">Para obter detalhes sobre como associar um perfil de política a um site, consulte <A href="lync-server-2013-creating-or-modifying-network-sites.md">criando ou modificando sites de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c6160-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="c6160-134">Para modificar um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="c6160-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="c6160-135">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c6160-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c6160-136">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6160-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c6160-137">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c6160-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c6160-138">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, em política de **largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="c6160-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="c6160-139">Na página **política de largura de banda** , clique no perfil de política de largura de banda que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="c6160-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="c6160-140">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c6160-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c6160-141">Na página **Editar perfil da política de largura de banda** , modifique os campos conforme necessário (para obter detalhes, consulte a seção "para criar um perfil de política de largura de banda" anteriormente neste tópico).</span><span class="sxs-lookup"><span data-stu-id="c6160-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="c6160-142">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c6160-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6160-143">Quando você modifica o perfil da política de largura de banda, ele atualiza imediatamente as limitações de largura de banda de todos os sites de rede associados a este perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c6160-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6160-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="c6160-144">See Also</span></span>


[<span data-ttu-id="c6160-145">Excluindo perfis de política de largura de banda de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6160-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="c6160-146">Configurar o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6160-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="c6160-147">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c6160-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="c6160-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c6160-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="c6160-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c6160-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

