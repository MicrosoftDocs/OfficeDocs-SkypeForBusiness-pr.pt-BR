---
title: 'Lync Server 2013: exibindo informações de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52baf7c9dca4d663630bbf0cb17384916f5a953e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="aa0a7-102">Exibir informações de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa0a7-102">Viewing network region information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa0a7-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="aa0a7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="aa0a7-104">Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="aa0a7-105">Todas as regiões de rede devem estar associadas a um site central.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="aa0a7-106">O site central é o site do Data Center no qual o serviço de política de largura de banda do controle de admissão de chamadas (CAC) está em execução.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="aa0a7-107">Você pode usar o painel de controle do Lync Server para exibir regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-107">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="aa0a7-108">As regiões de rede incluem configurações que determinam se caminhos alternativos pela Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="aa0a7-109">Use este tópico para exibir regiões de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-109">Use this topic to view existing network regions.</span></span> <span data-ttu-id="aa0a7-110">Para obter detalhes sobre como criar ou modificar regiões de rede existentes, consulte [criando ou modificando regiões de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="aa0a7-110">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="aa0a7-111">Para ver informações sobre uma região de rede com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="aa0a7-111">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="aa0a7-112">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aa0a7-113">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aa0a7-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aa0a7-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aa0a7-115">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **região**.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-115">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="aa0a7-116">Na página **região** , clique na região que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-116">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa0a7-117">Você só pode exibir uma região de cada vez.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-117">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="aa0a7-118">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aa0a7-119">Exibir informações de região de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa0a7-119">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aa0a7-120">Você pode exibir informações de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="aa0a7-120">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="aa0a7-121">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aa0a7-122">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="aa0a7-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="aa0a7-123">Para ver as informações da região de rede</span><span class="sxs-lookup"><span data-stu-id="aa0a7-123">To view network region information</span></span>

  - <span data-ttu-id="aa0a7-124">Para ver as informações sobre todas as suas regiões de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="aa0a7-124">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="aa0a7-125">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="aa0a7-125">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="aa0a7-126">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="aa0a7-126">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa0a7-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="aa0a7-127">See Also</span></span>


[<span data-ttu-id="aa0a7-128">Criando ou modificando regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa0a7-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="aa0a7-129">Excluindo regiões de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa0a7-129">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

