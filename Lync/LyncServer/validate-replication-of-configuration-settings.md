---
title: Validar a replicação de definições de configuração
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf08d920983ef4463f9e8236f6c9e458f120074b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="70a28-102">Validar a replicação de definições de configuração</span><span class="sxs-lookup"><span data-stu-id="70a28-102">Validate replication of configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70a28-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="70a28-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="70a28-104">Você pode validar a replicação de informações de configuração para o servidor de borda executando o cmdlet do Lync Server 2013 **Get-CsManagementStoreReplicationStatus** no computador interno no qual o repositório de gerenciamento central está localizado ou em qualquer computador que ingressou no domínio em que o Lync Server 2013 Core Components está instalado.</span><span class="sxs-lookup"><span data-stu-id="70a28-104">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="70a28-105">Os resultados iniciais podem indicar o status como "Falso" e não "Verdadeiro" para replicação.</span><span class="sxs-lookup"><span data-stu-id="70a28-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="70a28-106">Se for o caso, execute o cmdlet **Invoke-CsManagementStoreReplication** e permita que a replicação seja concluída antes de executar o cmdlet **Get-CsManagementStoreReplicationStatus** novamente.</span><span class="sxs-lookup"><span data-stu-id="70a28-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

