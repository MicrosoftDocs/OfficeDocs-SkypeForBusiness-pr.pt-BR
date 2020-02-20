---
title: 'Lync Server 2013: criar links de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ff183fc79f6921f1952c3a9d0fa9cc2c818face
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="9ebde-102">Criar links de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ebde-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ebde-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9ebde-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9ebde-p101">Regiões dentro de uma rede são vinculadas através de uma conectividade WAN física. Um *link de região de rede* cria um link entre duas regiões configuradas para controle de admissão de chamada (CAC) e define os limites da largura de banda em tráfego de áudio e vídeo entre estas regiões.</span><span class="sxs-lookup"><span data-stu-id="9ebde-p101">Regions within a network are linked through physical WAN connectivity. A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="9ebde-106">Para obter detalhes sobre como trabalhar com links de região de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="9ebde-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="9ebde-107">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9ebde-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="9ebde-108">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9ebde-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="9ebde-109">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9ebde-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="9ebde-110">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9ebde-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="9ebde-111">A topologia de exemplo possui um link entre as regiões da América do Norte e APAC e um link entre as regiões EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="9ebde-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="9ebde-112">Cada um desses links de região é restrito pela largura de banda de WAN, conforme descrito na tabela informações de largura de banda de link de região no [exemplo: reunir seus requisitos para controle de admissão de chamadas na seção do Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) da documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="9ebde-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="9ebde-113">Para criar links de região de rede usando o Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="9ebde-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="9ebde-114">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9ebde-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9ebde-p103">Execute o cmdlet New-CsNetworkRegionLink para criar os links de região e aplicar os perfis da política de largura de banda adequados. Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="9ebde-p103">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles. For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="9ebde-117">Para criar links de região de rede usando o Painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="9ebde-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9ebde-118">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ebde-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ebde-119">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9ebde-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="9ebde-120">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="9ebde-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="9ebde-121">Clique no botão de navegação **Link de região**.</span><span class="sxs-lookup"><span data-stu-id="9ebde-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="9ebde-122">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9ebde-122">Click **New**.</span></span>

5.  <span data-ttu-id="9ebde-123">Na página **Novo link de região**, clique em **Nome** e digite um nome para o link de região de rede.</span><span class="sxs-lookup"><span data-stu-id="9ebde-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="9ebde-124">Clique em **região \#de rede 1**e clique na região de rede na lista que você deseja vincular à região \#de rede 2.</span><span class="sxs-lookup"><span data-stu-id="9ebde-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="9ebde-125">Clique em **região \#de rede 2**e, em seguida, clique em uma região de rede na lista que você deseja \#vincular à região de rede 1.</span><span class="sxs-lookup"><span data-stu-id="9ebde-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="9ebde-126">Opcionalmente, clique em **Política da largura de banda** e selecione o perfil da política de largura de banda que deseja aplicar para o link de região de rede.</span><span class="sxs-lookup"><span data-stu-id="9ebde-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="9ebde-127">Aplique uma política de largura de banda apenas se o link de região de rede é restrito por largura de banda e se deseja usar o CAC para controlar o tráfego de mídia naquele link.</span><span class="sxs-lookup"><span data-stu-id="9ebde-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="9ebde-128">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9ebde-128">Click **Commit**.</span></span>

10. <span data-ttu-id="9ebde-129">Para finalizar a criação de links de região de rede para sua topologia, repita as etapas 4 a 9 com as configurações de outras regiões.</span><span class="sxs-lookup"><span data-stu-id="9ebde-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
