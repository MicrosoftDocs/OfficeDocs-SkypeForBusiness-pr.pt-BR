---
title: Gerenciando perfis de política de largura de banda de rede
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
description: Use os procedimentos deste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816441"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="85084-103">Gerenciando perfis de política de largura de banda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="85084-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="85084-104">Use os procedimentos deste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.</span><span class="sxs-lookup"><span data-stu-id="85084-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="85084-105">Exibir informações de perfil de política de largura de banda de rede</span><span class="sxs-lookup"><span data-stu-id="85084-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="85084-106">Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades.</span><span class="sxs-lookup"><span data-stu-id="85084-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="85084-107">No Skype for Business Server, apenas as modalidades de áudio e vídeo podem ter limitações de largura de banda atribuídas.</span><span class="sxs-lookup"><span data-stu-id="85084-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="85084-108">Você pode configurar os limites gerais de banda e os limites de sessão.</span><span class="sxs-lookup"><span data-stu-id="85084-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="85084-109">Você pode usar o Painel de Controle do Skype for Business Server para criar, modificar ou excluir um perfil de contêiner para essas políticas.</span><span class="sxs-lookup"><span data-stu-id="85084-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="85084-110">Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede.</span><span class="sxs-lookup"><span data-stu-id="85084-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="85084-111">Use os procedimentos a seguir para exibir um perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="85084-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="85084-112">Para exibir um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="85084-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="85084-113">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="85084-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85084-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85084-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="85084-115">Na barra de navegação à esquerda, clique em **Configuração de rede** e, em seguida, clique em **Política de largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="85084-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="85084-116">Na página Política **de Largura de** Banda, clique no perfil de política de largura de banda que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="85084-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="85084-117">No painel **Ações**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="85084-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="85084-118">Exibindo informações de perfil de política de largura de banda de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85084-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="85084-119">Os perfis de largura de banda de rede podem ser exibidos usando o Windows PowerShell e o Get-CsNetworkBandwidthPolicyProfile cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85084-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="85084-120">Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85084-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="85084-121">Para exibir informações de perfil de política de largura de banda de rede</span><span class="sxs-lookup"><span data-stu-id="85084-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="85084-122">Para exibir informações sobre todos os perfis de política de largura de banda de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="85084-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="85084-123">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="85084-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="85084-124">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkBandwidthPolicyProfile.](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)</span><span class="sxs-lookup"><span data-stu-id="85084-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="85084-125">Criar ou modificar perfis de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="85084-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="85084-126">Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades.</span><span class="sxs-lookup"><span data-stu-id="85084-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="85084-127">No Skype for Business Server, apenas as modalidades de áudio e vídeo podem ter limitações de largura de banda atribuídas.</span><span class="sxs-lookup"><span data-stu-id="85084-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="85084-128">Você pode configurar os limites gerais de banda e os limites de sessão.</span><span class="sxs-lookup"><span data-stu-id="85084-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="85084-129">Você pode usar o Painel de Controle do Skype for Business Server para criar, modificar ou excluir um perfil de contêiner para essas políticas.</span><span class="sxs-lookup"><span data-stu-id="85084-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="85084-130">Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede.</span><span class="sxs-lookup"><span data-stu-id="85084-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="85084-131">Use os procedimentos a seguir para criar ou modificar um perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="85084-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="85084-132">Para criar um novo perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="85084-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="85084-133">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="85084-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85084-134">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85084-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="85084-135">Na barra de navegação esquerda, clique em **Configuração de** Rede e em Política **de Largura de Banda.**</span><span class="sxs-lookup"><span data-stu-id="85084-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="85084-136">Na página **Política de largura de banda**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="85084-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="85084-p104">Em **Novo Perfil de Política de Largura de Banda**, digite um nome no campo **Nome**. Esse nome deve ser único entre todos os perfis de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="85084-p104">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="85084-p105">No campo **Limite de áudio**, digite um valor numérico. Esse valor é a quantidade máxima de largura de banda a ser alocada a todas as conexões de áudio, expressa em kbps.</span><span class="sxs-lookup"><span data-stu-id="85084-p105">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="85084-p106">Insira um valor numérico no campo **Limite da sessão de áudio**. Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de áudio individual, expressa em kbps. Esse valor precisa ser igual a ou maior que 40.</span><span class="sxs-lookup"><span data-stu-id="85084-p106">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="85084-p107">Insira um valor numérico no campo **Limite de vídeo**. Esse valor é quantidade máxima de largura de banda a ser alocada para todas as conexões de vídeo, expressa em kbps.</span><span class="sxs-lookup"><span data-stu-id="85084-p107">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="85084-p108">Insira um valor numérico no campo **Limite de sessão de vídeo**. Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de vídeo individual, expressa em kbps. Esse valor precisa ser igual a ou maior que 100.</span><span class="sxs-lookup"><span data-stu-id="85084-p108">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="85084-149">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse perfil da política de largura de banda que não pode ser expressa somente pelo nome.</span><span class="sxs-lookup"><span data-stu-id="85084-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="85084-150">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="85084-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="85084-151">Criar um novo perfil de política de largura de banda não reforça as restrições de largura de banda automaticamente.</span><span class="sxs-lookup"><span data-stu-id="85084-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="85084-152">É preciso, primeiro, associar o perfil da política com um site.</span><span class="sxs-lookup"><span data-stu-id="85084-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="85084-153">Para modificar um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="85084-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="85084-154">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="85084-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85084-155">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85084-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="85084-156">Na barra de navegação esquerda, clique em **Configuração de** Rede e em Política **de Largura de Banda.**</span><span class="sxs-lookup"><span data-stu-id="85084-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="85084-157">Na página **Política de largura de banda**, clique no perfil da política de largura de banda que você quer modificar.</span><span class="sxs-lookup"><span data-stu-id="85084-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="85084-158">No menu **Editar**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="85084-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="85084-159">Na página **Editar Perfil de Política de** Largura de Banda, modifique os campos conforme necessário (para obter detalhes, consulte Para criar um novo perfil de política de largura de [banda).](#to-create-a-new-bandwidth-policy-profile)</span><span class="sxs-lookup"><span data-stu-id="85084-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="85084-160">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="85084-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="85084-161">Ao modificar o perfil de política de largura de banda, as limitações de largura de banda de todos os sites da rede associados a esse perfil serão atualizadas imediatamente.</span><span class="sxs-lookup"><span data-stu-id="85084-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="85084-162">Excluir perfis de política de largura de banda de rede</span><span class="sxs-lookup"><span data-stu-id="85084-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="85084-163">Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades.</span><span class="sxs-lookup"><span data-stu-id="85084-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="85084-164">No Skype for Business Server, apenas as modalidades de áudio e vídeo podem ter limitações de largura de banda atribuídas.</span><span class="sxs-lookup"><span data-stu-id="85084-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="85084-165">Você pode configurar os limites gerais de banda e os limites de sessão.</span><span class="sxs-lookup"><span data-stu-id="85084-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="85084-166">Você pode usar o Painel de Controle do Skype for Business Server para criar, modificar ou excluir um perfil de contêiner para essas políticas.</span><span class="sxs-lookup"><span data-stu-id="85084-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="85084-167">Use os seguintes procedimentos para excluir um perfil de política de largura de banda de rede.</span><span class="sxs-lookup"><span data-stu-id="85084-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="85084-168">Para excluir um perfil de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="85084-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="85084-169">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="85084-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85084-170">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85084-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="85084-171">Na barra de navegação esquerda, clique em **Configuração de** Rede e em Política **de Largura de Banda.**</span><span class="sxs-lookup"><span data-stu-id="85084-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="85084-172">Na página **Política de largura de banda**, clique no perfil de política de largura de banda que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="85084-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="85084-p111">Você pode excluir mais de um perfil por vez. Para isso, pressione CTRL e selecione vários perfis mantendo a tecla CTRL pressionada. Ou, para selecionar perfis, clique em **Selecionar tudo** no menu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="85084-p111">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="85084-176">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="85084-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="85084-177">Você não pode excluir um perfil de política de largura de banda que esteja associado a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="85084-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="85084-178">É preciso primeiro remover a associação com o site antes de poder excluir o perfil.</span><span class="sxs-lookup"><span data-stu-id="85084-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="85084-179">Confira também</span><span class="sxs-lookup"><span data-stu-id="85084-179">See Also</span></span>

[<span data-ttu-id="85084-180">Gerenciando o controle de admissão de chamada para sites</span><span class="sxs-lookup"><span data-stu-id="85084-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="85084-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="85084-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="85084-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="85084-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="85084-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="85084-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="85084-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="85084-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

