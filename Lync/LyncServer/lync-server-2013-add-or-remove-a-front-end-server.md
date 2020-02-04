---
title: 'Lync Server 2013: Adicionar ou remover um servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 078c3d8eed34e7fb6fd98d2d7c12014b87a0497b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Add or remove a Front End Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-01-21_

Ao adicionar um servidor front-end a um pool ou remover um servidor front-end de um pool, você precisará reiniciar o pool. Para evitar qualquer interrupção do serviço para os usuários, use o procedimento a seguir ao adicionar ou remover um servidor front-end.

<div>


> [!NOTE]  
> Se estiver adicionando novos servidores ao pool, atualize os novos servidores do pool no mesmo nível de Atualização Cumulativa dos servidores existentes no Pool.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>Para adicionar ou remover servidores de front-end

1.  Se você estiver removendo qualquer servidor front-end, primeiro interrompa novas conexões para esses servidores. Para fazer isso, é possível usar o seguinte cmdlet:
    
        Stop-CsWindowsServices -Graceful

2.  Quando os servidores que estão sendo removidos não tiverem sessões atuais, interrompa os serviços do Lync Server.

3.  Abra o construtor de topologias e adicione ou remova os servidores necessários.

4.  Publique a topologia.

5.  Se o pool deixou de ter dois servidores front-end para mais de dois ou sair de mais de dois servidores para exatamente dois, você precisará digitar o seguinte cmdlet:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Se o pool tiver três ou mais servidores, pelo menos três desses servidores deverão estar em execução quando você digitar esse cmdlet.

6.  Reinicie todos os servidores front-end do pool, um de cada vez.

</div>

</div>

<span> </span>

</div>

</div>

</div>

