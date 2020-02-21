---
title: 'Lync Server 2013: redefinir uma regra de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa5bd589a6368e99401f2f84d702756d595f9be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="7ea16-102">Redefinir uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ea16-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ea16-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7ea16-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7ea16-104">Se você não gostar da forma como uma atualização funciona em seus dispositivos de teste, é possível redefinir a regra de atualização de dispositivo, que remove o status pendente da regra e desinstala a atualização dos dispositivos de teste.</span><span class="sxs-lookup"><span data-stu-id="7ea16-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="7ea16-105">Você pode remover uma regra de atualização de dispositivo usando o painel de controle do Lync Server ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ea16-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ea16-106">Para desinstalar uma regra que você já aprovou (isto é, distribuída), restaure-a.</span><span class="sxs-lookup"><span data-stu-id="7ea16-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="7ea16-107">Para obter detalhes, consulte <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update Rule in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7ea16-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="7ea16-108">Para redefinir uma regra de atualização de dispositivo usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="7ea16-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7ea16-109">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="7ea16-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ea16-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ea16-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7ea16-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7ea16-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7ea16-112">Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **atualização de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="7ea16-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="7ea16-113">Na página **atualização de dispositivo** , execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7ea16-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7ea16-114">Para redefinir uma regra, selecione a regra que você deseja redefinir.</span><span class="sxs-lookup"><span data-stu-id="7ea16-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="7ea16-115">Para redefinir todas as regras, no menu **Editar** , clique em **selecionar tudo**.</span><span class="sxs-lookup"><span data-stu-id="7ea16-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="7ea16-116">Para redefinir todas as regras para uma marca, use o menu coluna **da marca** .</span><span class="sxs-lookup"><span data-stu-id="7ea16-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="7ea16-117">Clique em **ação**e, em seguida, clique em **cancelar atualizações pendentes**.</span><span class="sxs-lookup"><span data-stu-id="7ea16-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7ea16-118">Se você tiver certeza de que nunca vai querer distribuir as regras de atualização de dispositivo que você cancelou, convém excluí-las.</span><span class="sxs-lookup"><span data-stu-id="7ea16-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="7ea16-119">Para obter detalhes, consulte <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update Rule in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7ea16-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7ea16-120">Redefinindo uma regra de atualização de dispositivo usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ea16-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7ea16-121">As regras de atualização de dispositivo também podem ser redefinidas usando o Windows PowerShell e o cmdlet **Reset-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="7ea16-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="7ea16-122">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ea16-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ea16-123">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="7ea16-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="7ea16-124">Para redefinir uma regra de atualização de dispositivo específica em um servidor</span><span class="sxs-lookup"><span data-stu-id="7ea16-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="7ea16-125">O comando a seguir redefine a regra de atualização de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 no servidor Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="7ea16-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="7ea16-126">Para redefinir todas as regras de atualização de dispositivo em um servidor</span><span class="sxs-lookup"><span data-stu-id="7ea16-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="7ea16-127">Este comando redefine todas as regras de atualização de dispositivo no servidor Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="7ea16-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="7ea16-128">Para redefinir todas as regras de atualização de dispositivos que têm uma marca específica</span><span class="sxs-lookup"><span data-stu-id="7ea16-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="7ea16-129">Neste exemplo, todas as atualizações de dispositivo em toda a organização que têm uma marca igual à Microsoft são redefinidas:</span><span class="sxs-lookup"><span data-stu-id="7ea16-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="7ea16-130">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="7ea16-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ea16-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="7ea16-131">See Also</span></span>


[<span data-ttu-id="7ea16-132">Aprovar uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ea16-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

