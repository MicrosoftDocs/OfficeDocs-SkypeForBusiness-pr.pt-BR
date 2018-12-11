---
title: Gerenciando as regiões de rede
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Região de rede * são os hubs de rede ou o backbones usados na configuração do bypass de mídia, E9-1-1 e controle de admissão chamada.
ms.openlocfilehash: 3fe6707e6949fa47a9cc5e96703e06132ed8cb2f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223308"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="e5668-103">Gerenciando regiões de rede Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e5668-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="e5668-104">*Regiões de rede* são os hubs de rede ou o backbones usados na configuração do bypass de mídia, E9-1-1 e controle de admissão chamada.</span><span class="sxs-lookup"><span data-stu-id="e5668-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="e5668-105">Use os procedimentos a seguir para exibir, criar ou modificar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="e5668-106">Por exemplo, se você já criou regiões de rede para um recurso de voz, você não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usará esses mesmos regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="e5668-107">No entanto, pode ser necessário modificar uma definição de região da rede existente para aplicar as configurações específicas do recurso.</span><span class="sxs-lookup"><span data-stu-id="e5668-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="e5668-108">Por exemplo, se você cria regiões da rede para o E9-1-1 (que não exige um local central associado) e depois implanta o serviço de controle de admissão de chamadas, precisará modificar as definições de região da rede para especificar um local central.</span><span class="sxs-lookup"><span data-stu-id="e5668-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="e5668-109">Use os procedimentos neste artigo para exibir informações de região de rede ou criar, modificar ou excluir as regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="e5668-110">Exibir informações de região de rede</span><span class="sxs-lookup"><span data-stu-id="e5668-110">View network region information</span></span> 


<span data-ttu-id="e5668-111">Uma região de rede interconexão várias partes de uma rede de várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="e5668-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e5668-112">Cada região de rede deve ser associado um site central.</span><span class="sxs-lookup"><span data-stu-id="e5668-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="e5668-113">O site central é o site do Centro de dados no qual o serviço de política de largura de banda do chamada admissão CAC (controle) é executado.</span><span class="sxs-lookup"><span data-stu-id="e5668-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="e5668-114">Você pode usar o Skype para painel de controle do Business Server para exibir as regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="e5668-115">Regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet, são permitidos conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e5668-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="e5668-116">Use este tópico para exibir as regiões de rede existente.</span><span class="sxs-lookup"><span data-stu-id="e5668-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="e5668-117">Para exibir informações sobre uma região de rede com Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="e5668-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="e5668-118">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e5668-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5668-119">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e5668-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e5668-120">Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="e5668-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="e5668-121">Na página **região** , clique na região que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="e5668-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="e5668-122">Você pode exibir apenas uma região por vez.</span><span class="sxs-lookup"><span data-stu-id="e5668-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="e5668-123">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e5668-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e5668-124">Visualizando informações de região de rede usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5668-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="e5668-125">Você pode exibir informações de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="e5668-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="e5668-126">Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5668-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="e5668-127">Para exibir informações de região de rede</span><span class="sxs-lookup"><span data-stu-id="e5668-127">To view network region information</span></span>

  - <span data-ttu-id="e5668-128">Para exibir informações sobre todas as regiões de rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="e5668-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="e5668-129">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="e5668-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="e5668-130">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="e5668-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="e5668-131">Criar ou modificar regiões de rede</span><span class="sxs-lookup"><span data-stu-id="e5668-131">Create or modify network regions</span></span> 

<span data-ttu-id="e5668-132">Uma região de rede interconexão várias partes de uma rede de várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="e5668-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e5668-133">Cada região de rede deve ser associado um site central.</span><span class="sxs-lookup"><span data-stu-id="e5668-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="e5668-134">O site central é o site do Centro de dados no qual o serviço de política de largura de banda do chamada admissão CAC (controle) é executado.</span><span class="sxs-lookup"><span data-stu-id="e5668-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="e5668-135">Você pode usar o Skype para painel de controle do Business Server para configurar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="e5668-136">Regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet, são permitidos conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e5668-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="e5668-137">Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="e5668-138">Use este tópico para criar e modificar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="e5668-139">Para criar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="e5668-139">To create a network region</span></span>

