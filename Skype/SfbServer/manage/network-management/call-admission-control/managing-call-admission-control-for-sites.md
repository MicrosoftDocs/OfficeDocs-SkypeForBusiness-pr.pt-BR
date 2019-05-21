---
title: Gerenciando o controle de admissão de chamadas para sites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sites de rede são os escritórios ou locais em cada região de rede do controle de admissão de chamadas (CAC), E9-1-1 e implantações de bypass de mídia.
ms.openlocfilehash: a90781eae38d92d560dd1bf34db3b6918e8aeaf5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279540"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="ef6b1-103">Gerenciar o controle de admissão de chamadas para sites no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ef6b1-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="ef6b1-104">Sites de rede são os escritórios ou locais em cada região de rede do controle de admissão de chamadas (CAC), E9-1-1 e implantações de bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="ef6b1-105">Use os procedimentos deste artigo para configurar o controle de admissão de chamadas para sites de rede.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="ef6b1-106">Configurar links de sites de rede</span><span class="sxs-lookup"><span data-stu-id="ef6b1-106">Configure network site links</span></span>

<span data-ttu-id="ef6b1-107">Em uma configuração de controle de admissão de chamadas (CAC), você pode criar políticas entre sites de rede que definem as limitações de largura de banda entre sites vinculados diretamente.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="ef6b1-108">Quando os sites de rede compartilham um link direto, as limitações de largura de banda para conexões de áudio e vídeo podem ser definidas entre esses dois sites.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="ef6b1-109">Você não pode usar o painel de controle do Skype for Business Server para configurar políticas de site de rede, isso pode ser feito somente usando cmdlets do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ef6b1-110">Você pode criar, modificar e remover um link de site de rede (também conhecido como política entre sites de rede) do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="ef6b1-111">Para criar um link de site de rede</span><span class="sxs-lookup"><span data-stu-id="ef6b1-111">To create a network site link</span></span>

1.  <span data-ttu-id="ef6b1-112">Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="ef6b1-113">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business Server**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="ef6b1-114">No prompt de comando, digite o comando a seguir, substituindo os valores válidos para a sua configuração:</span><span class="sxs-lookup"><span data-stu-id="ef6b1-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="ef6b1-115">Este exemplo cria um novo link de site de rede\_chamado Reno Portland que define as limitações de largura de banda entre os sites de rede Reno e Portland.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="ef6b1-116">Os sites de rede e o perfil da política de largura de banda já devem existir antes de executar este comando.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="ef6b1-117">Para obter descrições de parâmetros detalhadas, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="ef6b1-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="ef6b1-118">Para recuperar uma lista de perfis de política de largura de banda que podem ser aplicados ao link de site de rede, chame o cmdlet **Get-CsNetworkBandwidthPolicyProfile** .</span><span class="sxs-lookup"><span data-stu-id="ef6b1-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="ef6b1-119">Para obter detalhes, consulte [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="ef6b1-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="ef6b1-120">Para modificar um link de site de rede</span><span class="sxs-lookup"><span data-stu-id="ef6b1-120">To modify a network site link</span></span>

1.  <span data-ttu-id="ef6b1-121">Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="ef6b1-122">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business Server**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="ef6b1-123">Use o cmdlet **set-CsNetworkInterSitePolicy** para modificar as propriedades de um determinado link de site de rede.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="ef6b1-124">Você pode modificar um (ou ambos) ou os sites conectados, e pode modificar o perfil da política de largura de banda associado ao link.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="ef6b1-125">Aqui está um exemplo de modificação do perfil da política de largura de banda de um\_link de site chamado Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="ef6b1-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="ef6b1-126">Para obter descrições de parâmetros detalhadas, consulte [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="ef6b1-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="ef6b1-127">Para excluir um link de site de rede</span><span class="sxs-lookup"><span data-stu-id="ef6b1-127">To delete a network site link</span></span>

