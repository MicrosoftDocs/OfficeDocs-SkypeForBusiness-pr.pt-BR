---
title: 'Lync Server 2013: solução de problemas de cmdlets e serviços de funções de servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting server roles and services cmdlets
ms:assetid: 03be4cae-bf35-40b2-8e02-477b64afa4c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415628(v=OCS.15)
ms:contentKeyID: 48183268
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c4e8a69a87df5454a9e23cb75d2da85a8ae920
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-server-roles-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2fcef-102">Solução de problemas de cmdlets de serviços e funções de servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fcef-102">Troubleshooting server roles and services cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fcef-103">_**Tópico da última modificação:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="2fcef-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="2fcef-104">Os cmdlets de solução de problemas fornecem diferentes maneiras de verificar se o Microsoft Lync Server 2013 está funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="2fcef-104">The troubleshooting cmdlets provide different ways to verify that Microsoft Lync Server 2013 is working as expected.</span></span> <span data-ttu-id="2fcef-105">Por exemplo, os cmdlets do CsHealthMonitoringConfiguration permitem configurar contas de teste para os grupos de registrador e diretor.</span><span class="sxs-lookup"><span data-stu-id="2fcef-105">For example, the CsHealthMonitoringConfiguration cmdlets enable you to set up test accounts for Registrar and Director pools.</span></span> <span data-ttu-id="2fcef-106">Em seguida, você pode usar essas contas de teste para verificar se os usuários podem concluir com êxito tarefas comuns, como fazer logon no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado na rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="2fcef-106">In turn, you can then use those test accounts to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2fcef-107">Para obter informações adicionais sobre cmdlets, consulte o blog&nbsp;do Lync Server do <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>Windows PowerShell em.</span><span class="sxs-lookup"><span data-stu-id="2fcef-107">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="2fcef-108">O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="2fcef-108">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="server-roles-and-services-cmdlets"></a><span data-ttu-id="2fcef-109">Cmdlets de serviços e funções de servidor</span><span class="sxs-lookup"><span data-stu-id="2fcef-109">Server Roles and Services Cmdlets</span></span>

<span data-ttu-id="2fcef-110">Veja a seguir uma lista de cmdlets relacionados diretamente à solução de problemas de funções e serviços do servidor:</span><span class="sxs-lookup"><span data-stu-id="2fcef-110">The following is a list of cmdlets that relate directly to troubleshooting server roles and services:</span></span>

<span data-ttu-id="2fcef-111">**Solução de problemas de funções e serviços do servidor**</span><span class="sxs-lookup"><span data-stu-id="2fcef-111">**Troubleshooting Server Roles and Services**</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-112">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-112">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-113">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-113">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2fcef-114">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-114">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-115">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-115">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-116">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-116">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-117">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-117">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2fcef-118">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-118">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-119">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-119">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-120">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-120">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-121">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-121">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2fcef-122">[New-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-122">[New-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2fcef-123">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-123">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-124">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-124">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-125">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-125">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2fcef-126">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fcef-126">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

