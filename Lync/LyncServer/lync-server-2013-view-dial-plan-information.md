---
title: 'Lync Server 2013: exibir informações do plano de discagem'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial plan information
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49733587
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c63aead21441cb972cce2b6fb26391efc43969bb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-plan-information-in-lync-server-2013"></a><span data-ttu-id="c7f21-102">Exibir informações do plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7f21-102">View dial plan information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7f21-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c7f21-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c7f21-104">Para exibir informações de um plano de discagem existente, realize as etapas no seguinte procedimento.</span><span class="sxs-lookup"><span data-stu-id="c7f21-104">To view information for an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="c7f21-105">Se você quiser criar um novo plano de discagem, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="c7f21-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-view-information-about-a-dial-plan-from-lync-server-control-panel"></a><span data-ttu-id="c7f21-106">Para exibir informações sobre um plano de discagem no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c7f21-106">To view information about a dial plan from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c7f21-107">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c7f21-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c7f21-108">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c7f21-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c7f21-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7f21-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c7f21-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c7f21-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c7f21-111">Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Plano de Discagem**.</span><span class="sxs-lookup"><span data-stu-id="c7f21-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="c7f21-112">Na página **Plano de Discagem**, dê um duplo clique no nome de um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="c7f21-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7f21-113">É possível exibir informações para apenas um plano de discagem por vez.</span><span class="sxs-lookup"><span data-stu-id="c7f21-113">You can view information for only one dial plan at a time.</span></span>

    
    </div>

</div>

<div>

## <a name="to-view-dial-plans-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c7f21-114">Para exibir planos de discagem usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7f21-114">To view dial plans by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="c7f21-115">Os planos de discagem podem ser exibidos usando a interface de linha de comando do Windows PowerShell e o cmdlet **Get-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="c7f21-115">Dial plans can be viewed by using the Windows PowerShell command-line interface and the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="c7f21-116">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7f21-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c7f21-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="c7f21-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="c7f21-118">Para exibir informações sobre todos os planos de discagem, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="c7f21-118">To view information about all your dial plans, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="c7f21-119">Este comando retornará informações similares a este:</span><span class="sxs-lookup"><span data-stu-id="c7f21-119">That command will return information similar to this:</span></span>
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7f21-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="c7f21-120">See Also</span></span>


[<span data-ttu-id="c7f21-121">Criar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7f21-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="c7f21-122">Modificar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7f21-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