1.  <span data-ttu-id="e5668-140">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e5668-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5668-141">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e5668-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e5668-142">Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="e5668-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="e5668-143">Na página **região** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="e5668-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="e5668-144">Na página **Nova região** , digite um valor no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="e5668-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="e5668-145">Este valor deve ser exclusivo dentro de sua Skype para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e5668-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="e5668-146">Na lista suspensa **site Central** , selecione o site central para essa região de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="e5668-147">A caixa de seleção **Habilitar áudio caminho alternativo** está marcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="e5668-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="e5668-148">Esse campo determina se chamadas de áudio serão roteadas por um caminho alternativo se não existir largura de banda adequada no caminho primário.</span><span class="sxs-lookup"><span data-stu-id="e5668-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="e5668-149">Desmarque essa caixa de seleção somente se você precisar desativar a descarga para a Internet.</span><span class="sxs-lookup"><span data-stu-id="e5668-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="e5668-150">Se qualquer uma das suas chamadas serão chamadas pela Internet, esta caixa de seleção deve ser verificado, independentemente das configurações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="e5668-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="e5668-151">A caixa de seleção **Habilitar vídeo caminho alternativo** está marcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="e5668-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="e5668-152">Esse campo determina se chamadas de vídeo serão roteadas por um caminho alternativo se não existir largura de banda adequada no caminho primário.</span><span class="sxs-lookup"><span data-stu-id="e5668-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="e5668-153">Desmarque essa caixa de seleção somente se você precisar desativar a descarga para a Internet.</span><span class="sxs-lookup"><span data-stu-id="e5668-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="e5668-154">Se qualquer uma das suas chamadas serão chamadas pela Internet, esta caixa de seleção deve ser verificado, independentemente das configurações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="e5668-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="e5668-155">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre essa região que não pode ser expressa somente pelo nome.</span><span class="sxs-lookup"><span data-stu-id="e5668-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="e5668-156">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e5668-156">Click **Commit**.</span></span>

<span data-ttu-id="e5668-157">A tabela de **sites associado** não é usada para criar uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="e5668-158">Você associa um site com uma região quando você cria ou modifica o site.</span><span class="sxs-lookup"><span data-stu-id="e5668-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="e5668-159">Para obter detalhes, consulte [Gerenciando o controle de admissão de chamada para sites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="e5668-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="e5668-160">Para modificar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="e5668-160">To modify a network region</span></span>

1.  <span data-ttu-id="e5668-161">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e5668-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5668-162">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e5668-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e5668-163">Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="e5668-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="e5668-164">Na página **região** , clique na região que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="e5668-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="e5668-165">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e5668-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e5668-166">Na página **Editar região** , você pode modificar as configurações para habilitar e desabilitar áudio e vídeo alternam caminhos e alterar a descrição (para obter detalhes, consulte a seção "para criar uma região de rede" anteriormente contidas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e5668-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="e5668-167">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e5668-167">Click **Commit**.</span></span>

<span data-ttu-id="e5668-168">Você não pode modificar os **sites associado** nesta página.</span><span class="sxs-lookup"><span data-stu-id="e5668-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="e5668-169">A lista de sites associados é fornecida para referência, portanto você está ciente de que os sites que serão afetados quando você modifica as configurações de região.</span><span class="sxs-lookup"><span data-stu-id="e5668-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="e5668-170">Excluir as regiões de rede existente</span><span class="sxs-lookup"><span data-stu-id="e5668-170">Delete existing network regions</span></span> 

<span data-ttu-id="e5668-171">Uma região de rede interconexão várias partes de uma rede de várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="e5668-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e5668-172">Cada região de rede deve ser associado um site central.</span><span class="sxs-lookup"><span data-stu-id="e5668-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="e5668-173">O site central é o site do Centro de dados no qual o serviço de política de largura de banda do chamada admissão CAC (controle) é executado.</span><span class="sxs-lookup"><span data-stu-id="e5668-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="e5668-174">Você pode usar o Skype para painel de controle do Business Server para configurar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="e5668-175">Regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet, são permitidos conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e5668-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="e5668-176">Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="e5668-177">Use este tópico para excluir as regiões de rede existente.</span><span class="sxs-lookup"><span data-stu-id="e5668-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="e5668-178">Para excluir uma região de rede</span><span class="sxs-lookup"><span data-stu-id="e5668-178">To delete a network region</span></span>

1.  <span data-ttu-id="e5668-179">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e5668-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5668-180">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e5668-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e5668-181">Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="e5668-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="e5668-182">Na página **região** , clique na região que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="e5668-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="e5668-183">Você pode excluir mais de uma região por vez.</span><span class="sxs-lookup"><span data-stu-id="e5668-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="e5668-184">Para fazer isso, pressione CTRL e selecione várias regiões, mantendo pressionada a tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="e5668-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="e5668-185">Ou, para selecionar todas as regiões, clique em **Selecionar tudo** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="e5668-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="e5668-186">No menu **Editar** , clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="e5668-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="e5668-187">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5668-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="e5668-188">Uma região de rede não pode ser removida se estiver associada a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="e5668-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="e5668-189">Se você tentar remover uma região associada a um site, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="e5668-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="e5668-190">Para ver se uma região é associada a todos os sites, selecione a região e clique em **Mostrar detalhes** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="e5668-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="e5668-191">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5668-191">See Also</span></span>

[<span data-ttu-id="e5668-192">Gerenciando rotas de região de rede</span><span class="sxs-lookup"><span data-stu-id="e5668-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="e5668-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e5668-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="e5668-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e5668-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="e5668-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e5668-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="e5668-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e5668-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  