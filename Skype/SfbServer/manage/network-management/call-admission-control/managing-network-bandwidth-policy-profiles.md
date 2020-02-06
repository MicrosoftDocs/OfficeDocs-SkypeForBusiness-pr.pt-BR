---
title: Gerenciando perfis de política de largura de banda de rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Use os procedimentos deste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817500"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="69c74-103">Gerenciar perfis de política de largura de banda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="69c74-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="69c74-104">Use os procedimentos deste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.</span><span class="sxs-lookup"><span data-stu-id="69c74-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="69c74-105">Exibir informações do perfil da política de largura de banda de rede</span><span class="sxs-lookup"><span data-stu-id="69c74-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="69c74-106">Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir limitações de largura de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="69c74-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="69c74-107">No Skype for Business Server, apenas as modalidades de áudio e de vídeo podem ter limitações de largura de banda atribuídas.</span><span class="sxs-lookup"><span data-stu-id="69c74-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="69c74-108">Você pode definir limitações gerais de largura de banda e limitações de sessão.</span><span class="sxs-lookup"><span data-stu-id="69c74-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="69c74-109">Você pode usar o painel de controle do Skype for Business Server para criar, modificar ou excluir um perfil de contêiner para essas políticas.</span><span class="sxs-lookup"><span data-stu-id="69c74-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="69c74-110">Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede.</span><span class="sxs-lookup"><span data-stu-id="69c74-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="69c74-111">Use os procedimentos a seguir para exibir um perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="69c74-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="69c74-112">Para exibir um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="69c74-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="69c74-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="69c74-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69c74-114">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="69c74-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="69c74-115">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, em política de **largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="69c74-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="69c74-116">Na página **política de largura de banda** , clique no perfil de política de largura de banda que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="69c74-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="69c74-117">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="69c74-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="69c74-118">Exibindo informações do perfil da política de largura de banda de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69c74-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="69c74-119">Os perfis de largura de banda de rede podem ser exibidos usando o Windows PowerShell e o cmdlet Get-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="69c74-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="69c74-120">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69c74-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="69c74-121">Para ver as informações do perfil da política de largura de banda de rede</span><span class="sxs-lookup"><span data-stu-id="69c74-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="69c74-122">Para ver informações sobre todos os perfis da política de largura de banda de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="69c74-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="69c74-123">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="69c74-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="69c74-124">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="69c74-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="69c74-125">Criar ou modificar perfis de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="69c74-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="69c74-126">Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir limitações de largura de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="69c74-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="69c74-127">No Skype for Business Server, apenas as modalidades de áudio e de vídeo podem ter limitações de largura de banda atribuídas.</span><span class="sxs-lookup"><span data-stu-id="69c74-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="69c74-128">Você pode definir limitações gerais de largura de banda e limitações de sessão.</span><span class="sxs-lookup"><span data-stu-id="69c74-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="69c74-129">Você pode usar o painel de controle do Skype for Business Server para criar, modificar ou excluir um perfil de contêiner para essas políticas.</span><span class="sxs-lookup"><span data-stu-id="69c74-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="69c74-130">Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede.</span><span class="sxs-lookup"><span data-stu-id="69c74-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="69c74-131">Use os procedimentos a seguir para criar ou modificar um perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="69c74-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="69c74-132">Para criar um novo perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="69c74-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="69c74-133">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="69c74-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69c74-134">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="69c74-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="69c74-135">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em política de **largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="69c74-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="69c74-136">Na página **política de largura de banda** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="69c74-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="69c74-137">Em **novo perfil de política de largura de banda**, digite um nome no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="69c74-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="69c74-138">Esse nome deve ser exclusivo entre todos os perfis de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="69c74-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="69c74-139">No campo **limite de áudio** , digite um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="69c74-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="69c74-140">Esse valor é a quantidade máxima de largura de banda a ser alocada para todas as conexões de áudio, expressa em Kbps.</span><span class="sxs-lookup"><span data-stu-id="69c74-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="69c74-141">Insira um valor numérico no campo **limite da sessão de áudio** .</span><span class="sxs-lookup"><span data-stu-id="69c74-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="69c74-142">Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de áudio individual, expressa em Kbps.</span><span class="sxs-lookup"><span data-stu-id="69c74-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="69c74-143">Esse valor deve ser 40 ou superior.</span><span class="sxs-lookup"><span data-stu-id="69c74-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="69c74-144">Insira um valor numérico no campo **limite de vídeo** .</span><span class="sxs-lookup"><span data-stu-id="69c74-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="69c74-145">Esse valor é a quantidade máxima de largura de banda a ser alocada para todas as conexões de vídeo, expressa em Kbps.</span><span class="sxs-lookup"><span data-stu-id="69c74-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="69c74-146">Insira um valor numérico no campo **limite da sessão de vídeo** .</span><span class="sxs-lookup"><span data-stu-id="69c74-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="69c74-147">Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de vídeo individual, expressa em Kbps.</span><span class="sxs-lookup"><span data-stu-id="69c74-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="69c74-148">Esse valor deve ser 100 ou superior.</span><span class="sxs-lookup"><span data-stu-id="69c74-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="69c74-149">Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre esse perfil de política de largura de banda que não pode ser expresso apenas com o nome.</span><span class="sxs-lookup"><span data-stu-id="69c74-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="69c74-150">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="69c74-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="69c74-151">A criação de um novo perfil de política de largura de banda não impõe automaticamente restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="69c74-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="69c74-152">Você deve primeiro associar o perfil de política a um site.</span><span class="sxs-lookup"><span data-stu-id="69c74-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="69c74-153">Para modificar um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="69c74-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="69c74-154">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="69c74-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69c74-155">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="69c74-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="69c74-156">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em política de **largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="69c74-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="69c74-157">Na página **política de largura de banda** , clique no perfil de política de largura de banda que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="69c74-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="69c74-158">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="69c74-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="69c74-159">Na página **Editar perfil da política de largura de banda** , modifique os campos conforme necessário (para obter detalhes, consulte [criar um novo perfil de política de largura de banda](#to-create-a-new-bandwidth-policy-profile)).</span><span class="sxs-lookup"><span data-stu-id="69c74-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="69c74-160">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="69c74-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="69c74-161">Quando você modifica o perfil da política de largura de banda, ele atualiza imediatamente as limitações de largura de banda de todos os sites de rede associados a este perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="69c74-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="69c74-162">Excluir perfis de política de largura de banda de rede</span><span class="sxs-lookup"><span data-stu-id="69c74-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="69c74-163">Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir limitações de largura de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="69c74-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="69c74-164">No Skype for Business Server, apenas as modalidades de áudio e de vídeo podem ter limitações de largura de banda atribuídas.</span><span class="sxs-lookup"><span data-stu-id="69c74-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="69c74-165">Você pode definir limitações gerais de largura de banda e limitações de sessão.</span><span class="sxs-lookup"><span data-stu-id="69c74-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="69c74-166">Você pode usar o painel de controle do Skype for Business Server para criar, modificar ou excluir um perfil de contêiner para essas políticas.</span><span class="sxs-lookup"><span data-stu-id="69c74-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="69c74-167">Use os procedimentos a seguir para excluir um perfil de política de largura de banda de rede.</span><span class="sxs-lookup"><span data-stu-id="69c74-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="69c74-168">Para excluir um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="69c74-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="69c74-169">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="69c74-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69c74-170">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="69c74-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="69c74-171">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em política de **largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="69c74-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="69c74-172">Na página **política de largura de banda** , clique no perfil de política de largura de banda que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="69c74-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="69c74-173">Você pode excluir mais de um perfil de cada vez.</span><span class="sxs-lookup"><span data-stu-id="69c74-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="69c74-174">Para fazer isso, pressione CTRL e selecione vários perfis enquanto mantém a tecla CTRL pressionada.</span><span class="sxs-lookup"><span data-stu-id="69c74-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="69c74-175">Ou, para selecionar todos os perfis, clique em **selecionar tudo** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="69c74-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="69c74-176">No menu **Editar** , clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="69c74-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="69c74-177">Não é possível excluir um perfil de política de largura de banda associado a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="69c74-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="69c74-178">Você deve primeiro remover a associação com o site de rede antes de poder excluir o perfil.</span><span class="sxs-lookup"><span data-stu-id="69c74-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="69c74-179">Confira também</span><span class="sxs-lookup"><span data-stu-id="69c74-179">See Also</span></span>

[<span data-ttu-id="69c74-180">Gerenciando o controle de admissão de chamadas para sites</span><span class="sxs-lookup"><span data-stu-id="69c74-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="69c74-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="69c74-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="69c74-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="69c74-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="69c74-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="69c74-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="69c74-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="69c74-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