1.  <span data-ttu-id="ef6b1-128">Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="ef6b1-129">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business Server**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="ef6b1-130">Use o cmdlet **Remove-CsNetworkInterSitePolicy** para remover um link de site de rede.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="ef6b1-131">O exemplo a seguir exclui o\_link de site de rede de Portland Reno:</span><span class="sxs-lookup"><span data-stu-id="ef6b1-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="ef6b1-132">Para obter descrições de parâmetros detalhadas, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="ef6b1-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="ef6b1-133">Exibir informações do site de rede</span><span class="sxs-lookup"><span data-stu-id="ef6b1-133">View network site information</span></span>

<span data-ttu-id="ef6b1-134">Sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou implantação 9-1-1 aprimorada.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="ef6b1-135">Você pode exibir as informações do site de rede no painel de controle do Skype for Business Server ou no Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="ef6b1-136">Para ver as informações do site de rede no painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ef6b1-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ef6b1-137">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ef6b1-138">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ef6b1-139">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **site**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="ef6b1-140">Na página do **site** , clique no site que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="ef6b1-141">Você só pode exibir informações de um site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="ef6b1-142">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ef6b1-143">Exibir informações do site de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef6b1-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ef6b1-144">Você pode exibir informações do site de rede usando o Windows PowerShell e o cmdlet Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="ef6b1-145">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="ef6b1-146">Para ver as informações do site de rede</span><span class="sxs-lookup"><span data-stu-id="ef6b1-146">To view network site information</span></span>

  - <span data-ttu-id="ef6b1-147">Para ver informações sobre todos os seus sites de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="ef6b1-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="ef6b1-148">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="ef6b1-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="ef6b1-149">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="ef6b1-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="ef6b1-150">Criar ou modificar sites de rede</span><span class="sxs-lookup"><span data-stu-id="ef6b1-150">Create or modify network sites</span></span> 

<span data-ttu-id="ef6b1-151">Sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou implantação 9-1-1 aprimorada.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="ef6b1-152">Você pode usar o painel de controle do Skype for Business Server para configurar sites e associá-los a regiões.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="ef6b1-153">Por exemplo, uma região de rede para a América do Norte pode estar associada a sites de redes como Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="ef6b1-154">Um site de rede do CAC deve ser criado para cada site dentro de uma organização, mesmo que esse site não tenha limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="ef6b1-155">No painel de controle do Skype for Business Server, você pode criar, modificar e excluir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="ef6b1-156">Use os procedimentos a seguir para criar ou modificar um site de rede.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="ef6b1-157">Para criar um site de rede</span><span class="sxs-lookup"><span data-stu-id="ef6b1-157">To create a network site</span></span>

