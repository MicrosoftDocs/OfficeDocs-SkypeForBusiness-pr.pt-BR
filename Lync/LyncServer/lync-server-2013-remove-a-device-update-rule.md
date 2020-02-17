---
title: 'Lync Server 2013: remover uma regra de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6db307572d72d11b73baa723405fd32da46b7c75
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="9afea-102">Remover uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9afea-102">Remove a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9afea-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9afea-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9afea-104">Remover uma regra de atualização de dispositivo a retira permanentemente da fila de atualização do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9afea-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="9afea-105">Remover uma regra é diferente de desinstalar uma atualização dos dispositivos na sua implantação ou de seus dispositivos de teste.</span><span class="sxs-lookup"><span data-stu-id="9afea-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="9afea-106">Para desinstalar uma atualização aprovada da sua implantação, *restaure* a regra de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9afea-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="9afea-107">Para obter detalhes, consulte [Restore a Device Update Rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="9afea-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="9afea-108">Para desinstalar uma atualização que você não aprovou dos dispositivos de teste, *redefina* -a.</span><span class="sxs-lookup"><span data-stu-id="9afea-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="9afea-109">Para obter detalhes, consulte [Reset a Device Update Rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="9afea-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="9afea-110">Você pode remover uma regra de atualização de dispositivo usando o painel de controle do Lync Server ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9afea-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="9afea-111">Para remover as regras de atualização de dispositivo usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="9afea-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9afea-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9afea-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9afea-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9afea-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9afea-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9afea-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9afea-115">Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **atualização de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="9afea-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="9afea-116">Na página **atualização de dispositivo** , execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="9afea-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9afea-117">Para remover uma regra, selecione a regra que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="9afea-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="9afea-118">Para remover todas as regras, clique no menu **Editar** e, em seguida, clique em **selecionar tudo**.</span><span class="sxs-lookup"><span data-stu-id="9afea-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="9afea-119">Clique em **Editar**e em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="9afea-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9afea-120">Removendo regras de atualização de dispositivo usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9afea-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9afea-121">As regras de atualização de dispositivo também podem ser removidas usando o Windows PowerShell e o cmdlet **Remove-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="9afea-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="9afea-122">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9afea-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9afea-123">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="9afea-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="9afea-124">Para remover uma regra de atualização de dispositivo único de um servidor</span><span class="sxs-lookup"><span data-stu-id="9afea-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="9afea-125">O comando a seguir remove a regra de atualização de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 do servidor Web no atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9afea-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="9afea-126">Para remover todas as regras de atualização de dispositivo de um servidor</span><span class="sxs-lookup"><span data-stu-id="9afea-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="9afea-127">Este comando Remove todas as regras de atualização de dispositivo do servidor Web no atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9afea-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="9afea-128">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="9afea-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9afea-129">Confira Também</span><span class="sxs-lookup"><span data-stu-id="9afea-129">See Also</span></span>


[<span data-ttu-id="9afea-130">Aprovar uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9afea-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

