---
title: 'Lync Server 2013: modificar configurações para arquivos de log de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 770682cfed17d9b029688275469351c1cfdf9f4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="a96b3-102">Modificar configurações para arquivos de log de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a96b3-102">Modify settings for Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a96b3-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a96b3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a96b3-104">Você pode alterar as configurações de como as informações de atualização de dispositivo são registradas em sua organização usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a96b3-104">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="a96b3-105">A tabela a seguir mostra quais configurações podem ser modificadas e quais ferramentas você usa para modificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="a96b3-105">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="a96b3-106">As configurações de log podem ser alteradas e aplicadas globalmente, ou por site.</span><span class="sxs-lookup"><span data-stu-id="a96b3-106">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a96b3-107">Para alterar</span><span class="sxs-lookup"><span data-stu-id="a96b3-107">To change</span></span></th>
<th><span data-ttu-id="a96b3-108">Usar</span><span class="sxs-lookup"><span data-stu-id="a96b3-108">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a96b3-109">O tamanho máximo (em bytes) para um arquivo de log</span><span class="sxs-lookup"><span data-stu-id="a96b3-109">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="a96b3-110">Painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-110">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a96b3-111">- ou -</span><span class="sxs-lookup"><span data-stu-id="a96b3-111">-or-</span></span></p>
<p><span data-ttu-id="a96b3-112">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-112">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96b3-113">A quantidade máxima de informações (em bytes) que podem ser mantidas no cache</span><span class="sxs-lookup"><span data-stu-id="a96b3-113">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="a96b3-114">Painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-114">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a96b3-115">- ou -</span><span class="sxs-lookup"><span data-stu-id="a96b3-115">-or-</span></span></p>
<p><span data-ttu-id="a96b3-116">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-116">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96b3-117">Frequência (em minutos) de gravação de informações armazenadas em cache no arquivo de log</span><span class="sxs-lookup"><span data-stu-id="a96b3-117">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="a96b3-118">Painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-118">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a96b3-119">- ou -</span><span class="sxs-lookup"><span data-stu-id="a96b3-119">-or-</span></span></p>
<p><span data-ttu-id="a96b3-120">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-120">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96b3-121">Quanto tempo (em dias) para manter os arquivos de log</span><span class="sxs-lookup"><span data-stu-id="a96b3-121">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="a96b3-122">Painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-122">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a96b3-123">- ou -</span><span class="sxs-lookup"><span data-stu-id="a96b3-123">-or-</span></span></p>
<p><span data-ttu-id="a96b3-124">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-124">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96b3-125">Quando (hora do dia) para verificar se há arquivos expirados que devem ser excluídos</span><span class="sxs-lookup"><span data-stu-id="a96b3-125">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="a96b3-126">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-126">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96b3-127">Quais extensões de arquivo de log permitir</span><span class="sxs-lookup"><span data-stu-id="a96b3-127">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="a96b3-128">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-128">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96b3-129">Quais tipos de arquivo de log manter</span><span class="sxs-lookup"><span data-stu-id="a96b3-129">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="a96b3-130">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-130">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="a96b3-131">Para alterar as configurações de log usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a96b3-131">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a96b3-132">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a96b3-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a96b3-133">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a96b3-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a96b3-134">Na barra de navegação à esquerda, clique em **clientes**e em **configuração de log de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a96b3-134">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="a96b3-135">Na página **configuração do log do dispositivo** , clique duas vezes na configuração que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="a96b3-135">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="a96b3-136">Na caixa de diálogo **Editar configuração de log** , altere qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a96b3-136">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="a96b3-137">**Tamanho máximo de arquivo (bytes)**   especifica o tamanho máximo que um arquivo de log pode se tornar antes de ser removido.</span><span class="sxs-lookup"><span data-stu-id="a96b3-137">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="a96b3-138">O padrão é 1.024.000 bytes (1 MB).</span><span class="sxs-lookup"><span data-stu-id="a96b3-138">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="a96b3-139">**Tamanho máximo de cache (bytes)**   especifica a quantidade máxima de informações (em bytes) que podem ser mantidas no cache de arquivos de log antes que o cache deve ser limpo e os dados são gravados em um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="a96b3-139">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="a96b3-140">O padrão é 512.000 bytes (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="a96b3-140">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="a96b3-141">**Número de minutos para liberar o cache (1-60)**   indica a frequência com que as informações armazenadas no cache do arquivo de log são gravadas no arquivo de log real.</span><span class="sxs-lookup"><span data-stu-id="a96b3-141">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="a96b3-142">Depois que os dados são registrados, o cache é limpo.</span><span class="sxs-lookup"><span data-stu-id="a96b3-142">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="a96b3-143">O padrão é cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="a96b3-143">The default is five minutes.</span></span>
    
      - <span data-ttu-id="a96b3-144">**Número de dias para manter arquivos de log (1-365)**   especifica o número de dias que os arquivos de log são mantidos antes de serem limpos.</span><span class="sxs-lookup"><span data-stu-id="a96b3-144">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="a96b3-145">O padrão é 10 dias.</span><span class="sxs-lookup"><span data-stu-id="a96b3-145">The default is 10 days.</span></span>

5.  <span data-ttu-id="a96b3-146">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a96b3-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a96b3-147">Alterar as configurações de log usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a96b3-147">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a96b3-148">As configurações de arquivo de log de atualização de dispositivo podem ser modificadas usando o Windows PowerShell e o cmdlet **set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a96b3-148">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="a96b3-149">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a96b3-149">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a96b3-150">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="a96b3-150">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="a96b3-151">Os exemplos a seguir mostram algumas das maneiras que você pode usar **set-CsDeviceUpdateConfiguration** para modificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="a96b3-151">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="a96b3-152">Para modificar o tamanho máximo do arquivo de log e o intervalo de limpeza de log</span><span class="sxs-lookup"><span data-stu-id="a96b3-152">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="a96b3-153">O comando a seguir modifica as configurações de log de atualização de dispositivo aplicadas ao site Redmond.</span><span class="sxs-lookup"><span data-stu-id="a96b3-153">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="a96b3-154">Neste exemplo, o tamanho máximo do arquivo de log é definido como 204800 bytes e o intervalo de limpeza do log é definido como 14 dias.</span><span class="sxs-lookup"><span data-stu-id="a96b3-154">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="a96b3-155">Para modificar o horário de limpeza do log do dia</span><span class="sxs-lookup"><span data-stu-id="a96b3-155">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="a96b3-156">Este comando define o tempo de limpeza do log para o site Redmond para 3:00 AM.</span><span class="sxs-lookup"><span data-stu-id="a96b3-156">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="a96b3-157">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="a96b3-157">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

