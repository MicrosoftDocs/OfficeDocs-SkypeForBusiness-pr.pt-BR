---
title: Gerenciando o controle de admissão de chamada para sites
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Os sites de rede são os escritórios ou locais em cada região de rede do controle de admissão de chamadas (CAC), E9-1-1 e implantações de bypass de mídia.
ms.openlocfilehash: dbe02c78c40cab48a79d7c63d3c6239b4ae59458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816451"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="09704-103">Gerenciando o controle de admissão de chamadas para sites no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="09704-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="09704-104">Os sites de rede são os escritórios ou locais em cada região de rede do controle de admissão de chamadas (CAC), E9-1-1 e implantações de bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="09704-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="09704-105">Use os procedimentos neste artigo para configurar o controle de admissão de chamada para sites de rede.</span><span class="sxs-lookup"><span data-stu-id="09704-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="09704-106">Configurar links de site de rede</span><span class="sxs-lookup"><span data-stu-id="09704-106">Configure network site links</span></span>

<span data-ttu-id="09704-107">Em uma configuração de controle de admissão de chamada, você pode criar políticas entre locais de rede que definem as limitações de largura de banda entre os locais que estejam diretamente vinculados.</span><span class="sxs-lookup"><span data-stu-id="09704-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="09704-108">Quando os locais de uma rede compartilham um link direto, é possível definir limitações de largura de banda às conexões audiovisuais entre esses dois locais.</span><span class="sxs-lookup"><span data-stu-id="09704-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="09704-109">Não é possível usar o Painel de Controle do Skype for Business Server para configurar políticas de site de rede, isso só pode ser feito usando cmdlets do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="09704-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="09704-110">Você pode criar, modificar e remover um link de site de rede (também conhecido como política entre sites de rede) do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="09704-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="09704-111">Para criar um link de site de rede</span><span class="sxs-lookup"><span data-stu-id="09704-111">To create a network site link</span></span>

1.  <span data-ttu-id="09704-112">Faça logoff no computador em que o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.</span><span class="sxs-lookup"><span data-stu-id="09704-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="09704-113">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business Server** e, em seguida, clique no Shell de Gerenciamento do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="09704-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="09704-114">No prompt de comando, digite o seguinte comando, substituindo os valores que são válidos para a sua configuração:</span><span class="sxs-lookup"><span data-stu-id="09704-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="09704-115">Este exemplo cria um novo link de site de rede chamado Reno Portland que define limitações de largura de banda entre os sites de rede Reno e \_ Portland.</span><span class="sxs-lookup"><span data-stu-id="09704-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="09704-116">Os sites de rede e o perfil da política de largura de banda já devem existir antes de executar este comando.</span><span class="sxs-lookup"><span data-stu-id="09704-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="09704-117">Para descrições detalhadas dos parâmetros, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="09704-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="09704-118">Para recuperar uma lista de perfis de políticas de largura de banda que podem ser aplicada ao link de site de rede, chame o cmdlet de **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="09704-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="09704-119">Para obter detalhes, [consulte Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="09704-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="09704-120">Para modificar um link de site de rede</span><span class="sxs-lookup"><span data-stu-id="09704-120">To modify a network site link</span></span>

1.  <span data-ttu-id="09704-121">Faça logoff no computador em que o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.</span><span class="sxs-lookup"><span data-stu-id="09704-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="09704-122">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business Server** e, em seguida, clique no Shell de Gerenciamento do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="09704-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="09704-123">Use o cmdlet **Set-CsNetworkInterSitePolicy** para modificar as propriedades de um link de site de rede fornecido.</span><span class="sxs-lookup"><span data-stu-id="09704-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="09704-124">Você pode modificar um (ou ambos) dos sites conectados e modificar o perfil da política de largura de banda associado ao link.</span><span class="sxs-lookup"><span data-stu-id="09704-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="09704-125">Aqui está um exemplo de modificação do perfil de política de largura de banda de um link de site chamado Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="09704-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="09704-126">Para descrições detalhadas de parâmetros, consulte [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="09704-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="09704-127">Para excluir um link de site de rede</span><span class="sxs-lookup"><span data-stu-id="09704-127">To delete a network site link</span></span>

