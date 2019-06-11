---
title: 'Lync Server 2013: remover uma regra de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3776fe2b80e301e02c099f3c6154afc1c382d0d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="0f695-102">Remover uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f695-102">Remove a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f695-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0f695-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0f695-104">Remover uma regra de atualização de dispositivo a retira permanentemente da fila de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0f695-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="0f695-105">Remover uma regra é diferente de desinstalar uma atualização dos dispositivos na sua implantação ou dos seus dispositivos de teste.</span><span class="sxs-lookup"><span data-stu-id="0f695-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="0f695-106">Para desinstalar uma atualização aprovada da sua implantação, *restaure* a regra de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0f695-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="0f695-107">Para obter detalhes, consulte [restaurar uma regra de atualização de dispositivo no Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="0f695-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="0f695-108">Para desinstalar uma atualização que você não aprovou dos seus dispositivos de teste \*\* , você a redefiniu.</span><span class="sxs-lookup"><span data-stu-id="0f695-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="0f695-109">Para obter detalhes, consulte [redefinir uma regra de atualização de dispositivo no Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="0f695-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="0f695-110">Você pode remover uma regra de atualização de dispositivo usando o painel de controle do Lync Server ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f695-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="0f695-111">Para remover regras de atualização de dispositivo usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="0f695-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0f695-112">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="0f695-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0f695-113">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f695-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0f695-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0f695-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0f695-115">Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação de **atualização do dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="0f695-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="0f695-116">Na página **atualização do dispositivo** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="0f695-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="0f695-117">Para remover uma regra, selecione a regra que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="0f695-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="0f695-118">Para remover todas as regras, clique no menu **Editar** e, em seguida, clique em **selecionar tudo**.</span><span class="sxs-lookup"><span data-stu-id="0f695-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="0f695-119">Clique em **Editar** e então em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0f695-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0f695-120">Remover regras de atualização de dispositivo usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f695-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0f695-121">As regras de atualização de dispositivo também podem ser removidas usando o Windows PowerShell e o cmdlet **Remove-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="0f695-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="0f695-122">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f695-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0f695-123">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="0f695-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="0f695-124">Para remover uma regra de atualização de dispositivo único de um servidor</span><span class="sxs-lookup"><span data-stu-id="0f695-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="0f695-125">O comando a seguir remove a regra de atualização de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 do servidor Web em atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="0f695-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="0f695-126">Para remover todas as regras de atualização de dispositivo de um servidor</span><span class="sxs-lookup"><span data-stu-id="0f695-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="0f695-127">Esse comando Remove todas as regras de atualização de dispositivo do servidor Web no atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="0f695-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="0f695-128">Para obter detalhes, consulte o tópico da ajuda para o cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="0f695-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f695-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="0f695-129">See Also</span></span>


[<span data-ttu-id="0f695-130">Aprovar uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f695-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

