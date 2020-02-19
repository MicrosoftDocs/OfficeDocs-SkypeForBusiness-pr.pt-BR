---
title: 'Lync Server 2013: exibir informações de configuração de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccf5658b49118f4053f0bd76b18273fb77f90237
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a><span data-ttu-id="3ddae-102">Exibir informações de configuração de CDR no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ddae-102">View CDR configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ddae-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3ddae-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3ddae-p101">O CDR (registro de detalhes de chamadas) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.</span><span class="sxs-lookup"><span data-stu-id="3ddae-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="3ddae-106">Quando você instala o Microsoft Lync Server 2013, um único conjunto global de definições de configuração de CDR é criado para você.</span><span class="sxs-lookup"><span data-stu-id="3ddae-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="3ddae-107">Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a sites individuais.</span><span class="sxs-lookup"><span data-stu-id="3ddae-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="3ddae-108">Você pode exibir as definições de configuração de CDR em uso na sua organização usando o painel de controle do Lync Server ou o cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3ddae-108">You can view the CDR configuration settings in use in your organization by using Lync Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="3ddae-109">Para exibir informações de configuração de CDR usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="3ddae-109">To view CDR configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3ddae-110">No painel de controle do Lync Server, clique em **monitoramento e arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="3ddae-110">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="3ddae-p103">Uma lista com todas as configurações de CDR será exibida na guia **Registro de Detalhes de Chamada**. Para cada conjunto de configurações, você verá o **Nome** do conjunto; se o CDR foi habilitado ou não (a propriedade **CDR**); e se a limpeza foi habilitada ou não (a propriedade **Limpeza de CDR**). Para ver informações detalhadas sobre um conjunto, clique duas vezes no conjunto ou selecione o conjunto correto, clique em **Editar** e em **Mostrar Detalhes**. Observe que só é possível visualizar informações detalhadas de um conjunto de configurações de CDR por vez.</span><span class="sxs-lookup"><span data-stu-id="3ddae-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3ddae-114">Exibindo informações de configuração de CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ddae-114">Viewing CDR Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3ddae-115">Você pode visualizar as definições de configuração de CDR usando o Windows PowerShell e o cmdlet Get-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3ddae-115">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="3ddae-116">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ddae-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3ddae-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="3ddae-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="3ddae-118">Para visualizar informações de configuração do CDR</span><span class="sxs-lookup"><span data-stu-id="3ddae-118">To view CDR configuration information</span></span>

  - <span data-ttu-id="3ddae-119">Para exibir informações sobre todas as suas definições de configuração de CDR, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="3ddae-119">To view information about all your CDR configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsCdrConfiguration
    
    <span data-ttu-id="3ddae-120">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="3ddae-120">That will return information similar to this:</span></span>
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

<span data-ttu-id="3ddae-121">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3ddae-121">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

