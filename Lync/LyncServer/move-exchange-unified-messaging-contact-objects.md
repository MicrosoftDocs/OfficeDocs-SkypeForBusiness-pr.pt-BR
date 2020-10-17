---
title: Mover objetos de contato de Unificação de mensagens do Exchange
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42abb209eaf59be66c8516401616dcac4f1c94ad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500288"
---
# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="1708f-102">Mover objetos de contato de Unificação de mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="1708f-102">Move Exchange Unified Messaging Contact objects</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1708f-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1708f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1708f-104">Para migrar objetos de contato do atendedor automático (AA) e de acesso do assinante (SA) para a nova implantação do Lync Server 2013, primeiro você move os objetos da implantação herdada do Office Communications Server 2007 R2 para a nova implantação do Lync Server 2013 usando os cmdlets **Get-CsExUmContact** e **move-CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="1708f-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="1708f-105">No servidor do Exchange, execute o script **ExchUCUtil** do Windows PowerShell para fazer o seguinte para o pool do Lync recém implantado:</span><span class="sxs-lookup"><span data-stu-id="1708f-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="1708f-106">Adicioná-lo aos gateways IP de unificação de mensagens</span><span class="sxs-lookup"><span data-stu-id="1708f-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="1708f-107">Adicioná-lo aos grupos de busca de unificação de mensagens</span><span class="sxs-lookup"><span data-stu-id="1708f-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1708f-p102">Para usar os cmdlets <STRONG>Get-CsExUmContact</STRONG> e <STRONG>Move-CsExUmContact</STRONG>, é preciso ser membro do grupo RTCUniversalUserAdmins e ter permissão de OU (unidade organizacional) para a OU em que os objetos de contato estão armazenados. A permissão de OU pode ser concedida usando o cmdlet <STRONG>Grant-OUPermission</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1708f-p102">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored. OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="1708f-110">Para mover objetos de contato usando o Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="1708f-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="1708f-111">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1708f-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="1708f-112">Para cada pool registrado com UM do Exchange (onde pool1.contoso.net é um pool da implantação do Office Communications Server 2007 R2 e pool2.contoso.net é o pool da implantação do Lync Server 2013) na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1708f-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="1708f-113">Para verificar se os objetos de contato foram movidos, execute o cmdlet **Get-CsExumContact** e confirme se **RegistrarPool** indica agora o novo pool.</span><span class="sxs-lookup"><span data-stu-id="1708f-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="1708f-114">Para executar o script ExchUCUtil Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1708f-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="1708f-115">Faça logon no servidor UM do Exchange como usuário com privilégios de administrador de organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="1708f-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="1708f-116">Navegue até o script ExchUCUtil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1708f-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="1708f-117">No Exchange 2007, o ExchUCUtil.ps1 está localizado em: **% arquivos de programas% \\ scripts do Microsoft \\ Exchange Server \\ \\ExchUCUtil.ps1**</span><span class="sxs-lookup"><span data-stu-id="1708f-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="1708f-118">No Exchange 2010, o ExchUCUtil.ps1 está localizado em: **% arquivos de programas% \\ scripts do Microsoft \\ Exchange Server \\ v14 \\ \\ExchUCUtil.ps1**</span><span class="sxs-lookup"><span data-stu-id="1708f-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="1708f-119">Se o Exchange estiver implantado em uma única floresta, digite:</span><span class="sxs-lookup"><span data-stu-id="1708f-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="1708f-120">Se o Exchange estiver implantado em várias florestas, digite:</span><span class="sxs-lookup"><span data-stu-id="1708f-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="1708f-121">onde FQDN da floresta especifica a floresta na qual o Lync Server 2013 é implantado.</span><span class="sxs-lookup"><span data-stu-id="1708f-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1708f-122">Certifique-se de reiniciar o serviço de <STRONG>Front-End do Lync Server</STRONG> (rtcsrv.exe) <EM>depois</EM> de executar exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="1708f-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="1708f-123">Caso contrário, o Lync Server 2013 não detectará a Unificação de mensagens na topologia.</span><span class="sxs-lookup"><span data-stu-id="1708f-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

