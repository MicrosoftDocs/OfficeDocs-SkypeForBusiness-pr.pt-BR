---
title: 'Lync Server 2013: Criando ou modificando perfis de política de largura de banda'
description: 'Lync Server 2013: Criando ou modificando perfis de política de largura de banda.'
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
ms.openlocfilehash: de8450cf8f4da53bf4a7e096fd7618b7fc6d055b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562967"
---
# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="d93fc-103">Criando ou modificando perfis de política de largura de banda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d93fc-103">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d93fc-104">_**Última modificação do tópico:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="d93fc-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="d93fc-105">Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades.</span><span class="sxs-lookup"><span data-stu-id="d93fc-105">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="d93fc-106">No Microsoft Lync Server 2013, somente as modalidades de áudio e vídeo podem ser atribuídas a limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="d93fc-106">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="d93fc-107">Você pode configurar os limites gerais de banda e os limites de sessão.</span><span class="sxs-lookup"><span data-stu-id="d93fc-107">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="d93fc-108">Você pode usar o painel de controle do Lync Server para criar, modificar ou excluir um perfil de contêiner para essas políticas.</span><span class="sxs-lookup"><span data-stu-id="d93fc-108">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="d93fc-109">Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede.</span><span class="sxs-lookup"><span data-stu-id="d93fc-109">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="d93fc-110">Use os procedimentos a seguir para criar ou modificar um perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="d93fc-110">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="d93fc-111">Para excluir um perfil de política de largura de banda, consulte [excluindo perfis de política de largura de banda de rede no Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d93fc-111">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="d93fc-112">Para criar um novo perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="d93fc-112">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="d93fc-113">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d93fc-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d93fc-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d93fc-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d93fc-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d93fc-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d93fc-116">Na barra de navegação à esquerda, clique em **Configuração de Rede** e depois em **Política de largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="d93fc-116">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="d93fc-117">Na página **Política de largura de banda**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d93fc-117">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="d93fc-p103">Em **Novo Perfil de Política de Largura de Banda**, digite um nome no campo **Nome**. Esse nome deve ser único entre todos os perfis de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="d93fc-p103">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="d93fc-p104">No campo **Limite de áudio**, digite um valor numérico. Esse valor é a quantidade máxima de largura de banda a ser alocada a todas as conexões de áudio, expressa em kbps.</span><span class="sxs-lookup"><span data-stu-id="d93fc-p104">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="d93fc-p105">Insira um valor numérico no campo **Limite da sessão de áudio**. Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de áudio individual, expressa em kbps. Esse valor precisa ser igual a ou maior que 40.</span><span class="sxs-lookup"><span data-stu-id="d93fc-p105">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="d93fc-p106">Insira um valor numérico no campo **Limite de vídeo**. Esse valor é quantidade máxima de largura de banda a ser alocada para todas as conexões de vídeo, expressa em kbps.</span><span class="sxs-lookup"><span data-stu-id="d93fc-p106">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="d93fc-p107">Insira um valor numérico no campo **Limite de sessão de vídeo**. Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de vídeo individual, expressa em kbps. Esse valor precisa ser igual a ou maior que 100.</span><span class="sxs-lookup"><span data-stu-id="d93fc-p107">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="d93fc-130">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse perfil da política de largura de banda que não pode ser expressa somente pelo nome.</span><span class="sxs-lookup"><span data-stu-id="d93fc-130">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="d93fc-131">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d93fc-131">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d93fc-132">Criar um novo perfil de política de largura de banda não reforça as restrições de largura de banda automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d93fc-132">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="d93fc-133">É preciso, primeiro, associar o perfil da política com um site.</span><span class="sxs-lookup"><span data-stu-id="d93fc-133">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="d93fc-134">Para obter detalhes sobre como associar um perfil de política a um site, consulte <A href="lync-server-2013-creating-or-modifying-network-sites.md">criando ou modificando sites de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d93fc-134">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="d93fc-135">Para modificar um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="d93fc-135">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="d93fc-136">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d93fc-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d93fc-137">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d93fc-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d93fc-138">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d93fc-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d93fc-139">Na barra de navegação à esquerda, clique em **Configuração de rede** e clique em **Política de largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="d93fc-139">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="d93fc-140">Na página **Política de largura de banda**, clique no perfil da política de largura de banda que você quer modificar.</span><span class="sxs-lookup"><span data-stu-id="d93fc-140">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="d93fc-141">No menu **Editar**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d93fc-141">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="d93fc-142">Na página **Editar Perfil de Política de Largura de Banda**, modifique os campos conforme necessário (para obter mais detalhes, consulte a seção "Para criar um novo perfil de política de largura de banda", já vista neste tópico).</span><span class="sxs-lookup"><span data-stu-id="d93fc-142">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="d93fc-143">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d93fc-143">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d93fc-144">Ao modificar o perfil de política de largura de banda, as limitações de largura de banda de todos os sites da rede associados a esse perfil serão atualizadas imediatamente.</span><span class="sxs-lookup"><span data-stu-id="d93fc-144">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d93fc-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="d93fc-145">See Also</span></span>


[<span data-ttu-id="d93fc-146">Excluindo perfis de política de largura de banda de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d93fc-146">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="d93fc-147">Configurar o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d93fc-147">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="d93fc-148">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="d93fc-148">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="d93fc-149">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="d93fc-149">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="d93fc-150">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="d93fc-150">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

