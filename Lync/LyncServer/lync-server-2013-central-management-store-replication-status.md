---
title: 'Lync Server 2013: Status de replicação do repositório de gerenciamento central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4212e8616916f6a2a256530a7a0b74c9811f166d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="03568-102">Status de replicação do repositório de gerenciamento central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03568-102">Central management store replication status in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03568-103">_**Tópico da última modificação:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="03568-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="03568-104">Quando um administrador faz uma alteração de algum tipo para o Lync Server (por exemplo, quando um administrador cria uma nova política de voz ou altera as configurações de configuração do servidor do catálogo de endereços), essa alteração é registrada no repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="03568-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="03568-105">Em seguida, a alteração deve ser duplicada em todos os computadores que estão executando os serviços ou funções de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="03568-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="03568-106">Para replicar dados, o Replicador Mestre (executado no Servidor de Gerenciamento Central) cria um instantâneo dos dados de configuração alterados.</span><span class="sxs-lookup"><span data-stu-id="03568-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="03568-107">Uma cópia desse instantâneo é enviada para cada computador que esteja executando serviços do Lync Server ou funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="03568-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="03568-108">Nesses computadores, um agente de replicação recebe o instantâneo e carrega os dados alterados.</span><span class="sxs-lookup"><span data-stu-id="03568-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="03568-109">Em seguida, o agente envia uma mensagem ao Replicador Mestre informando o status recente da replicação.</span><span class="sxs-lookup"><span data-stu-id="03568-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="03568-110">O cmdlet Get-CsManagementStoreReplicationStatus permite que você verifique o status de replicação de qualquer (ou todos) dos computadores do Lync Server em sua organização.</span><span class="sxs-lookup"><span data-stu-id="03568-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="03568-111">Quem pode executar este cmdlet?</span><span class="sxs-lookup"><span data-stu-id="03568-111">Who can run this cmdlet?</span></span> <span data-ttu-id="03568-112">Por padrão, os membros destes grupos estão autorizados a executar o cmdlet Get-CsManagementStoreReplicationStatus localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="03568-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="03568-113">Para retornar uma lista de todas as funções RBAC às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você tenha criado), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03568-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="03568-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="03568-114">See Also</span></span>


[<span data-ttu-id="03568-115">Get-CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="03568-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

