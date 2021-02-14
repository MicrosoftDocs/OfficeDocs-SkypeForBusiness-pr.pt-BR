---
title: Criar links de região de rede no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Criar ou modificar links de região de rede, que são usados pelo controle de admissão de chamada do Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 1b891a299e85836e4a69b4a6c6e9df9a52cb0cdc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822461"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="c2927-103">Criar links de região de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c2927-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="c2927-104">Criar ou modificar links de região de rede, que são usados pelo controle de admissão de chamada do Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2927-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="c2927-105">As regiões dentro de uma rede são vinculadas por meio da conectividade Wan.</span><span class="sxs-lookup"><span data-stu-id="c2927-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="c2927-106">Um link de região de rede cria um link entre duas regiões configuradas para o Controle de Admissão de Chamada (CAC) e define as limitações de largura de banda no tráfego de áudio e vídeo entre essas regiões.</span><span class="sxs-lookup"><span data-stu-id="c2927-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="c2927-107">A topologia de exemplo possui um link entre as regiões da América do Norte e APAC e um link entre as regiões EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="c2927-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="c2927-108">Cada um desses links de região é restringido pela largura de banda WAN, conforme descrito na tabela de Informações de Largura de Banda do Link de Região no Exemplo: Coletando requisitos para o controle de admissão de chamadas no [Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="c2927-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c2927-109">Para criar links de região de rede usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c2927-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c2927-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="c2927-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c2927-111">Execute o cmdlet New-CsNetworkRegionLink para criar os links de região e aplicar os perfis da política de largura de banda adequados.</span><span class="sxs-lookup"><span data-stu-id="c2927-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="c2927-112">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="c2927-112">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c2927-113">Para criar links de região de rede usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c2927-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c2927-114">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2927-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="c2927-115">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="c2927-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="c2927-116">Clique no botão de navegação **Link de região**.</span><span class="sxs-lookup"><span data-stu-id="c2927-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="c2927-117">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c2927-117">Click **New**.</span></span>
    
5. <span data-ttu-id="c2927-118">Na página **Novo link de região**, clique em **Nome** e digite um nome para o link de região de rede.</span><span class="sxs-lookup"><span data-stu-id="c2927-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="c2927-119">Clique em **Região de rede 1** e clique na região de rede da lista que deseja vincular para a Região de rede 2.</span><span class="sxs-lookup"><span data-stu-id="c2927-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="c2927-120">Clique em **Região de rede 2** e clique na região de rede da lista que deseja vincular para a Região de rede 1.</span><span class="sxs-lookup"><span data-stu-id="c2927-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="c2927-121">Opcionalmente, clique em **Política da largura de banda** e selecione o perfil da política de largura de banda que deseja aplicar para o link de região de rede.</span><span class="sxs-lookup"><span data-stu-id="c2927-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c2927-122">Aplique uma política de largura de banda apenas se o link de região de rede é restrito por largura de banda e se deseja usar o CAC para controlar o tráfego de mídia naquele link.</span><span class="sxs-lookup"><span data-stu-id="c2927-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="c2927-123">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c2927-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="c2927-124">Para finalizar a criação de links de região de rede para sua topologia, repita as etapas 4 a 9 com as configurações de outras regiões.</span><span class="sxs-lookup"><span data-stu-id="c2927-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c2927-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="c2927-125">See also</span></span>

[<span data-ttu-id="c2927-126">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="c2927-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="c2927-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="c2927-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="c2927-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="c2927-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="c2927-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="c2927-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
