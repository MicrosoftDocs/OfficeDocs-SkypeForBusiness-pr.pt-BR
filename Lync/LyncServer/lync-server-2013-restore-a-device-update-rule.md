---
title: 'Lync Server 2013: restaurar uma regra de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c6b6084577979264648e706c70fb6387b47971
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511628"
---
# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="90e93-102">Restaurar uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90e93-102">Restore a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90e93-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="90e93-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="90e93-104">Para desinstalar uma regra de atualização de dispositivo dos dispositivos em sua implantação, restaure-a.</span><span class="sxs-lookup"><span data-stu-id="90e93-104">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="90e93-105">A restauração de uma regra de atualização de dispositivo desinstala a atualização e reinstala a versão anterior dessa regra.</span><span class="sxs-lookup"><span data-stu-id="90e93-105">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="90e93-106">Você pode restaurar uma regra de atualização de dispositivo usando o painel de controle do Lync Server ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90e93-106">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="90e93-107">Para restaurar regras de atualização de dispositivo usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="90e93-107">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="90e93-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="90e93-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90e93-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="90e93-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="90e93-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="90e93-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="90e93-111">Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **atualização de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="90e93-111">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="90e93-112">Na página **atualização de dispositivo** , execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="90e93-112">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="90e93-113">Para restaurar uma regra, selecione essa regra.</span><span class="sxs-lookup"><span data-stu-id="90e93-113">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="90e93-114">Para restaurar todas as regras, clique em **Editar**e, em seguida, clique em **selecionar tudo**.</span><span class="sxs-lookup"><span data-stu-id="90e93-114">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="90e93-115">Clique no menu **ação** e, em seguida, clique em **restaurar**.</span><span class="sxs-lookup"><span data-stu-id="90e93-115">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="90e93-116">Restauração de regras de atualização de dispositivo usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90e93-116">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="90e93-117">As regras de atualização de dispositivo também podem ser restauradas usando o Windows PowerShell e o cmdlet **Restore-CsDeviceUpdateRule** ..</span><span class="sxs-lookup"><span data-stu-id="90e93-117">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="90e93-118">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90e93-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90e93-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="90e93-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="90e93-120">Para restaurar uma regra de atualização de dispositivo único em um servidor</span><span class="sxs-lookup"><span data-stu-id="90e93-120">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="90e93-121">O seguinte comando restaura a regra de atualização de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 no servidor Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="90e93-121">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="90e93-122">Para restaurar todas as regras de atualização de dispositivo em um servidor</span><span class="sxs-lookup"><span data-stu-id="90e93-122">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="90e93-123">Este comando restaura todas as regras de atualização de dispositivo no servidor Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="90e93-123">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="90e93-124">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="90e93-124">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

