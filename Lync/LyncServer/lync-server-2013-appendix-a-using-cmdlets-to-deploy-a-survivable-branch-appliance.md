---
title: 'Lync Server 2013: Anexo A: Usando cmdlets para implantar uma Aparelho de Filial Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9541e6cb63cee91a6bfd1072695fb3ce09a0134
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="2ec83-102">Anexo A: Usando cmdlets para implantar uma Aparelho de Filial Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ec83-102">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ec83-103">_**Tópico da última modificação:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="2ec83-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="2ec83-104">Este tópico descreve como implantar um aparelho de ramificação sobreviventes usando o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ec83-104">This topic describes how to deploy a Survivable Branch Appliance using the Lync Server Management Shell.</span></span> <span data-ttu-id="2ec83-105">Execute este procedimento no site central.</span><span class="sxs-lookup"><span data-stu-id="2ec83-105">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a><span data-ttu-id="2ec83-106">Para implantar um aparelho de ramificação sobreviventes remotamente</span><span class="sxs-lookup"><span data-stu-id="2ec83-106">To deploy a Survivable Branch Appliance remotely</span></span>

1.  <span data-ttu-id="2ec83-107">Siga o procedimento em [adicionar sites de filiais à sua topologia no Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) para adicionar um novo site de filial.</span><span class="sxs-lookup"><span data-stu-id="2ec83-107">Follow the procedure in [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) to add a new branch site.</span></span>

2.  <span data-ttu-id="2ec83-108">Ingresse no site de filial para o domínio.</span><span class="sxs-lookup"><span data-stu-id="2ec83-108">Join the branch site to the domain.</span></span>

3.  <span data-ttu-id="2ec83-109">Adicione o grupo RTCUniversalSBATechnicians ao grupo Administradores local.</span><span class="sxs-lookup"><span data-stu-id="2ec83-109">Add the RTCUniversalSBATechnicians group to the local Administrators group.</span></span>

4.  <span data-ttu-id="2ec83-110">Reinicie o servidor e faça logon como membro do grupo RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="2ec83-110">Restart the server, and log on to it as a member of the RTCUniversalSBATechnicians group.</span></span>

5.  <span data-ttu-id="2ec83-111">No Shell de gerenciamento do Lync Server, digite os seguintes comandos, substituindo os espaços reservados pelas informações corretas para a sua organização:</span><span class="sxs-lookup"><span data-stu-id="2ec83-111">In the Lync Server Management Shell, type the following commands, replacing the placeholders with the correct information for your organization:</span></span>
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

