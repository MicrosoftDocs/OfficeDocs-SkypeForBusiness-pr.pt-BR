---
title: Gerenciando perfis de política de largura de banda de rede
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Use os procedimentos neste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.
ms.openlocfilehash: 58a73774a55a64ac6cb81f0bdf887eb0d1493a35
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222937"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="88e54-103">Gerenciando perfis de política de largura de banda de rede no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="88e54-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="88e54-104">Use os procedimentos neste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.</span><span class="sxs-lookup"><span data-stu-id="88e54-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="88e54-105">Exibir informações de perfil de política de largura de banda de rede</span><span class="sxs-lookup"><span data-stu-id="88e54-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="88e54-106">Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir as limitações de largura de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="88e54-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="88e54-107">Skype para Business Server, modalidades somente de áudio e vídeos podem ser atribuídas as limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="88e54-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="88e54-108">Você pode definir as limitações de largura de banda gerais e as limitações de sessão.</span><span class="sxs-lookup"><span data-stu-id="88e54-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="88e54-109">Você pode usar o Skype para painel de controle do Business Server para criar, modificar ou excluir um perfil de contêiner para essas diretivas.</span><span class="sxs-lookup"><span data-stu-id="88e54-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="88e54-110">Cada perfil de política de largura de banda pode ser associado um ou mais sites de rede.</span><span class="sxs-lookup"><span data-stu-id="88e54-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="88e54-111">Use os procedimentos a seguir para exibir um perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="88e54-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="88e54-112">Para exibir um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="88e54-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="88e54-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="88e54-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88e54-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="88e54-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="88e54-115">Na barra de navegação à esquerda, clique em **Configuração de rede** e clique em **Política de largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="88e54-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="88e54-116">Na página **Política de largura de banda** , clique no perfil da política de largura de banda que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="88e54-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="88e54-117">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="88e54-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="88e54-118">Exibindo informações de perfil de política de largura de banda de rede usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88e54-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="88e54-119">Perfis de largura de banda de rede podem ser exibidos usando o Windows PowerShell e o cmdlet Get-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="88e54-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="88e54-120">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88e54-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="88e54-121">Para exibir informações de perfil de política de largura de banda de rede</span><span class="sxs-lookup"><span data-stu-id="88e54-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="88e54-122">Para exibir informações sobre todos os seus perfis de política de largura de banda rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="88e54-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="88e54-123">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="88e54-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="88e54-124">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="88e54-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="88e54-125">Criar ou modificar perfis de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="88e54-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="88e54-126">Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir as limitações de largura de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="88e54-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="88e54-127">Skype para Business Server, modalidades somente de áudio e vídeos podem ser atribuídas as limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="88e54-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="88e54-128">Você pode definir as limitações de largura de banda gerais e as limitações de sessão.</span><span class="sxs-lookup"><span data-stu-id="88e54-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="88e54-129">Você pode usar o Skype para painel de controle do Business Server para criar, modificar ou excluir um perfil de contêiner para essas diretivas.</span><span class="sxs-lookup"><span data-stu-id="88e54-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="88e54-130">Cada perfil de política de largura de banda pode ser associado um ou mais sites de rede.</span><span class="sxs-lookup"><span data-stu-id="88e54-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="88e54-131">Use os procedimentos a seguir para criar ou modificar um perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="88e54-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="88e54-132">Para criar um novo perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="88e54-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="88e54-133">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="88e54-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88e54-134">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="88e54-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="88e54-135">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **Política de largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="88e54-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="88e54-136">Na página **Política de largura de banda** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="88e54-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="88e54-137">Em **Novo perfil de política de largura de banda**, digite um nome no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="88e54-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="88e54-138">Esse nome deve ser exclusivo entre todos os perfis de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="88e54-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="88e54-139">No campo de **limite de áudio** , digite um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="88e54-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="88e54-140">Esse valor é a quantidade máxima de largura de banda a se alocar para todas as conexões de áudio, expressadas em kbps.</span><span class="sxs-lookup"><span data-stu-id="88e54-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="88e54-141">Insira um valor numérico no campo de **limite de sessão de áudio** .</span><span class="sxs-lookup"><span data-stu-id="88e54-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="88e54-142">Esse valor é a quantidade máxima de largura de banda a se alocar para uma conexão de áudio individual, expressado em kbps.</span><span class="sxs-lookup"><span data-stu-id="88e54-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="88e54-143">Este valor deve ser 40 ou superior.</span><span class="sxs-lookup"><span data-stu-id="88e54-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="88e54-144">Insira um valor numérico no campo de **limite de vídeo** .</span><span class="sxs-lookup"><span data-stu-id="88e54-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="88e54-145">Esse valor é a quantidade máxima de largura de banda a se alocar para todas as conexões de vídeos, expressadas em kbps.</span><span class="sxs-lookup"><span data-stu-id="88e54-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="88e54-146">Insira um valor numérico no campo de **limite de sessão de vídeo** .</span><span class="sxs-lookup"><span data-stu-id="88e54-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="88e54-147">Esse valor é a quantidade máxima de largura de banda a se alocar para uma conexão de vídeo individual, expressado em kbps.</span><span class="sxs-lookup"><span data-stu-id="88e54-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="88e54-148">Este valor deve ser 100 ou superior.</span><span class="sxs-lookup"><span data-stu-id="88e54-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="88e54-149">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse perfil da política de largura de banda que não pode ser expressa somente pelo nome.</span><span class="sxs-lookup"><span data-stu-id="88e54-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="88e54-150">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="88e54-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="88e54-151">Criando um novo perfil de política de largura de banda não impõe restrições de largura de banda automaticamente.</span><span class="sxs-lookup"><span data-stu-id="88e54-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="88e54-152">Primeiro você deve associar o perfil da política um site.</span><span class="sxs-lookup"><span data-stu-id="88e54-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="88e54-153">Para modificar um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="88e54-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="88e54-154">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="88e54-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88e54-155">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="88e54-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="88e54-156">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **Política de largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="88e54-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="88e54-157">Na página **Política de largura de banda** , clique no perfil da política de largura de banda que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="88e54-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="88e54-158">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="88e54-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="88e54-159">Na página **Editar perfil da política de largura de banda** , modifique os campos conforme necessário (para obter detalhes, consulte [criar um novo perfil de política de largura de banda](#to-create-a-new-bandwidth-policy-profile)).</span><span class="sxs-lookup"><span data-stu-id="88e54-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="88e54-160">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="88e54-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="88e54-161">Quando você modifica o perfil de política de largura de banda, serão atualizadas imediatamente as limitações de largura de banda de todos os sites de rede associados a esse perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="88e54-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="88e54-162">Excluir perfis de política de largura de banda de rede</span><span class="sxs-lookup"><span data-stu-id="88e54-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="88e54-163">Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir as limitações de largura de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="88e54-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="88e54-164">Skype para Business Server, modalidades somente de áudio e vídeos podem ser atribuídas as limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="88e54-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="88e54-165">Você pode definir as limitações de largura de banda gerais e as limitações de sessão.</span><span class="sxs-lookup"><span data-stu-id="88e54-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="88e54-166">Você pode usar o Skype para painel de controle do Business Server para criar, modificar ou excluir um perfil de contêiner para essas diretivas.</span><span class="sxs-lookup"><span data-stu-id="88e54-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="88e54-167">Use os procedimentos a seguir para excluir um perfis de política de largura de banda de rede.</span><span class="sxs-lookup"><span data-stu-id="88e54-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="88e54-168">Para excluir um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="88e54-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="88e54-169">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="88e54-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88e54-170">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="88e54-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="88e54-171">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **Política de largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="88e54-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="88e54-172">Na página **Política de largura de banda** , clique no perfil da política de largura de banda que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="88e54-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="88e54-173">Você pode excluir mais de um perfil por vez.</span><span class="sxs-lookup"><span data-stu-id="88e54-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="88e54-174">Para fazer isso, pressione CTRL e selecione vários perfis, mantendo pressionada a tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="88e54-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="88e54-175">Ou, para selecionar todos os perfis, clique em **Selecionar tudo** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="88e54-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="88e54-176">No menu **Editar** , clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="88e54-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="88e54-177">Você não pode excluir um perfil de política de largura de banda que está associado um site de rede.</span><span class="sxs-lookup"><span data-stu-id="88e54-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="88e54-178">Você deve primeiro remover a associação com o site de rede antes de excluir o perfil.</span><span class="sxs-lookup"><span data-stu-id="88e54-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="88e54-179">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="88e54-179">See Also</span></span>

[<span data-ttu-id="88e54-180">Gerenciando o controle de admissão de chamada para sites</span><span class="sxs-lookup"><span data-stu-id="88e54-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="88e54-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="88e54-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="88e54-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="88e54-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="88e54-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="88e54-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="88e54-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="88e54-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

