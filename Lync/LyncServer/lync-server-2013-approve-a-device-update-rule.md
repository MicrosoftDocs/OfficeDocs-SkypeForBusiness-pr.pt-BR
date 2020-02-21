---
title: 'Lync Server 2013: aprovar uma regra de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c6fad9547e9c738523ac0f460d3e6696d1920a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="b1b45-102">Aprovar uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1b45-102">Approve a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1b45-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b1b45-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b1b45-104">Após a importação de uma regra de atualização de dispositivo, ela é instalada em seus dispositivos de teste.</span><span class="sxs-lookup"><span data-stu-id="b1b45-104">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="b1b45-105">Se o teste for bem-sucedido e você quiser distribuir a atualização para sua organização, aprove-a usando o painel de controle do Lync Server ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1b45-105">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="b1b45-106">Para aprovar uma regra de atualização de dispositivo usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="b1b45-106">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b1b45-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b1b45-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b1b45-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b1b45-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b1b45-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b1b45-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b1b45-110">Na página **atualização de dispositivo** , execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b1b45-110">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b1b45-111">Para aprovar uma regra, selecione essa regra.</span><span class="sxs-lookup"><span data-stu-id="b1b45-111">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="b1b45-112">Para aprovar todas as regras, clique em **Editar**e, em seguida, clique em **selecionar tudo**.</span><span class="sxs-lookup"><span data-stu-id="b1b45-112">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="b1b45-113">Clique em **ação**e em **aprovar**.</span><span class="sxs-lookup"><span data-stu-id="b1b45-113">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b1b45-114">Aprovar uma regra de atualização de dispositivo usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1b45-114">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b1b45-115">As regras de atualização de dispositivo também podem ser aprovadas usando o Windows PowerShell e o cmdlet **Approve-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="b1b45-115">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="b1b45-116">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1b45-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1b45-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="b1b45-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="b1b45-118">Para aprovar uma única regra de atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b1b45-118">To approve a single device update rule</span></span>

  - <span data-ttu-id="b1b45-119">O comando a seguir aprova a regra de atualização de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 encontrada no servidor Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="b1b45-119">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="b1b45-120">Para aprovar várias regras de atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b1b45-120">To approve multiple device update rules</span></span>

  - <span data-ttu-id="b1b45-121">Este comando aprova todas as regras de atualização de dispositivo para dispositivos da marca Microsoft:</span><span class="sxs-lookup"><span data-stu-id="b1b45-121">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="b1b45-122">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="b1b45-122">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1b45-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="b1b45-123">See Also</span></span>


[<span data-ttu-id="b1b45-124">Importar regras de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1b45-124">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="b1b45-125">Restaurar uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1b45-125">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

