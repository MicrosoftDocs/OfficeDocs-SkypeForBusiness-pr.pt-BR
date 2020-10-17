---
title: 'Lync Server 2013: status de replicação do repositório de gerenciamento central'
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
ms.openlocfilehash: b30b96ce505848e0cb1ec426d959b4c004ddde04
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533398"
---
# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="1deb2-102">Status de replicação do repositório de gerenciamento central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1deb2-102">Central management store replication status in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1deb2-103">_**Última modificação do tópico:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="1deb2-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="1deb2-104">Quando um administrador faz uma alteração de algum tipo no Lync Server (por exemplo, quando um administrador cria uma nova política de voz ou altera as definições de configuração do servidor do catálogo de endereços), essa alteração é registrada no repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="1deb2-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="1deb2-105">Por sua vez, a alteração deve ser replicada para todos os computadores que estão executando serviços do Lync Server ou funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="1deb2-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="1deb2-106">Para replicar dados, o mestre replicador (em execução no servidor de gerenciamento central) cria um instantâneo dos dados de configuração alterados.</span><span class="sxs-lookup"><span data-stu-id="1deb2-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="1deb2-107">Uma cópia desse instantâneo é enviada para cada computador que está executando os serviços do Lync Server ou funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="1deb2-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="1deb2-108">Nesses computadores, um agente de Replicação recebe o instantâneo e carrega os dados alterados.</span><span class="sxs-lookup"><span data-stu-id="1deb2-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="1deb2-109">O agente então envia o mestre replicador uma mensagem relatando o status de replicação mais recente.</span><span class="sxs-lookup"><span data-stu-id="1deb2-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="1deb2-110">O cmdlet Get-CsManagementStoreReplicationStatus permite que você verifique o status de replicação de qualquer (ou todos) dos computadores do Lync Server em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1deb2-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="1deb2-111">Quem pode executar este cmdlet?</span><span class="sxs-lookup"><span data-stu-id="1deb2-111">Who can run this cmdlet?</span></span> <span data-ttu-id="1deb2-112">Por padrão, os membros dos seguintes grupos são autorizados a executar o cmdlet Get-CsManagementStoreReplicationStatus localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1deb2-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="1deb2-113">Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou sozinho), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1deb2-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="1deb2-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="1deb2-114">See Also</span></span>


[<span data-ttu-id="1deb2-115">Get-CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="1deb2-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

