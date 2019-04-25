---
title: Criar links de região de rede no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Criar ou modificar os links de região de rede, que são usados pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server.
ms.openlocfilehash: 729b20010390bf0a8865adce96a398d362009552
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223357"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="4fd93-103">Criar links de região de rede no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4fd93-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="4fd93-104">Criar ou modificar os links de região de rede, que são usados pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="4fd93-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="4fd93-105">Regiões dentro de uma rede são vinculadas através de uma conectividade WAN física.</span><span class="sxs-lookup"><span data-stu-id="4fd93-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="4fd93-106">Um link de região de rede cria um link entre duas regiões configuradas para Controle de Admissão de Chamada (CAC) e define os limites da largura de banda em tráfego de áudio e vídeo entre essas regiões.</span><span class="sxs-lookup"><span data-stu-id="4fd93-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="4fd93-107">A topologia de exemplo possui um link entre as regiões da América do Norte e APAC e um link entre as regiões EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="4fd93-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="4fd93-108">Cada um desses links de região é restrito por largura de banda WAN, conforme descrito na tabela de informações de largura de banda do Link de região no [exemplo: coletando os requisitos para o controle de admissão de chamada no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fd93-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4fd93-109">Para criar links de região de rede usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="4fd93-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="4fd93-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="4fd93-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4fd93-111">Execute o cmdlet New-CsNetworkRegionLink para criar os links de região e aplicar os perfis da política de largura de banda adequados.</span><span class="sxs-lookup"><span data-stu-id="4fd93-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="4fd93-112">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="4fd93-112">For example, run:</span></span>
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4fd93-113">Para criar links de região de rede usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="4fd93-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="4fd93-114">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="4fd93-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="4fd93-115">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="4fd93-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="4fd93-116">Clique no botão de navegação **Link de região**.</span><span class="sxs-lookup"><span data-stu-id="4fd93-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="4fd93-117">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4fd93-117">Click **New**.</span></span>
    
5. <span data-ttu-id="4fd93-118">Na página **Novo link de região**, clique em **Nome** e digite um nome para o link de região de rede.</span><span class="sxs-lookup"><span data-stu-id="4fd93-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="4fd93-119">Clique em **Região de rede 1** e clique na região de rede da lista que deseja vincular para a Região de rede 2.</span><span class="sxs-lookup"><span data-stu-id="4fd93-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="4fd93-120">Clique em **Região de rede 2** e clique na região de rede da lista que deseja vincular para a Região de rede 1.</span><span class="sxs-lookup"><span data-stu-id="4fd93-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="4fd93-121">Opcionalmente, clique em **Política da largura de banda** e selecione o perfil da política de largura de banda que deseja aplicar para o link de região de rede.</span><span class="sxs-lookup"><span data-stu-id="4fd93-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4fd93-122">Aplique uma política de largura de banda apenas se o link de região de rede é restrito por largura de banda e se deseja usar o CAC para controlar o tráfego de mídia naquele link.</span><span class="sxs-lookup"><span data-stu-id="4fd93-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="4fd93-123">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4fd93-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="4fd93-124">Para finalizar a criação de links de região de rede para sua topologia, repita as etapas 4 a 9 com as configurações de outras regiões.</span><span class="sxs-lookup"><span data-stu-id="4fd93-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4fd93-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="4fd93-125">See also</span></span>

[<span data-ttu-id="4fd93-126">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4fd93-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="4fd93-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4fd93-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="4fd93-128">Set-CsNetworkRegionLink.</span><span class="sxs-lookup"><span data-stu-id="4fd93-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="4fd93-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4fd93-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
