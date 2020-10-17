---
title: Verificar a conectividade entre servidores internos e servidores de borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a170ac21c89bd405ad0406830c00feabbde5434
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518648"
---
# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>Verificar a conectividade entre servidores internos e servidores de borda no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

No Lync Server 2013, um assistente de validação separado estava disponível para ajudar a validar a conectividade entre servidores de borda e servidores internos. No Lync Server 2013 a validação da conectividade é feita automaticamente quando você instala seus servidores de borda.

Você pode validar a replicação de informações de configuração para a borda executando o cmdlet **Get-CsManagementStoreReplicationStatus** do Windows PowerShell no computador interno no qual o repositório de gerenciamento central está localizado (ou qualquer computador ingressado no domínio em que o Lync Server 2013 Core Components (OcsCore.msi) está instalado. Os resultados iniciais podem indicar o status como "Falso" e não "Verdadeiro" para replicação. Se assim, execute o cmdlet **Invoke-CsManagementStoreReplication** e permita que o tempo necessário para a replicação seja concluído antes de executar o **Get-CsManagementStoreReplicationStatus** novamente.

É possível verificar a conectividade de usuário externo separadamente, inclusive o uso do Analisador de Conectividade Remota do Office Communications Server para verificar a conectividade de usuários remotos. Para obter detalhes, consulte [Verify Connectivity for External Users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).

</div>

<span> </span>

</div>

</div>

</div>

