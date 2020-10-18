---
title: 'Lync Server 2013: índice de cmdlets'
description: 'Lync Server 2013: índice de cmdlets.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets index
ms:assetid: cd37aba7-3d27-4db9-b69f-3a6da1fb4b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398867(v=OCS.15)
ms:contentKeyID: 48185661
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41df7b0c7c0c5ffd873c36968d4413ec7751f40f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577047"
---
# <a name="lync-server-2013-cmdlets-index"></a><span data-ttu-id="71929-103">Índice de cmdlets do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71929-103">Lync Server 2013 cmdlets index</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71929-104">_**Última modificação do tópico:** 2016-04-12_</span><span class="sxs-lookup"><span data-stu-id="71929-104">_**Topic Last Modified:** 2016-04-12_</span></span>

<span data-ttu-id="71929-105">O Microsoft Lync Server 2013 vem com mais de 700 cmdlets que permitem que administradores gerenciem o Lync Server 2013 na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="71929-105">Microsoft Lync Server 2013 ships with more than 700 cmdlets that enable administrators to manage Lync Server 2013 from the command line.</span></span> <span data-ttu-id="71929-106">Os cmdlets do Lync Server normalmente são usados com o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="71929-106">The Lync Server cmdlets are typically used with the Lync Server Management Shell.</span></span> <span data-ttu-id="71929-107">Uma maneira de usar o Shell de gerenciamento do Lync Server é fazer logon em um computador que executa uma função de servidor ou serviço do Lync Server, clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="71929-107">One way to use the Lync Server Management Shell is to log on to a computer running a Lync Server service or server role, click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="71929-108">Quando o Shell de Gerenciamento estiver aberto, é possível recuperar a ajuda de um cmdlet diretamente na linha de comando digitando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="71929-108">After the Management Shell is open you can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="71929-109">O comando anterior recupera a ajuda completa disponível para o cmdlet **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="71929-109">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="71929-110">Para exibir a ajuda para um cmdlet diferente, substitua **New-CsVoicePolicy** pelo nome do cmdlet para o qual você deseja recuperar a ajuda.</span><span class="sxs-lookup"><span data-stu-id="71929-110">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="71929-111">Para recuperar uma lista completa de cmdlets disponíveis para o gerenciamento do Lync Server, digite o seguinte no prompt de comando do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="71929-111">To retrieve a full list of cmdlets available for managing Lync Server, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="71929-112">Para obter detalhes sobre como usar o Shell de gerenciamento do Lync Server, consulte o blog do Lync Server Windows PowerShell em [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150) .</span><span class="sxs-lookup"><span data-stu-id="71929-112">For details about using the Lync Server Management Shell, see the Lync Server Windows PowerShell blog at [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

<div>

## <a name="lync-server-2013-cmdlets"></a><span data-ttu-id="71929-113">Cmdlets do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71929-113">Lync Server 2013 Cmdlets</span></span>

<span data-ttu-id="71929-114">Veja a seguir uma lista dos cmdlets fornecidos com o Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="71929-114">Following is a list of the cmdlets that ship with Lync Server 2013:</span></span>

  - <span data-ttu-id="71929-115">[Add-CsSlaDelegates](https://technet.microsoft.com/library/Mt703199(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-115">[Add-CsSlaDelegates](https://technet.microsoft.com/library/Mt703199(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-116">[Aprovar-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-116">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-117">[Backup-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-117">[Backup-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-118">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-118">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-119">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-119">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-120">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-120">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-121">[Convert-CsUserData](https://technet.microsoft.com/library/JJ205337(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-121">[Convert-CsUserData](https://technet.microsoft.com/library/JJ205337(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-122">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-122">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-123">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-123">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-124">[Debug-CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-124">[Debug-CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-125">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-125">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-126">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-126">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-127">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-127">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-128">[Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-128">[Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-129">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-129">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-130">[Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-130">[Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-131">[Disable-CsUser](https://technet.microsoft.com/library/Gg398747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-131">[Disable-CsUser](https://technet.microsoft.com/library/Gg398747(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-132">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-132">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-133">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-133">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-134">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-134">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-135">[Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-135">[Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-136">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-136">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-137">[Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-137">[Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-138">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-138">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-139">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-139">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-140">[Enable-CsUser](https://technet.microsoft.com/library/Gg398711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-140">[Enable-CsUser](https://technet.microsoft.com/library/Gg398711(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-141">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-141">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-142">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-142">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-143">[Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-143">[Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-144">[Export-CsPersistentChatData](https://technet.microsoft.com/library/JJ205378(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-144">[Export-CsPersistentChatData](https://technet.microsoft.com/library/JJ205378(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-145">[Export-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-145">[Export-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205011(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-146">[Export-CsUserData](https://technet.microsoft.com/library/JJ204897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-146">[Export-CsUserData](https://technet.microsoft.com/library/JJ204897(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-147">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-147">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-148">[Get-CsAdContact](https://technet.microsoft.com/library/Gg412776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-148">[Get-CsAdContact](https://technet.microsoft.com/library/Gg412776(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-149">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-149">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-150">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-150">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-151">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-151">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-152">[Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-152">[Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-153">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-153">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-154">[Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-154">[Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-155">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-155">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-156">[Get-CsAdUser](https://technet.microsoft.com/library/Gg398592(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-156">[Get-CsAdUser](https://technet.microsoft.com/library/Gg398592(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-157">[Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-157">[Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-158">[Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-158">[Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-159">[Get-CsAnnouncement](https://technet.microsoft.com/library/Gg398937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-159">[Get-CsAnnouncement](https://technet.microsoft.com/library/Gg398937(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-160">[Get-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398655(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-160">[Get-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398655(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-161">[Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-161">[Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-162">[Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-162">[Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-163">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-163">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-164">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-164">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-165">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-165">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-166">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-166">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-167">[Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-167">[Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-168">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-168">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-169">[Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-169">[Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-170">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-170">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-171">[Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-171">[Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-172">[Get-CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-172">[Get-CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-173">[Get-CsClientAccessLicense](https://technet.microsoft.com/library/JJ204853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-173">[Get-CsClientAccessLicense](https://technet.microsoft.com/library/JJ204853(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-174">[Get-CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-174">[Get-CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-175">[Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-175">[Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-176">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-176">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-177">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-177">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-178">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-178">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-179">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-179">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-180">[Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-180">[Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-181">[Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-181">[Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-182">[Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-182">[Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-183">[Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-183">[Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-184">[Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-184">[Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-185">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-185">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-186">[Get-CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-186">[Get-CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-187">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-187">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-188">[Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-188">[Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-189">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-189">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-190">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-190">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-191">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-191">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-192">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-192">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-193">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-193">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-194">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-194">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-195">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-195">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-196">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-196">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-197">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-197">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-198">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-198">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-199">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-199">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-200">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-200">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-201">[Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-201">[Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-202">[Get-CsEffectivePolicy](https://technet.microsoft.com/library/JJ204636(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-202">[Get-CsEffectivePolicy](https://technet.microsoft.com/library/JJ204636(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-203">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-203">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-204">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-204">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-205">[Get-CsExUmContact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-205">[Get-CsExUmContact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-206">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-206">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-207">[Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-207">[Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-208">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-208">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-209">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-209">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-210">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-210">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-211">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-211">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-212">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-212">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-213">[Get-CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-213">[Get-CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-214">[Get-CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-214">[Get-CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-215">[Get-CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-215">[Get-CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-216">[Get-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-216">[Get-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-217">[Get-CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-217">[Get-CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-218">[Get-CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-218">[Get-CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-219">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-219">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-220">[Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-220">[Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-221">[Get-CsManagementConnection](https://technet.microsoft.com/library/Gg412849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-221">[Get-CsManagementConnection](https://technet.microsoft.com/library/Gg412849(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-222">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-222">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-223">[Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-223">[Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-224">[Get-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-224">[Get-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398128(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-225">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-225">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-226">[Get-CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-226">[Get-CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-227">[Get-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-227">[Get-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-228">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-228">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-229">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-229">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-230">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-230">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-231">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-231">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-232">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-232">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-233">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-233">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-234">[Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-234">[Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-235">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-235">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-236">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-236">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-237">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-237">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-238">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-238">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-239">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-239">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-240">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-240">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-241">[Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-241">[Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-242">[Get-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-242">[Get-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-243">[Get-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-243">[Get-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-244">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-244">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-245">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-245">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-246">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-246">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-247">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-247">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-248">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-248">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-249">[Get-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-249">[Get-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-250">[Get-CsPersistentChatState](https://technet.microsoft.com/library/JJ204915(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-250">[Get-CsPersistentChatState](https://technet.microsoft.com/library/JJ204915(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-251">[Get-CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-251">[Get-CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-252">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-252">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-253">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-253">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-254">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-254">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-255">[Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-255">[Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-256">[Get-CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-256">[Get-CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-257">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-257">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-258">[Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-258">[Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-259">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-259">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-260">[Get-CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-260">[Get-CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-261">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-261">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-262">[Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-262">[Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-263">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-263">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-264">[Get-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-264">[Get-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-265">[Get-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425793(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-265">[Get-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425793(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-266">[Get-CsRgsConfiguration](https://technet.microsoft.com/library/Gg412762(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-266">[Get-CsRgsConfiguration](https://technet.microsoft.com/library/Gg412762(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-267">[Get-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg412983(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-267">[Get-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg412983(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-268">[Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398284(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-268">[Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398284(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-269">[Get-CsRgsQueue](https://technet.microsoft.com/library/Gg412759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-269">[Get-CsRgsQueue](https://technet.microsoft.com/library/Gg412759(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-270">[Get-CsRgsWorkflow](https://technet.microsoft.com/library/Gg425766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-270">[Get-CsRgsWorkflow](https://technet.microsoft.com/library/Gg425766(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-271">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-271">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-272">[Get-CsServerApplication](https://technet.microsoft.com/library/Gg425948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-272">[Get-CsServerApplication](https://technet.microsoft.com/library/Gg425948(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-273">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-273">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-274">[Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-274">[Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-275">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-275">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-276">[Get-CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-276">[Get-CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-277">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-277">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-278">[Get-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-278">[Get-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-279">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-279">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-280">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-280">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-281">[Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-281">[Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-282">[Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-282">[Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-283">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-283">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-284">[Get-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-284">[Get-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-285">[Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-285">[Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-286">[Get-CsTrustedApplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-286">[Get-CsTrustedApplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-287">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-287">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-288">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-288">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-289">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-289">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-290">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-290">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-291">[Get-CsUICulture](https://technet.microsoft.com/library/Gg412900(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-291">[Get-CsUICulture](https://technet.microsoft.com/library/Gg412900(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-292">[Get-CsUnassignedNumber](https://technet.microsoft.com/library/Gg412792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-292">[Get-CsUnassignedNumber](https://technet.microsoft.com/library/Gg412792(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-293">[Get-CsUser](https://technet.microsoft.com/library/Gg398125(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-293">[Get-CsUser](https://technet.microsoft.com/library/Gg398125(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-294">[Get-CsUserAcp](https://technet.microsoft.com/library/Gg398978(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-294">[Get-CsUserAcp](https://technet.microsoft.com/library/Gg398978(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-295">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-295">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-296">[Get-CsUserPoolInfo](https://technet.microsoft.com/library/Gg398615(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-296">[Get-CsUserPoolInfo](https://technet.microsoft.com/library/Gg398615(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-297">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-297">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-298">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-298">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-299">[Get-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ204838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-299">[Get-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ204838(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-300">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-300">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-301">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-301">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425732(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-302">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-302">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-303">[Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-303">[Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-304">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-304">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-305">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-305">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-306">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-306">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-307">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-307">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-308">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-308">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-309">[Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-309">[Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-310">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-310">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-311">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-311">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-312">[Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-312">[Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-313">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-313">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-314">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-314">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-315">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-315">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-316">[Grant-CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-316">[Grant-CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-317">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-317">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-318">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-318">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-319">[Grant-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-319">[Grant-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-320">[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-320">[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-321">[Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-321">[Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-322">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-322">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-323">[Grant-CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-323">[Grant-CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-324">[Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-324">[Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-325">[Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-325">[Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-326">[Grant-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205388(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-326">[Grant-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205388(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-327">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-327">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-328">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-328">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-329">[Import-CsAnnouncementFile](https://technet.microsoft.com/library/Gg398472(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-329">[Import-CsAnnouncementFile](https://technet.microsoft.com/library/Gg398472(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-330">[Import-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-330">[Import-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-331">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-331">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-332">[Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-332">[Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-333">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-333">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-334">[Import-CsLegacyConfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-334">[Import-CsLegacyConfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-335">[Import-CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-335">[Import-CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-336">[Import-CsPersistentChatData](https://technet.microsoft.com/library/JJ204709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-336">[Import-CsPersistentChatData](https://technet.microsoft.com/library/JJ204709(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-337">[Import-CsRgsAudioFile](https://technet.microsoft.com/library/Gg412830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-337">[Import-CsRgsAudioFile](https://technet.microsoft.com/library/Gg412830(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-338">[Import-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-338">[Import-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205245(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-339">[Import-CsUserData](https://technet.microsoft.com/library/JJ205373(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-339">[Import-CsUserData](https://technet.microsoft.com/library/JJ205373(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-340">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-340">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-341">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-341">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-342">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-342">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-343">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-343">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-344">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-344">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-345">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-345">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-346">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-346">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-347">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-347">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-348">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-348">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-349">[Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-349">[Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-350">[Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-350">[Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-351">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-351">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-352">[Invoke-CsUcsRollback](https://technet.microsoft.com/library/JJ204661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-352">[Invoke-CsUcsRollback](https://technet.microsoft.com/library/JJ204661(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-353">[Lock-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-353">[Lock-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-354">[Merge-CsLegacyTopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-354">[Merge-CsLegacyTopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-355">[Move-CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-355">[Move-CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-356">[Move-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-356">[Move-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-357">[Move-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-357">[Move-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-358">[Move-CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-358">[Move-CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-359">[Move-CsExUmContact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-359">[Move-CsExUmContact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-360">[Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-360">[Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-361">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-361">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-362">[Move-CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-362">[Move-CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-363">[Move-CsRgsConfiguration](https://technet.microsoft.com/library/Gg398782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-363">[Move-CsRgsConfiguration](https://technet.microsoft.com/library/Gg398782(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-364">[Move-CsUser](https://technet.microsoft.com/library/Gg398528(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-364">[Move-CsUser](https://technet.microsoft.com/library/Gg398528(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-365">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-365">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-366">[New-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-366">[New-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-367">[New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-367">[New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-368">[New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-368">[New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-369">[New-CsAnnouncement](https://technet.microsoft.com/library/Gg398522(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-369">[New-CsAnnouncement](https://technet.microsoft.com/library/Gg398522(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-370">[New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-370">[New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-371">[New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-371">[New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-372">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-372">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-373">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-373">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-374">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-374">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-375">[New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-375">[New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-376">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-376">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-377">[New-CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-377">[New-CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-378">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-378">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-379">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-379">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-380">[New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-380">[New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-381">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-381">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-382">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-382">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-383">[New-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-383">[New-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-384">[New-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-384">[New-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-385">[New-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-385">[New-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-386">[New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-386">[New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-387">[New-CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-387">[New-CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-388">[New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-388">[New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-389">[New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-389">[New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-390">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-390">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-391">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-391">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-392">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-392">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-393">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-393">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-394">[New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-394">[New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-395">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-395">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-396">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-396">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-397">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-397">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-398">[New-CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-398">[New-CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-399">[New-CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-399">[New-CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-400">[New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-400">[New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-401">[New-CsExUmContact](https://technet.microsoft.com/library/Gg398139(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-401">[New-CsExUmContact](https://technet.microsoft.com/library/Gg398139(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-402">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-402">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-403">[New-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-403">[New-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-404">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-404">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-405">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-405">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-406">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-406">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-407">[New-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-407">[New-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-408">[New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-408">[New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-409">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-409">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-410">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-410">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-411">[New-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-411">[New-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-412">[New-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-412">[New-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-413">[New-CsMediaConfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-413">[New-CsMediaConfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-414">[New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-414">[New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-415">[New-CsMobilityPolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-415">[New-CsMobilityPolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-416">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-416">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-417">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-417">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-418">[New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-418">[New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-419">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-419">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-420">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-420">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-421">[New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-421">[New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-422">[New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-422">[New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-423">[New-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-423">[New-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-424">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-424">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-425">[New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-425">[New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-426">[New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-426">[New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-427">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-427">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-428">[New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-428">[New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-429">[New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-429">[New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-430">[New-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-430">[New-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-431">[New-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-431">[New-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-432">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-432">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-433">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-433">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-434">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-434">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-435">[New-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-435">[New-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-436">[New-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-436">[New-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-437">[New-CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-437">[New-CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-438">[New-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-438">[New-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-439">[New-CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-439">[New-CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-440">[New-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-440">[New-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-441">[New-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-441">[New-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-442">[New-CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-442">[New-CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-443">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-443">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-444">[New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-444">[New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-445">[New-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-445">[New-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-446">[New-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-446">[New-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-447">[New-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg413065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-447">[New-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg413065(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-448">[New-CsRgsAnswer](https://technet.microsoft.com/library/Gg412812(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-448">[New-CsRgsAnswer](https://technet.microsoft.com/library/Gg412812(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-449">[New-CsRgsCallAction](https://technet.microsoft.com/library/Gg398136(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-449">[New-CsRgsCallAction](https://technet.microsoft.com/library/Gg398136(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-450">[New-CsRgsHoliday](https://technet.microsoft.com/library/Gg398075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-450">[New-CsRgsHoliday](https://technet.microsoft.com/library/Gg398075(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-451">[New-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398403(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-451">[New-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398403(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-452">[New-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398291(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-452">[New-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398291(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-453">[New-CsRgsPrompt](https://technet.microsoft.com/library/Gg398486(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-453">[New-CsRgsPrompt](https://technet.microsoft.com/library/Gg398486(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-454">[New-CsRgsQuestion](https://technet.microsoft.com/library/Gg398186(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-454">[New-CsRgsQuestion](https://technet.microsoft.com/library/Gg398186(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-455">[New-CsRgsQueue](https://technet.microsoft.com/library/Gg398989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-455">[New-CsRgsQueue](https://technet.microsoft.com/library/Gg398989(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-456">[New-CsRgsTimeRange](https://technet.microsoft.com/library/Gg399040(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-456">[New-CsRgsTimeRange](https://technet.microsoft.com/library/Gg399040(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-457">[New-CsRgsWorkflow](https://technet.microsoft.com/library/Gg398246(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-457">[New-CsRgsWorkflow](https://technet.microsoft.com/library/Gg398246(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-458">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-458">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-459">[New-CsServerApplication](https://technet.microsoft.com/library/Gg398096(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-459">[New-CsServerApplication](https://technet.microsoft.com/library/Gg398096(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-460">[New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-460">[New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-461">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-461">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-462">[New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-462">[New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-463">[New-CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-463">[New-CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-464">[New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-464">[New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-465">[New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-465">[New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-466">[New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-466">[New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-467">[New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-467">[New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-468">[New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-468">[New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-469">[New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-469">[New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-470">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-470">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-471">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-471">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-472">[New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-472">[New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-473">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-473">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-474">[New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-474">[New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-475">[New-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-475">[New-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-476">[New-CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-476">[New-CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-477">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-477">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-478">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-478">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-479">[New-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-479">[New-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-480">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-480">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-481">[New-CsUnassignedNumber](https://technet.microsoft.com/library/Gg398651(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-481">[New-CsUnassignedNumber](https://technet.microsoft.com/library/Gg398651(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-482">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-482">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-483">[New-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-483">[New-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-484">[New-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-484">[New-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205072(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-485">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-485">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425849(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-486">[New-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-486">[New-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-487">[New-CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-487">[New-CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-488">[New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-488">[New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-489">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-489">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-490">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-490">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-491">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-491">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-492">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-492">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-493">[New-CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-493">[New-CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-494">[New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-494">[New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-495">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-495">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-496">[New-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-496">[New-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-497">[Publish-CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-497">[Publish-CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-498">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-498">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-499">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-499">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-500">[Remove-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-500">[Remove-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-501">[Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-501">[Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-502">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-502">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-503">[Remove-CsAnnouncement](https://technet.microsoft.com/library/Gg412766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-503">[Remove-CsAnnouncement](https://technet.microsoft.com/library/Gg412766(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-504">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-504">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-505">[Remove-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-505">[Remove-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-506">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-506">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-507">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-507">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-508">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-508">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-509">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-509">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-510">[Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-510">[Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-511">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-511">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-512">[Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-512">[Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-513">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-513">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-514">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-514">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-515">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-515">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-516">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-516">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-517">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-517">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-518">[Remove-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-518">[Remove-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-519">[Remove-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-519">[Remove-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-520">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-520">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-521">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-521">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-522">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-522">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-523">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-523">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-524">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-524">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-525">[Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-525">[Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-526">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-526">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-527">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-527">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-528">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-528">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-529">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-529">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-530">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-530">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-531">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-531">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-532">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-532">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-533">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-533">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-534">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-534">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-535">[Remove-CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-535">[Remove-CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-536">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-536">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-537">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-537">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-538">[Remove-CsExUmContact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-538">[Remove-CsExUmContact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-539">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-539">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-540">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-540">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-541">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-541">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-542">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398211(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-542">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398211(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-543">[Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-543">[Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-544">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-544">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-545">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-545">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-546">[Remove-CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-546">[Remove-CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-547">[Remove-CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-547">[Remove-CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-548">[Remove-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-548">[Remove-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-549">[Remove-CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-549">[Remove-CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-550">[Remove-CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-550">[Remove-CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-551">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-551">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-552">[Remove-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-552">[Remove-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-553">[Remove-CsManagementConnection](https://technet.microsoft.com/library/Gg425803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-553">[Remove-CsManagementConnection](https://technet.microsoft.com/library/Gg425803(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-554">[Remove-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-554">[Remove-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-555">[Remove-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-555">[Remove-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398705(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-556">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-556">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-557">[Remove-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-557">[Remove-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-558">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-558">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-559">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-559">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-560">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-560">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-561">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-561">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-562">[Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-562">[Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-563">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-563">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-564">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-564">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-565">[Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-565">[Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-566">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-566">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-567">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-567">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-568">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-568">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-569">[Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-569">[Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-570">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ205350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-570">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ205350(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-571">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-571">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-572">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-572">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-573">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-573">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-574">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-574">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-575">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-575">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-576">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205301(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-576">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205301(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-577">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-577">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-578">[Remove-CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-578">[Remove-CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-579">[Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-579">[Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-580">[Remove-CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-580">[Remove-CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-581">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-581">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-582">[Remove-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-582">[Remove-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-583">[Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-583">[Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-584">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690028(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-584">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690028(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-585">[Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-585">[Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-586">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-586">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-587">[Remove-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-587">[Remove-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-588">[Remove-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg398969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-588">[Remove-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg398969(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-589">[Remove-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398521(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-589">[Remove-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398521(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-590">[Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398568(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-590">[Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398568(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-591">[Remove-CsRgsQueue](https://technet.microsoft.com/library/Gg398576(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-591">[Remove-CsRgsQueue](https://technet.microsoft.com/library/Gg398576(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-592">[Remove-CsRgsWorkflow](https://technet.microsoft.com/library/Gg398765(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-592">[Remove-CsRgsWorkflow](https://technet.microsoft.com/library/Gg398765(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-593">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-593">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-594">[Remove-CsServerApplication](https://technet.microsoft.com/library/Gg398366(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-594">[Remove-CsServerApplication](https://technet.microsoft.com/library/Gg398366(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-595">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-595">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-596">[Remove-CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-596">[Remove-CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-597">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-597">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-598">[Remove-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-598">[Remove-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703201(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-599">[Remove-CsSlaDelegates](https://technet.microsoft.com/library/Mt703203(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-599">[Remove-CsSlaDelegates](https://technet.microsoft.com/library/Mt703203(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-600">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-600">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-601">[Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-601">[Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-602">[Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-602">[Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-603">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-603">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-604">[Remove-CsTrustedApplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-604">[Remove-CsTrustedApplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-605">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-605">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-606">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-606">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-607">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-607">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-608">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-608">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-609">[Remove-CsUnassignedNumber](https://technet.microsoft.com/library/Gg398209(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-609">[Remove-CsUnassignedNumber](https://technet.microsoft.com/library/Gg398209(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-610">[Remove-CsUserAcp](https://technet.microsoft.com/library/Gg398982(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-610">[Remove-CsUserAcp](https://technet.microsoft.com/library/Gg398982(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-611">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-611">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-612">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-612">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-613">[Remove-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ204629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-613">[Remove-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ204629(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-614">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-614">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-615">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-615">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-616">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg398573(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-616">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg398573(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-617">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-617">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-618">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-618">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-619">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-619">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-620">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-620">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-621">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-621">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-622">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-622">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-623">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-623">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-624">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-624">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-625">[Request-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-625">[Request-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-626">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-626">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-627">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-627">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-628">[REVOKE-CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-628">[Revoke-CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-629">[REVOKE-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-629">[Revoke-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-630">[REVOKE-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-630">[Revoke-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-631">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-631">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-632">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-632">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-633">[Set-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-633">[Set-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-634">[Set-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-634">[Set-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-635">[Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-635">[Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-636">[Set-CsAnnouncement](https://technet.microsoft.com/library/Gg425752(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-636">[Set-CsAnnouncement](https://technet.microsoft.com/library/Gg425752(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-637">[Set-CsApplicationServer](https://technet.microsoft.com/library/Gg398562(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-637">[Set-CsApplicationServer](https://technet.microsoft.com/library/Gg398562(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-638">[Set-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-638">[Set-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-639">[Set-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-639">[Set-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-640">[Set-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-640">[Set-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-641">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-641">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-642">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-642">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-643">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-643">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-644">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-644">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-645">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-645">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-646">[Set-CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-646">[Set-CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-647">[Set-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-647">[Set-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-648">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-648">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-649">[Set-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-649">[Set-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-650">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-650">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-651">[Set-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-651">[Set-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-652">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-652">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-653">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-653">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-654">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-654">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-655">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-655">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-656">[Set-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-656">[Set-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-657">[Set-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-657">[Set-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-658">[Set-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-658">[Set-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-659">[Set-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-659">[Set-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-660">[Set-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-660">[Set-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-661">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-661">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-662">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-662">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-663">[Set-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-663">[Set-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-664">[Set-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-664">[Set-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-665">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-665">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-666">[Set-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-666">[Set-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-667">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-667">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-668">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-668">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-669">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-669">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-670">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-670">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-671">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-671">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-672">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-672">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-673">[Set-CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15)) Set-CsDialPlan</span><span class="sxs-lookup"><span data-stu-id="71929-673">[Set-CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))Set-CsDialPlan</span></span>

  - <span data-ttu-id="71929-674">[Set-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-674">[Set-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-675">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-675">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-676">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-676">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-677">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-677">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-678">[Set-CsExUmContact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-678">[Set-CsExUmContact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-679">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-679">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-680">[Set-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-680">[Set-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-681">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-681">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-682">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-682">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-683">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-683">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-684">[Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-684">[Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-685">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-685">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-686">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-686">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-687">[Set-CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-687">[Set-CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-688">[Set-CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-688">[Set-CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-689">[Set-CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-689">[Set-CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-690">[Set-CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-690">[Set-CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-691">[Set-CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-691">[Set-CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-692">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-692">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-693">[Set-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-693">[Set-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-694">[Set-CsManagementConnection](https://technet.microsoft.com/library/Gg413045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-694">[Set-CsManagementConnection](https://technet.microsoft.com/library/Gg413045(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-695">[Set-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-695">[Set-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-696">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-696">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-697">[Set-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-697">[Set-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-698">[Set-CsMediationServer](https://technet.microsoft.com/library/Gg398213(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-698">[Set-CsMediationServer](https://technet.microsoft.com/library/Gg398213(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-699">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-699">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-700">[Set-CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-700">[Set-CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-701">[Set-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-701">[Set-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-702">[Set-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-702">[Set-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-703">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-703">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-704">[Set-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-704">[Set-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-705">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-705">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-706">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-706">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-707">[Set-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-707">[Set-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-708">[Set-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-708">[Set-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-709">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-709">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-710">[Set-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-710">[Set-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-711">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-711">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-712">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-712">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-713">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-713">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-714">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-714">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-715">[Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-715">[Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-716">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/library/JJ205065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-716">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/library/JJ205065(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-717">[Set-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-717">[Set-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-718">[Set-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-718">[Set-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-719">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-719">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-720">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-720">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-721">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-721">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-722">[Set-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-722">[Set-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-723">[Set-CsPersistentChatState](https://technet.microsoft.com/library/JJ205109(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-723">[Set-CsPersistentChatState](https://technet.microsoft.com/library/JJ205109(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-724">[Set-CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-724">[Set-CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-725">[Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-725">[Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-726">[Set-CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-726">[Set-CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-727">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-727">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-728">[Set-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-728">[Set-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-729">[Set-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-729">[Set-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-730">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-730">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-731">[Set-CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-731">[Set-CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-732">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-732">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-733">[Set-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-733">[Set-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-734">[Set-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-734">[Set-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-735">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-735">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-736">[Set-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-736">[Set-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-737">[Set-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-737">[Set-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425955(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-738">[Set-CsRgsConfiguration](https://technet.microsoft.com/library/Gg425728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-738">[Set-CsRgsConfiguration](https://technet.microsoft.com/library/Gg425728(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-739">[Set-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-739">[Set-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398736(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-740">[Set-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg412929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-740">[Set-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg412929(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-741">[Set-CsRgsQueue](https://technet.microsoft.com/library/Gg412947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-741">[Set-CsRgsQueue](https://technet.microsoft.com/library/Gg412947(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-742">[Set-CsRgsWorkflow](https://technet.microsoft.com/library/Gg425845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-742">[Set-CsRgsWorkflow](https://technet.microsoft.com/library/Gg425845(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-743">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-743">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-744">[Set-CsServerApplication](https://technet.microsoft.com/library/Gg412850(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-744">[Set-CsServerApplication](https://technet.microsoft.com/library/Gg412850(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-745">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-745">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-746">[Set-CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-746">[Set-CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-747">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-747">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-748">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-748">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-749">[Set-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-749">[Set-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-750">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-750">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-751">[Set-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-751">[Set-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-752">[Set-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-752">[Set-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-753">[Set-CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-753">[Set-CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-754">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-754">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-755">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-755">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-756">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-756">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-757">[Set-CsUICulture](https://technet.microsoft.com/library/Gg398354(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-757">[Set-CsUICulture](https://technet.microsoft.com/library/Gg398354(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-758">[Set-CsUnassignedNumber](https://technet.microsoft.com/library/Gg399033(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-758">[Set-CsUnassignedNumber](https://technet.microsoft.com/library/Gg399033(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-759">[Set-CsUser](https://technet.microsoft.com/library/Gg398510(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-759">[Set-CsUser](https://technet.microsoft.com/library/Gg398510(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-760">[Set-CsUserAcp](https://technet.microsoft.com/library/Gg413018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-760">[Set-CsUserAcp](https://technet.microsoft.com/library/Gg413018(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-761">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-761">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-762">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-762">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-763">[Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-763">[Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-764">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-764">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-765">[Set-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205414(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-765">[Set-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205414(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-766">[Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-766">[Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-767">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg412948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-767">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg412948(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-768">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-768">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-769">[Set-CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-769">[Set-CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-770">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-770">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-771">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-771">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-772">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-772">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-773">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-773">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-774">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-774">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-775">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-775">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-776">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-776">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-777">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-777">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-778">[Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-778">[Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-779">[Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-779">[Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-780">[Sync-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-780">[Sync-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-781">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-781">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-782">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-782">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-783">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-783">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-784">[Test-CsAudioConferencingProvider](https://technet.microsoft.com/library/JJ205117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-784">[Test-CsAudioConferencingProvider](https://technet.microsoft.com/library/JJ205117(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-785">[Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-785">[Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-786">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-786">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-787">[Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-787">[Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-788">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-788">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-789">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-789">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-790">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-790">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-791">[Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-791">[Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-792">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-792">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-793">[Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-793">[Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-794">[Test-CsExStorageNotification](https://technet.microsoft.com/library/JJ205331(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-794">[Test-CsExStorageNotification](https://technet.microsoft.com/library/JJ205331(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-795">[Test-CsExUMConnectivity](https://technet.microsoft.com/library/JJ204784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-795">[Test-CsExUMConnectivity](https://technet.microsoft.com/library/JJ204784(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-796">[Test-CsExUMVoiceMail](https://technet.microsoft.com/library/JJ205058(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-796">[Test-CsExUMVoiceMail](https://technet.microsoft.com/library/JJ205058(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-797">[Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-797">[Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-798">[Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-798">[Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-799">[Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-799">[Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-800">[Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-800">[Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-801">[Test-CsInterTrunkRouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-801">[Test-CsInterTrunkRouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-802">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-802">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-803">[Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-803">[Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-804">[Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-804">[Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-805">[Test-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-805">[Test-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-806">[Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-806">[Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-807">[Test-CsMcxP2PIM](https://technet.microsoft.com/library/Hh690020(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-807">[Test-CsMcxP2PIM](https://technet.microsoft.com/library/Hh690020(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-808">[Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-808">[Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-809">[Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-809">[Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-810">[Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-810">[Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-811">[Test-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-811">[Test-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-812">[Test-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-812">[Test-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-813">[Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-813">[Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-814">[Test-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-814">[Test-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-815">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-815">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-816">[Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-816">[Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-817">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-817">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-818">[Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-818">[Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-819">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-819">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-820">[Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-820">[Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-821">[Test-CsUnifiedContactStore](https://technet.microsoft.com/library/JJ204662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-821">[Test-CsUnifiedContactStore](https://technet.microsoft.com/library/JJ204662(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-822">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-822">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-823">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-823">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-824">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-824">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-825">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-825">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-826">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-826">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-827">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-827">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-828">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-828">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-829">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-829">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-830">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-830">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-831">[Test-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-831">[Test-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-832">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-832">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-833">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-833">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-834">[Unlock-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-834">[Unlock-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-835">[UNPUBLISH-CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-835">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-836">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-836">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-837">[Update-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-837">[Update-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-838">[Update-CsTenantMeetingUrl](https://technet.microsoft.com/library/Dn424754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-838">[Update-CsTenantMeetingUrl](https://technet.microsoft.com/library/Dn424754(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-839">[Update-CsUserData](https://technet.microsoft.com/library/JJ205358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-839">[Update-CsUserData](https://technet.microsoft.com/library/JJ205358(v=OCS.15))</span></span>

  - <span data-ttu-id="71929-840">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="71929-840">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

