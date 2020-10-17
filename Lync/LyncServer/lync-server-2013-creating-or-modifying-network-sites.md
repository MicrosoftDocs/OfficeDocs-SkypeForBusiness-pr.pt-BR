---
title: 'Lync Server 2013: Criando ou modificando sites de rede'
description: 'Lync Server 2013: Criando ou modificando sites de rede.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 700f089cfe190a8f46b5eefc05e656e7c62a59a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544007"
---
# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="3ea02-103">Criando ou modificando sites de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ea02-103">Creating or modifying network sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ea02-104">_**Última modificação do tópico:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="3ea02-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="3ea02-105">Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado.</span><span class="sxs-lookup"><span data-stu-id="3ea02-105">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="3ea02-106">Você pode usar o painel de controle do Microsoft Lync Server 2013 para configurar sites e associá-los a regiões.</span><span class="sxs-lookup"><span data-stu-id="3ea02-106">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="3ea02-107">Por exemplo, uma região de rede da América do Norte pode ser associada a sites da rede, como Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="3ea02-107">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="3ea02-108">Um site da rede do CAC deve ser criado para cada site da organização, mesmo que esse site não tenha limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="3ea02-108">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="3ea02-109">No painel de controle do Lync Server, você pode criar, modificar e excluir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="3ea02-109">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="3ea02-110">Use os procedimentos a seguir para criar ou modificar um site da rede.</span><span class="sxs-lookup"><span data-stu-id="3ea02-110">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="3ea02-111">Para obter detalhes sobre como excluir um site de rede existente, consulte [excluindo um site de rede existente no Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="3ea02-111">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="3ea02-112">Para criar um local de rede</span><span class="sxs-lookup"><span data-stu-id="3ea02-112">To create a network site</span></span>

1.  <span data-ttu-id="3ea02-113">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3ea02-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3ea02-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ea02-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3ea02-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3ea02-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3ea02-116">Na barra de navegação esquerda, clique em **Configuração da Rede** e em **Local**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-116">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="3ea02-117">Na página **Local**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-117">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="3ea02-118">Em **Novo Local**, digite um nome para este local no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-118">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ea02-119">Os nomes de site devem ser exclusivos na implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ea02-119">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="3ea02-120">Na lista suspensa **Região**, selecione uma região da rede para associar a este local.</span><span class="sxs-lookup"><span data-stu-id="3ea02-120">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="3ea02-121">(Opcional) Se deseja impor limitações de largura de banda em chamadas de áudio ou vídeo para este local, selecione o perfil da política da largura de banda com as configurações apropriadas na lista suspensa **Política da largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-121">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ea02-122">Você pode ver os detalhes dos perfis disponíveis da política de largura de banda, ou criar um novo perfil, na página <STRONG>Perfil de Política</STRONG> do grupo <STRONG>Configuração de Rede</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3ea02-122">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="3ea02-123">Para obter detalhes, consulte <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">criando ou modificando perfis de política de largura de banda no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3ea02-123">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="3ea02-124">(Opcional) Se deseja fornecer configurações de localização para esse local, selecione uma política de localização na lista suspensa **Política de localização**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-124">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ea02-125">A política de localização atribui configurações específicas de 9-1-1 Aprimorado (E9-1-1) e de localização do cliente ao local.</span><span class="sxs-lookup"><span data-stu-id="3ea02-125">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="3ea02-126">Você pode ver os detalhes das políticas de localização disponíveis ou criar uma política nova na página <STRONG>Política de localização</STRONG> do grupo <STRONG>Configuração de Rede</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3ea02-126">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="3ea02-127">Para obter detalhes, consulte <A href="lync-server-2013-viewing-location-policy-information.md">Viewing Location Policy Information in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3ea02-127">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="3ea02-128">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse local, que não podem ser expressadas apenas pelo nome.</span><span class="sxs-lookup"><span data-stu-id="3ea02-128">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="3ea02-129">Clique em **Comprometer**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-129">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ea02-130">Você não usa a tabela <STRONG>Sub-redes Associadas</STRONG> ao criar um novo local de rede.</span><span class="sxs-lookup"><span data-stu-id="3ea02-130">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="3ea02-131">Você associa a sub-rede ao local quando criá-la ou modificá-la.</span><span class="sxs-lookup"><span data-stu-id="3ea02-131">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="3ea02-132">Para obter detalhes, consulte <A href="lync-server-2013-create-or-modify-network-subnets.md">create or Modify Network sub-redes in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3ea02-132">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="3ea02-133">Para modificar um local de rede</span><span class="sxs-lookup"><span data-stu-id="3ea02-133">To modify a network site</span></span>

1.  <span data-ttu-id="3ea02-134">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3ea02-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3ea02-135">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ea02-135">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3ea02-136">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3ea02-136">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3ea02-137">Na barra de navegação esquerda, clique em **Configuração da Rede** e em **Local**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-137">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="3ea02-138">Na página **Local**, clique no local que deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="3ea02-138">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="3ea02-139">No painel **Ações**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-139">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="3ea02-p107">Na página **Editar Local**, você pode modificar a descrição, região, perfil da política da largura de banda e política de localização associados ao novo local. Para obter os detalhes, consulte a seção "Para criar um local de rede" anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3ea02-p107">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site. For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="3ea02-142">Clique em **Comprometer**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-142">Click **Commit**.</span></span>

<span data-ttu-id="3ea02-p108">Você não pode modificar a tabela **Sub-redes Associadas** nesta página. A lista de sub-redes associadas é fornecida para referência, para que você saiba quais sub-redes serão afetadas quando você modificar as configurações do local.</span><span class="sxs-lookup"><span data-stu-id="3ea02-p108">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="3ea02-145">Para excluir um local de rede</span><span class="sxs-lookup"><span data-stu-id="3ea02-145">To delete a network site</span></span>

1.  <span data-ttu-id="3ea02-146">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3ea02-146">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3ea02-147">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ea02-147">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3ea02-148">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3ea02-148">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3ea02-149">Na barra de navegação esquerda, clique em **Configuração da Rede** e em **Local**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-149">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="3ea02-150">Na página **Local**, clique no local que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="3ea02-150">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ea02-p110">Você pode excluir mais de um local de cada vez. Para fazer isso, pressione CTRL e selecione diversos locais mantendo a tecla pressionada. Ou então, para selecionar todos os locais, clique em <STRONG>Selecionar Tudo</STRONG> no menu <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3ea02-p110">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="3ea02-154">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-154">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="3ea02-155">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ea02-155">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3ea02-p111">Você não poderá remover um local de rede se ele estiver associado a uma sub-rede. Se você tentar fazer isso, receberá uma mensagem de erro. Para ver se o local está associado a alguma sub-rede, clique no local e em <STRONG>Mostrar detalhes</STRONG> no menu <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3ea02-p111">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ea02-159">Confira também</span><span class="sxs-lookup"><span data-stu-id="3ea02-159">See Also</span></span>


[<span data-ttu-id="3ea02-160">Excluindo um site de rede existente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ea02-160">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="3ea02-161">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3ea02-161">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="3ea02-162">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3ea02-162">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="3ea02-163">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3ea02-163">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="3ea02-164">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3ea02-164">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

