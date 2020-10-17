---
title: 'Lync Server 2013: excluir uma coleção de definições de configuração de atualização de dispositivo'
description: 'Lync Server 2013: excluir uma coleção de definições de configuração de atualização de dispositivo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3a03227869f68a52a30ea94db33bfb954b7e122
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566647"
---
# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="cd777-103">Excluir uma coleção de definições de configuração de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd777-103">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd777-104">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="cd777-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="cd777-105">As definições de configuração de atualização de dispositivo também podem ser excluídas usando o Windows PowerShell e o cmdlet **Remove-CsdeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="cd777-105">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="cd777-106">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd777-106">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cd777-107">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="cd777-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="cd777-108">Para remover um conjunto específico de definições de configuração de atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="cd777-108">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="cd777-109">Este comando exclui as definições de configuração de atualização de dispositivo aplicadas ao site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="cd777-109">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="cd777-110">Para remover todas as definições de configuração de atualização de dispositivo aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="cd777-110">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="cd777-111">Este comando exclui todas as definições de configuração de atualização de dispositivo aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="cd777-111">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="cd777-112">Para remover as definições de configuração de atualização de dispositivo com base no valor da propriedade LogCleanUpInterval</span><span class="sxs-lookup"><span data-stu-id="cd777-112">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="cd777-113">O comando a seguir exclui todas as definições de configuração de atualização de dispositivo onde o intervalo de limpeza de log é maior que 10 dias (10,00:00:00):</span><span class="sxs-lookup"><span data-stu-id="cd777-113">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="cd777-114">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="cd777-114">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