1.  <span data-ttu-id="ef6b1-158">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ef6b1-159">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ef6b1-160">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **site**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="ef6b1-161">Na página do **site** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="ef6b1-162">Em **novo site**, digite um nome para este site no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="ef6b1-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ef6b1-163">Os nomes dos sites devem ser exclusivos na implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="ef6b1-164">Na lista suspensa **região** , selecione uma região de rede para associar a este site.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="ef6b1-165">Adicionais Se você quiser colocar as limitações de largura de banda em chamadas de áudio ou vídeo para este site, selecione o perfil da política de largura de banda com as configurações apropriadas na lista suspensa **política de largura de banda** .</span><span class="sxs-lookup"><span data-stu-id="ef6b1-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="ef6b1-166">Você pode exibir os detalhes dos perfis da política de largura de banda disponíveis ou criar um novo perfil de política de largura de banda na página **Profil da política** do grupo **configuração de rede** .</span><span class="sxs-lookup"><span data-stu-id="ef6b1-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="ef6b1-167">Para obter detalhes, consulte [Gerenciando perfis da política de largura de banda de rede](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ef6b1-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="ef6b1-168">Adicionais Se você quiser fornecer configurações de localização para este site, selecione uma política de localização na lista suspensa **política de localização** .</span><span class="sxs-lookup"><span data-stu-id="ef6b1-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ef6b1-169">A política de localização atribui configurações de localização avançada de 9-1-1 (E9-1-1) e de cliente de cliente (-1-1) específicas ao site.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="ef6b1-170">Você pode exibir os detalhes das políticas de localização disponíveis ou criar uma nova política de localização, na página **política de localização** do grupo de **configuração de rede** .</span><span class="sxs-lookup"><span data-stu-id="ef6b1-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="ef6b1-171">Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre esse site que não pode ser expresso apenas pelo nome.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="ef6b1-172">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ef6b1-173">Você não usa a tabela de **sub-redes associadas** quando cria um novo site de rede.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="ef6b1-174">Você associa uma sub-rede a um site quando cria ou modifica a sub-rede.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="ef6b1-175">Para obter detalhes, consulte [Gerenciando sub-redes de rede](managing-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="ef6b1-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="ef6b1-176">Para modificar um site de rede</span><span class="sxs-lookup"><span data-stu-id="ef6b1-176">To modify a network site</span></span>

1.  <span data-ttu-id="ef6b1-177">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ef6b1-178">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ef6b1-179">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **site**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="ef6b1-180">Na página do **site** , clique no site que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="ef6b1-181">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ef6b1-182">Na página **Editar site** , você pode modificar a descrição, a região, o perfil da política de largura de banda e a política de localização associada ao site.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="ef6b1-183">Para obter detalhes, consulte [criar um site de rede](#to-create-a-network-site) acima.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="ef6b1-184">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-184">Click **Commit**.</span></span>

<span data-ttu-id="ef6b1-185">Não é possível modificar a tabela de **sub-redes associadas** nesta página.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="ef6b1-186">A lista de sub-redes associadas é fornecida para referência para que você saiba quais são as sub-redes que serão afetadas quando você modificar as configurações do site.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="ef6b1-187">Excluir um site de rede existente</span><span class="sxs-lookup"><span data-stu-id="ef6b1-187">Delete an existing network site</span></span>

<span data-ttu-id="ef6b1-188">Sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou implantação 9-1-1 aprimorada.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="ef6b1-189">Você pode usar o painel de controle do Skype for Business Server para configurar sites e associá-los a regiões.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="ef6b1-190">Por exemplo, uma região de rede para a América do Norte pode estar associada a sites de redes como Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="ef6b1-191">Um site de rede do CAC deve ser criado para cada site dentro de uma organização, mesmo que esse site não tenha limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="ef6b1-192">No painel de controle do Skype for Business Server, você pode criar, modificar e excluir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="ef6b1-193">Use o procedimento a seguir para excluir um site de rede existente.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="ef6b1-194">Para obter detalhes sobre como criar ou modificar sites de rede, consulte Gerenciando o [controle de admissão de chamadas para sites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="ef6b1-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="ef6b1-195">Para excluir um site de rede</span><span class="sxs-lookup"><span data-stu-id="ef6b1-195">To delete a network site</span></span>

1.  <span data-ttu-id="ef6b1-196">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ef6b1-197">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ef6b1-198">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **site**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="ef6b1-199">Na página do **site** , clique no site que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ef6b1-200">Você pode excluir mais de um site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="ef6b1-201">Para fazer isso, pressione CTRL e selecione vários sites enquanto mantém a tecla CTRL pressionada.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="ef6b1-202">Ou, para selecionar todos os sites, clique em **selecionar tudo** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="ef6b1-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="ef6b1-203">No menu **Editar** , clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ef6b1-204">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="ef6b1-205">Você não pode remover um site de rede se ele estiver associado a uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="ef6b1-206">Se você tentar remover um site associado a uma sub-rede, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="ef6b1-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="ef6b1-207">Para ver se um site está associado a qualquer sub-rede, clique no site e, em seguida, clique em **Mostrar detalhes** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="ef6b1-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="ef6b1-208">Confira também</span><span class="sxs-lookup"><span data-stu-id="ef6b1-208">See Also</span></span>


[<span data-ttu-id="ef6b1-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ef6b1-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="ef6b1-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ef6b1-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="ef6b1-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ef6b1-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="ef6b1-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ef6b1-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="ef6b1-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ef6b1-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="ef6b1-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ef6b1-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="ef6b1-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ef6b1-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="ef6b1-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ef6b1-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="ef6b1-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ef6b1-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
