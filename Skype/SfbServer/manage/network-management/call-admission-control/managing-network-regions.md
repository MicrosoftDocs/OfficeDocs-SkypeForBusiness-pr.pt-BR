---
title: Gerenciando regiões de rede
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
description: Região de rede* são os hubs de rede ou backbones usados na configuração do controle de admissão de chamada, E9-1-1 e bypass de mídia.
ms.openlocfilehash: 14c8004ddd14c0a37c25d700edae845ac9adfe29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816411"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="eaa58-103">Gerenciando regiões de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eaa58-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="eaa58-104">*Regiões de rede* são hubs de rede ou backbones usados na configuração do serviço de controle de admissão de chamadas, E9-1-1 e desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="eaa58-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="eaa58-105">Use os procedimentos a seguir para visualizar, criar ou modificar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="eaa58-106">Por exemplo, se você já criou regiões de rede para um recurso de Voz, não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usarão essas mesmas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="eaa58-107">Porém, talvez seja necessário modificar uma definição de região de rede existente para aplicar configurações específicas ao recurso.</span><span class="sxs-lookup"><span data-stu-id="eaa58-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="eaa58-108">Por exemplo, se você cria regiões de rede para o E9-1-1 (que não exige um local central associado) e depois implanta o controle de admissão de chamadas, precisará modificar as definições de região de rede para especificar um local central.</span><span class="sxs-lookup"><span data-stu-id="eaa58-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="eaa58-109">Use os procedimentos neste artigo para exibir informações de região de rede ou criar, modificar ou excluir regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="eaa58-110">Exibir informações de região de rede</span><span class="sxs-lookup"><span data-stu-id="eaa58-110">View network region information</span></span> 


<span data-ttu-id="eaa58-111">Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="eaa58-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="eaa58-112">Cada região de rede deve ser associada com um local central.</span><span class="sxs-lookup"><span data-stu-id="eaa58-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="eaa58-113">O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando.</span><span class="sxs-lookup"><span data-stu-id="eaa58-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="eaa58-114">Você pode usar o Painel de Controle do Skype for Business Server para exibir regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="eaa58-115">As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="eaa58-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="eaa58-116">Use este tópico para exibir regiões de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="eaa58-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="eaa58-117">Para exibir informações sobre uma região de rede com o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eaa58-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="eaa58-118">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="eaa58-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eaa58-119">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eaa58-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="eaa58-120">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Região.**</span><span class="sxs-lookup"><span data-stu-id="eaa58-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="eaa58-121">Na página **Região,** clique na região que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="eaa58-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="eaa58-122">Você só pode exibir uma região por vez.</span><span class="sxs-lookup"><span data-stu-id="eaa58-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="eaa58-123">No painel **Ações**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="eaa58-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="eaa58-124">Exibindo informações de região de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eaa58-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="eaa58-125">Você pode exibir informações de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegion.**</span><span class="sxs-lookup"><span data-stu-id="eaa58-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="eaa58-126">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eaa58-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="eaa58-127">Para exibir informações de região de rede</span><span class="sxs-lookup"><span data-stu-id="eaa58-127">To view network region information</span></span>

  - <span data-ttu-id="eaa58-128">Para exibir informações sobre todas as regiões de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="eaa58-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="eaa58-129">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="eaa58-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="eaa58-130">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)</span><span class="sxs-lookup"><span data-stu-id="eaa58-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="eaa58-131">Criar ou modificar regiões de rede</span><span class="sxs-lookup"><span data-stu-id="eaa58-131">Create or modify network regions</span></span> 

<span data-ttu-id="eaa58-132">Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="eaa58-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="eaa58-133">Cada região de rede deve ser associada com um local central.</span><span class="sxs-lookup"><span data-stu-id="eaa58-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="eaa58-134">O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando.</span><span class="sxs-lookup"><span data-stu-id="eaa58-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="eaa58-135">Você pode usar o Painel de Controle do Skype for Business Server para configurar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="eaa58-136">As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="eaa58-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="eaa58-137">No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="eaa58-138">Use este tópico para criar e modificar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="eaa58-139">Para criar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="eaa58-139">To create a network region</span></span>

