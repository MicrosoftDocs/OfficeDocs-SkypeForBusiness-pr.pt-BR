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
# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Status de replicação do repositório de gerenciamento central no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-01-26_

Quando um administrador faz uma alteração de algum tipo no Lync Server (por exemplo, quando um administrador cria uma nova política de voz ou altera as definições de configuração do servidor do catálogo de endereços), essa alteração é registrada no repositório de gerenciamento central. Por sua vez, a alteração deve ser replicada para todos os computadores que estão executando serviços do Lync Server ou funções de servidor.

Para replicar dados, o mestre replicador (em execução no servidor de gerenciamento central) cria um instantâneo dos dados de configuração alterados. Uma cópia desse instantâneo é enviada para cada computador que está executando os serviços do Lync Server ou funções de servidor. Nesses computadores, um agente de Replicação recebe o instantâneo e carrega os dados alterados. O agente então envia o mestre replicador uma mensagem relatando o status de replicação mais recente.

O cmdlet Get-CsManagementStoreReplicationStatus permite que você verifique o status de replicação de qualquer (ou todos) dos computadores do Lync Server em sua organização.

Quem pode executar este cmdlet? Por padrão, os membros dos seguintes grupos são autorizados a executar o cmdlet Get-CsManagementStoreReplicationStatus localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou sozinho), execute o seguinte comando no prompt do Windows PowerShell:

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

