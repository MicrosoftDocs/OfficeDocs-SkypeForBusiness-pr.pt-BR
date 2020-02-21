---
title: 'Lync Server 2013: excluir arquivos de log de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 685b3e34c0f2bd5392f71899564d0738e814b616
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="c9c8c-102">Excluir arquivos de log de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9c8c-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9c8c-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c9c8c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c9c8c-104">O serviço Web de atualização de dispositivo mantém uma ampla coleção de arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="c9c8c-105">Essa coleção inclui os logs de auditoria conduzidos pelo próprio serviço e arquivos de log carregados de dispositivos clientes.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="c9c8c-106">Para impedir que o servidor seja preenchido com logs do serviço Web de atualização de dispositivos, você provavelmente desejará desmarcá-lo de arquivos de log que já estão por um determinado número de dias.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="c9c8c-107">Defina esse número de dias com base na atividade de atualização e no número de dispositivos clientes em sua organização e usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="c9c8c-108">Para limpar o log de atualização de dispositivo usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c9c8c-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c9c8c-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c9c8c-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c9c8c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="c9c8c-111">Na barra de navegação à esquerda, clique em **clientes**e em **configuração de log de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="c9c8c-112">Na página **configuração do log do dispositivo** , clique duas vezes na configuração que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="c9c8c-113">Na caixa de diálogo **Editar configuração de log** , em **número de dias para manter arquivos de log (1-365)**, especifique um número de dias.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="c9c8c-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-114">Click **Commit**.</span></span> <span data-ttu-id="c9c8c-115">Todos os arquivos que estão no servidor por mais do que o número de dia especificado são excluídos.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="c9c8c-116">Essa configuração será aplicada a essa configuração até que você a altere.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="c9c8c-117">Limpando o log de atualização de dispositivo usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9c8c-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c9c8c-118">Você pode limpar logs de atualização de dispositivo usando o Windows PowerShell e o cmdlet **Clear-CsDeviceUpdateLog** .</span><span class="sxs-lookup"><span data-stu-id="c9c8c-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="c9c8c-119">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9c8c-120">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="c9c8c-121">Para limpar logs de atualização de dispositivo em um servidor</span><span class="sxs-lookup"><span data-stu-id="c9c8c-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="c9c8c-122">O comando a seguir limpa o log de atualização do dispositivo no servidor Web atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="c9c8c-123">Todas as entradas de log com mais de 10 dias (o valor especificado pelo parâmetro DaysBack) serão removidas do log.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="c9c8c-124">Para limpar todos os logs de atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="c9c8c-124">To clear all device update logs</span></span>

  - <span data-ttu-id="c9c8c-125">Este comando remove as entradas desatualizadas (neste exemplo, entradas com mais de 10 dias) de todos os logs de atualização de dispositivo atualmente em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="c9c8c-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="c9c8c-126">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .</span><span class="sxs-lookup"><span data-stu-id="c9c8c-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