1.  <span data-ttu-id="eaa58-140">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="eaa58-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eaa58-141">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eaa58-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="eaa58-142">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Região.**</span><span class="sxs-lookup"><span data-stu-id="eaa58-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="eaa58-143">Na página **Região**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="eaa58-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="eaa58-144">Na página **Nova Região**, digite um valor no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="eaa58-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="eaa58-145">Esse valor deve ser exclusivo em sua implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eaa58-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="eaa58-146">Na lista suspensa **Site central**, selecione o site central para essa região de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="eaa58-p106">A caixa de seleção **Habilitar caminho alternativo do áudio** está marcada por padrão. Esse campo determina se as chamadas de áudio serão roteadas por um caminho alternativo, caso a largura de banda adequada não exista no caminho primário. Desmarque essa caixa de seleção somente se precisar desativar o descarregamento para a Internet. Se qualquer uma de suas chamadas for uma chamada pela Internet, essa caixa de seleção deverá ser marcada, independente das configurações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="eaa58-p106">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="eaa58-p107">A caixa de seleção **Habilitar caminho alternativo do vídeo** está marcada por padrão. Esse campo determina se as chamadas de vídeo serão roteadas por um caminho alternativo, caso a largura de banda adequada não exista no caminho primário. Desmarque essa caixa de seleção somente se precisar desativar o descarregamento para a Internet. Se qualquer uma de suas chamadas for uma chamada pela Internet, essa caixa de seleção deverá ser marcada, independente das configurações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="eaa58-p107">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="eaa58-155">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre essa região que não podem ser expressas somente pelo nome.</span><span class="sxs-lookup"><span data-stu-id="eaa58-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="eaa58-156">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eaa58-156">Click **Commit**.</span></span>

<span data-ttu-id="eaa58-157">A tabela **Sites associados** não é usada para criar uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="eaa58-158">Você associa um site a uma região quando cria ou modifica o site.</span><span class="sxs-lookup"><span data-stu-id="eaa58-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="eaa58-159">Para obter detalhes, consulte [Gerenciando o controle de admissão de chamada para sites.](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="eaa58-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="eaa58-160">Para modificar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="eaa58-160">To modify a network region</span></span>

1.  <span data-ttu-id="eaa58-161">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="eaa58-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eaa58-162">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eaa58-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="eaa58-163">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Região.**</span><span class="sxs-lookup"><span data-stu-id="eaa58-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="eaa58-164">Na página **Região**, clique na região que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="eaa58-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="eaa58-165">No menu **Editar**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="eaa58-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="eaa58-166">Na página **Editar Região**, é possível modificar as configurações para habilitar e desabilitar caminhos alternativos de áudio e vídeo e alterar a descrição (para obter detalhes, consulte a seção "Para criar uma região de rede" acima neste tópico.</span><span class="sxs-lookup"><span data-stu-id="eaa58-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="eaa58-167">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eaa58-167">Click **Commit**.</span></span>

<span data-ttu-id="eaa58-p109">Não é possível modificar os **Sites associados** nesta página. A lista de sites associados é fornecida para referência de modo que você fique ciente de quais sites serão afetados quando você modificar as configurações de região.</span><span class="sxs-lookup"><span data-stu-id="eaa58-p109">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="eaa58-170">Excluir regiões de rede existentes</span><span class="sxs-lookup"><span data-stu-id="eaa58-170">Delete existing network regions</span></span> 

<span data-ttu-id="eaa58-171">Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="eaa58-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="eaa58-172">Cada região de rede deve ser associada com um local central.</span><span class="sxs-lookup"><span data-stu-id="eaa58-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="eaa58-173">O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando.</span><span class="sxs-lookup"><span data-stu-id="eaa58-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="eaa58-174">Você pode usar o Painel de Controle do Skype for Business Server para configurar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="eaa58-175">As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="eaa58-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="eaa58-176">No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="eaa58-177">Use este tópico para excluir regiões de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="eaa58-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="eaa58-178">Para excluir uma região de rede</span><span class="sxs-lookup"><span data-stu-id="eaa58-178">To delete a network region</span></span>

1.  <span data-ttu-id="eaa58-179">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="eaa58-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eaa58-180">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eaa58-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="eaa58-181">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Região.**</span><span class="sxs-lookup"><span data-stu-id="eaa58-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="eaa58-182">Na página **Região**, clique na região que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="eaa58-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="eaa58-p111">É possível excluir mais de uma região por vez. Para fazer isso, pressione CTRL e selecione várias regiões enquanto mantém pressionada a tecla CTRL. Ou, para selecionar todas as regiões, clique em **Selecionar tudo** no menu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="eaa58-p111">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="eaa58-186">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="eaa58-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="eaa58-187">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="eaa58-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="eaa58-188">Uma região de rede não pode ser removida se estiver associada a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="eaa58-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="eaa58-189">Se você tentar remover uma região associada a um site, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="eaa58-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="eaa58-190">Para ver se um região está associada a algum site, selecione a região e clique em **Mostrar detalhes** no menu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="eaa58-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="eaa58-191">Confira também</span><span class="sxs-lookup"><span data-stu-id="eaa58-191">See Also</span></span>

[<span data-ttu-id="eaa58-192">Gerenciando rotas de região de rede</span><span class="sxs-lookup"><span data-stu-id="eaa58-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="eaa58-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="eaa58-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="eaa58-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="eaa58-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="eaa58-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="eaa58-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="eaa58-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="eaa58-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
