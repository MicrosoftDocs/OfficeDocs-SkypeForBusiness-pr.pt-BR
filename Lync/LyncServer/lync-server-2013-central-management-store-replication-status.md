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

# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Status de replicação do repositório de gerenciamento central no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-01-26_

Quando um administrador faz uma alteração de algum tipo para o Lync Server (por exemplo, quando um administrador cria uma nova política de voz ou altera as configurações de configuração do servidor do catálogo de endereços), essa alteração é registrada no repositório de gerenciamento central. Em seguida, a alteração deve ser duplicada em todos os computadores que estão executando os serviços ou funções de servidor do Lync Server.

Para replicar dados, o Replicador Mestre (executado no Servidor de Gerenciamento Central) cria um instantâneo dos dados de configuração alterados. Uma cópia desse instantâneo é enviada para cada computador que esteja executando serviços do Lync Server ou funções de servidor. Nesses computadores, um agente de replicação recebe o instantâneo e carrega os dados alterados. Em seguida, o agente envia uma mensagem ao Replicador Mestre informando o status recente da replicação.

O cmdlet Get-CsManagementStoreReplicationStatus permite que você verifique o status de replicação de qualquer (ou todos) dos computadores do Lync Server em sua organização.

Quem pode executar este cmdlet? Por padrão, os membros destes grupos estão autorizados a executar o cmdlet Get-CsManagementStoreReplicationStatus localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Para retornar uma lista de todas as funções RBAC às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você tenha criado), execute o seguinte comando no prompt do Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>Confira também


[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

