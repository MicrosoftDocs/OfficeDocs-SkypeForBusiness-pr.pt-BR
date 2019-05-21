---
title: Gerenciando regiões de rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Região de rede * são os hubs de rede ou backbones usados na configuração de controle de admissão de chamadas, E9-1-1 e bypass de mídia.
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279526"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="f2b52-103">Gerenciar regiões de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f2b52-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="f2b52-104">*Regiões de rede* são os hubs de rede ou backbones usados na configuração de controle de admissão de chamadas, E9-1-1 e bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="f2b52-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="f2b52-105">Use os procedimentos a seguir para exibir, criar ou modificar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="f2b52-106">Por exemplo, se você já tiver criado regiões de rede para um recurso de voz, não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usarão essas mesmas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="f2b52-107">No entanto, pode ser necessário modificar uma definição de região da rede existente para aplicar as configurações específicas do recurso.</span><span class="sxs-lookup"><span data-stu-id="f2b52-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="f2b52-108">Por exemplo, se você cria regiões da rede para o E9-1-1 (que não exige um local central associado) e depois implanta o serviço de controle de admissão de chamadas, precisará modificar as definições de região da rede para especificar um local central.</span><span class="sxs-lookup"><span data-stu-id="f2b52-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="f2b52-109">Use os procedimentos deste artigo para exibir informações de região de rede ou criar, modificar ou excluir regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="f2b52-110">Exibir informações de região de rede</span><span class="sxs-lookup"><span data-stu-id="f2b52-110">View network region information</span></span> 


<span data-ttu-id="f2b52-111">Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="f2b52-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="f2b52-112">Todas as regiões de rede devem estar associadas a um site central.</span><span class="sxs-lookup"><span data-stu-id="f2b52-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="f2b52-113">O site central é o site do Data Center no qual o serviço de política de largura de banda do controle de admissão de chamadas (CAC) está em execução.</span><span class="sxs-lookup"><span data-stu-id="f2b52-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="f2b52-114">Você pode usar o painel de controle do Skype for Business Server para exibir regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="f2b52-115">As regiões de rede incluem configurações que determinam se caminhos alternativos pela Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="f2b52-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="f2b52-116">Use este tópico para exibir regiões de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="f2b52-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="f2b52-117">Para ver informações sobre uma região de rede com o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f2b52-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f2b52-118">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f2b52-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2b52-119">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2b52-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f2b52-120">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="f2b52-121">Na página **região** , clique na região que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="f2b52-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="f2b52-122">Você só pode exibir uma região de cada vez.</span><span class="sxs-lookup"><span data-stu-id="f2b52-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="f2b52-123">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f2b52-124">Exibir informações de região de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2b52-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f2b52-125">Você pode exibir informações de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="f2b52-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="f2b52-126">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2b52-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="f2b52-127">Para ver as informações da região de rede</span><span class="sxs-lookup"><span data-stu-id="f2b52-127">To view network region information</span></span>

  - <span data-ttu-id="f2b52-128">Para ver as informações sobre todas as suas regiões de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="f2b52-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="f2b52-129">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="f2b52-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="f2b52-130">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="f2b52-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="f2b52-131">Criar ou modificar regiões de rede</span><span class="sxs-lookup"><span data-stu-id="f2b52-131">Create or modify network regions</span></span> 

<span data-ttu-id="f2b52-132">Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="f2b52-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="f2b52-133">Todas as regiões de rede devem estar associadas a um site central.</span><span class="sxs-lookup"><span data-stu-id="f2b52-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="f2b52-134">O site central é o site do Data Center no qual o serviço de política de largura de banda do controle de admissão de chamadas (CAC) está em execução.</span><span class="sxs-lookup"><span data-stu-id="f2b52-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="f2b52-135">Você pode usar o painel de controle do Skype for Business Server para configurar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="f2b52-136">As regiões de rede incluem configurações que determinam se caminhos alternativos pela Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="f2b52-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="f2b52-137">No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="f2b52-138">Use este tópico para criar e modificar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="f2b52-139">Para criar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="f2b52-139">To create a network region</span></span>