1.  <span data-ttu-id="09704-128">Faça logoff no computador em que o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.</span><span class="sxs-lookup"><span data-stu-id="09704-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="09704-129">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business Server** e, em seguida, clique no Shell de Gerenciamento do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="09704-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="09704-130">Use o cmdlet **Remove-CsNetworkInterSitePolicy** para remover um link de site de rede.</span><span class="sxs-lookup"><span data-stu-id="09704-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="09704-131">O exemplo a seguir exclui o link de site de rede Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="09704-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="09704-132">Para descrições detalhadas de parâmetros, [consulte Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="09704-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="09704-133">Exibir informações de site de rede</span><span class="sxs-lookup"><span data-stu-id="09704-133">View network site information</span></span>

<span data-ttu-id="09704-134">Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado.</span><span class="sxs-lookup"><span data-stu-id="09704-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="09704-135">Você pode exibir informações do site de rede no Painel de Controle do Skype for Business Server ou no Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="09704-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="09704-136">Para exibir informações do site de rede no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="09704-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="09704-137">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="09704-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="09704-138">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="09704-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="09704-139">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Site.**</span><span class="sxs-lookup"><span data-stu-id="09704-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="09704-140">Na página **Local**, clique no local que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="09704-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="09704-141">É possível exibir apenas informações de um local por vez.</span><span class="sxs-lookup"><span data-stu-id="09704-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="09704-142">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="09704-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="09704-143">Exibindo informações de site de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09704-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="09704-144">Você pode exibir informações do site de rede usando o Windows PowerShell e o Get-CsNetworkSite cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09704-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="09704-145">Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09704-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="09704-146">Para exibir a informação do local de rede</span><span class="sxs-lookup"><span data-stu-id="09704-146">To view network site information</span></span>

  - <span data-ttu-id="09704-147">Para exibir informações sobre todos os seus sites de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="09704-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="09704-148">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="09704-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="09704-149">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="09704-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="09704-150">Criar ou modificar sites de rede</span><span class="sxs-lookup"><span data-stu-id="09704-150">Create or modify network sites</span></span> 

<span data-ttu-id="09704-151">Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado.</span><span class="sxs-lookup"><span data-stu-id="09704-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="09704-152">Você pode usar o Painel de Controle do Skype for Business Server para configurar sites e associá-los a regiões.</span><span class="sxs-lookup"><span data-stu-id="09704-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="09704-153">Por exemplo, uma região de rede da América do Norte pode ser associada a sites da rede, como Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="09704-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="09704-154">Um site da rede do CAC deve ser criado para cada site da organização, mesmo que esse site não tenha limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="09704-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="09704-155">No Painel de Controle do Skype for Business Server, você pode criar, modificar e excluir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="09704-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="09704-156">Use os procedimentos a seguir para criar ou modificar um site da rede.</span><span class="sxs-lookup"><span data-stu-id="09704-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="09704-157">Para criar um local de rede</span><span class="sxs-lookup"><span data-stu-id="09704-157">To create a network site</span></span>

1.  <span data-ttu-id="09704-158">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="09704-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="09704-159">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="09704-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="09704-160">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Site.**</span><span class="sxs-lookup"><span data-stu-id="09704-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="09704-161">Na página **Local**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="09704-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="09704-162">Em **Novo Local**, digite um nome para este local no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="09704-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="09704-163">Os nomes de site devem ser exclusivos na implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="09704-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="09704-164">Na lista suspensa **Região**, selecione uma região da rede para associar a este local.</span><span class="sxs-lookup"><span data-stu-id="09704-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="09704-165">(Opcional) Se deseja impor limitações de largura de banda em chamadas de áudio ou vídeo para este local, selecione o perfil da política da largura de banda com as configurações apropriadas na lista suspensa **Política da largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="09704-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="09704-166">Você pode exibir os detalhes dos perfis de política de largura de banda disponíveis ou criar um novo perfil de política de largura de banda na página **Profil** de Política do grupo **Configuração de** Rede.</span><span class="sxs-lookup"><span data-stu-id="09704-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="09704-167">Para obter detalhes, consulte [Gerenciando perfis de política de largura de banda de rede.](managing-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="09704-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="09704-168">(Opcional) Se deseja fornecer configurações de localização para esse local, selecione uma política de localização na lista suspensa **Política de localização**.</span><span class="sxs-lookup"><span data-stu-id="09704-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="09704-169">A política de localização atribui configurações específicas de 9-1-1 Aprimorado (E9-1-1) e de localização do cliente ao local.</span><span class="sxs-lookup"><span data-stu-id="09704-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="09704-170">Você pode ver os detalhes das políticas de localização disponíveis ou criar uma política nova na página **Política de localização** do grupo **Configuração de Rede**.</span><span class="sxs-lookup"><span data-stu-id="09704-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="09704-171">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse local, que não podem ser expressadas apenas pelo nome.</span><span class="sxs-lookup"><span data-stu-id="09704-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="09704-172">Clique em **Comprometer**.</span><span class="sxs-lookup"><span data-stu-id="09704-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="09704-173">Você não usa a tabela **Sub-redes Associadas** ao criar um novo local de rede.</span><span class="sxs-lookup"><span data-stu-id="09704-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="09704-174">Você associa a sub-rede ao local quando criá-la ou modificá-la.</span><span class="sxs-lookup"><span data-stu-id="09704-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="09704-175">Para obter detalhes, consulte [Gerenciando sub-redes de rede.](managing-network-subnets.md)</span><span class="sxs-lookup"><span data-stu-id="09704-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="09704-176">Para modificar um local de rede</span><span class="sxs-lookup"><span data-stu-id="09704-176">To modify a network site</span></span>

1.  <span data-ttu-id="09704-177">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="09704-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="09704-178">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="09704-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="09704-179">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Site.**</span><span class="sxs-lookup"><span data-stu-id="09704-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="09704-180">Na página **Local**, clique no local que deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="09704-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="09704-181">No painel **Ações**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="09704-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="09704-182">Na página **Editar Local**, você pode modificar a descrição, região, perfil da política da largura de banda e política de localização associados ao novo local.</span><span class="sxs-lookup"><span data-stu-id="09704-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="09704-183">Para obter detalhes, [consulte Para criar um site de rede](#to-create-a-network-site) acima.</span><span class="sxs-lookup"><span data-stu-id="09704-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="09704-184">Clique em **Comprometer**.</span><span class="sxs-lookup"><span data-stu-id="09704-184">Click **Commit**.</span></span>

<span data-ttu-id="09704-p114">Você não pode modificar a tabela **Sub-redes Associadas** nesta página. A lista de sub-redes associadas é fornecida para referência, para que você saiba quais sub-redes serão afetadas quando você modificar as configurações do local.</span><span class="sxs-lookup"><span data-stu-id="09704-p114">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="09704-187">Excluir um site de rede existente</span><span class="sxs-lookup"><span data-stu-id="09704-187">Delete an existing network site</span></span>

<span data-ttu-id="09704-188">Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado.</span><span class="sxs-lookup"><span data-stu-id="09704-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="09704-189">Você pode usar o Painel de Controle do Skype for Business Server para configurar sites e associá-los a regiões.</span><span class="sxs-lookup"><span data-stu-id="09704-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="09704-190">Por exemplo, uma região de rede da América do Norte pode ser associada a sites da rede, como Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="09704-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="09704-191">Um site da rede do CAC deve ser criado para cada site da organização, mesmo que esse site não tenha limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="09704-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="09704-192">No Painel de Controle do Skype for Business Server, você pode criar, modificar e excluir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="09704-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="09704-193">Use o seguinte procedimento para excluir um local de rede existente.</span><span class="sxs-lookup"><span data-stu-id="09704-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="09704-194">Para obter detalhes sobre como criar ou modificar sites de rede, consulte [Gerenciando o controle de admissão de chamada para sites.](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="09704-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="09704-195">Para excluir um local de rede</span><span class="sxs-lookup"><span data-stu-id="09704-195">To delete a network site</span></span>

1.  <span data-ttu-id="09704-196">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="09704-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="09704-197">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="09704-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="09704-198">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Site.**</span><span class="sxs-lookup"><span data-stu-id="09704-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="09704-199">Na página **Local**, clique no local que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="09704-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="09704-p116">Você pode excluir mais de um local de cada vez. Para fazer isso, pressione CTRL e selecione diversos locais mantendo a tecla pressionada. Ou então, para selecionar todos os locais, clique em **Selecionar Tudo** no menu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="09704-p116">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="09704-203">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="09704-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="09704-204">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="09704-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="09704-p117">Você não poderá remover um local de rede se ele estiver associado a uma sub-rede. Se você tentar fazer isso, receberá uma mensagem de erro. Para ver se o local está associado a alguma sub-rede, clique no local e em **Mostrar detalhes** no menu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="09704-p117">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="09704-208">Confira também</span><span class="sxs-lookup"><span data-stu-id="09704-208">See Also</span></span>


[<span data-ttu-id="09704-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="09704-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="09704-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="09704-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="09704-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="09704-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="09704-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="09704-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="09704-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="09704-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="09704-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="09704-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="09704-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="09704-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="09704-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="09704-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="09704-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="09704-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