1.  <span data-ttu-id="f2b52-140">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f2b52-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2b52-141">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2b52-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f2b52-142">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="f2b52-143">Na página **região** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="f2b52-144">Na página **nova região** , digite um valor no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="f2b52-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="f2b52-145">Esse valor deve ser exclusivo na implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2b52-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="f2b52-146">Na lista suspensa **site central** , selecione o site central para esta região de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="f2b52-147">A caixa de seleção **habilitar caminho alternativo de áudio** está marcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="f2b52-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="f2b52-148">Esse campo determina se as chamadas de áudio serão roteadas por meio de um caminho alternativo se a largura de banda adequada não existir no caminho principal.</span><span class="sxs-lookup"><span data-stu-id="f2b52-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="f2b52-149">Desmarque essa caixa de seleção apenas se precisar desativar o Offload para a Internet.</span><span class="sxs-lookup"><span data-stu-id="f2b52-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="f2b52-150">Se qualquer uma de suas chamadas for chamada pela Internet, essa caixa de seleção deve ser marcada, independentemente das configurações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="f2b52-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="f2b52-151">A caixa de seleção **habilitar caminho alternativo de vídeo** está marcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="f2b52-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="f2b52-152">Esse campo determina se as chamadas com vídeo serão roteadas por meio de um caminho alternativo se a largura de banda adequada não existir no caminho principal.</span><span class="sxs-lookup"><span data-stu-id="f2b52-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="f2b52-153">Desmarque essa caixa de seleção apenas se precisar desativar o Offload para a Internet.</span><span class="sxs-lookup"><span data-stu-id="f2b52-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="f2b52-154">Se qualquer uma de suas chamadas for chamada pela Internet, essa caixa de seleção deve ser marcada, independentemente das configurações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="f2b52-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="f2b52-155">Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre essa região que não pode ser expressa apenas pelo nome.</span><span class="sxs-lookup"><span data-stu-id="f2b52-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="f2b52-156">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-156">Click **Commit**.</span></span>

<span data-ttu-id="f2b52-157">A tabela de **sites associados** não é usada para criar uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="f2b52-158">Você associa um site com uma região quando cria ou modifica o site.</span><span class="sxs-lookup"><span data-stu-id="f2b52-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="f2b52-159">Para obter detalhes, consulte Gerenciando o [controle de admissão de chamadas para sites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="f2b52-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="f2b52-160">Para modificar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="f2b52-160">To modify a network region</span></span>

1.  <span data-ttu-id="f2b52-161">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f2b52-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2b52-162">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2b52-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f2b52-163">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="f2b52-164">Na página **região** , clique na região que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="f2b52-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="f2b52-165">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f2b52-166">Na página **Editar região** , você pode modificar as configurações para habilitar e desabilitar caminhos alternativos de áudio e vídeo e alterar a descrição (para obter detalhes, consulte a seção "para criar uma região de rede" anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f2b52-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="f2b52-167">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-167">Click **Commit**.</span></span>

<span data-ttu-id="f2b52-168">Não é possível modificar os **sites associados** nesta página.</span><span class="sxs-lookup"><span data-stu-id="f2b52-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="f2b52-169">A lista de sites associados é fornecida para referência para que você saiba quais sites serão afetados quando você modificar as configurações de região.</span><span class="sxs-lookup"><span data-stu-id="f2b52-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="f2b52-170">Excluir regiões de rede existentes</span><span class="sxs-lookup"><span data-stu-id="f2b52-170">Delete existing network regions</span></span> 

<span data-ttu-id="f2b52-171">Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="f2b52-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="f2b52-172">Todas as regiões de rede devem estar associadas a um site central.</span><span class="sxs-lookup"><span data-stu-id="f2b52-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="f2b52-173">O site central é o site do Data Center no qual o serviço de política de largura de banda do controle de admissão de chamadas (CAC) está em execução.</span><span class="sxs-lookup"><span data-stu-id="f2b52-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="f2b52-174">Você pode usar o painel de controle do Skype for Business Server para configurar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="f2b52-175">As regiões de rede incluem configurações que determinam se caminhos alternativos pela Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="f2b52-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="f2b52-176">No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="f2b52-177">Use este tópico para excluir regiões de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="f2b52-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="f2b52-178">Para excluir uma região de rede</span><span class="sxs-lookup"><span data-stu-id="f2b52-178">To delete a network region</span></span>

1.  <span data-ttu-id="f2b52-179">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f2b52-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2b52-180">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2b52-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f2b52-181">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="f2b52-182">Na página **região** , clique na região que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="f2b52-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="f2b52-183">Você pode excluir mais de uma região de cada vez.</span><span class="sxs-lookup"><span data-stu-id="f2b52-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="f2b52-184">Para fazer isso, pressione CTRL e selecione várias regiões enquanto mantém a tecla CTRL pressionada.</span><span class="sxs-lookup"><span data-stu-id="f2b52-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="f2b52-185">Ou, para selecionar todas as regiões, clique em **selecionar tudo** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f2b52-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="f2b52-186">No menu **Editar** , clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="f2b52-187">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2b52-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="f2b52-188">Uma região de rede não poderá ser removida se estiver associada a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="f2b52-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="f2b52-189">Se você tentar remover uma região associada a um site, uma mensagem de erro será exibida.</span><span class="sxs-lookup"><span data-stu-id="f2b52-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="f2b52-190">Para ver se uma região está associada a qualquer site, selecione a região e clique em **Mostrar detalhes** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f2b52-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="f2b52-191">Confira também</span><span class="sxs-lookup"><span data-stu-id="f2b52-191">See Also</span></span>

[<span data-ttu-id="f2b52-192">Gerenciando rotas de região de rede</span><span class="sxs-lookup"><span data-stu-id="f2b52-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="f2b52-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f2b52-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="f2b52-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f2b52-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="f2b52-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f2b52-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="f2b52-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f2b52-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
