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
ms.openlocfilehash: 1a13a7d618b7d7f8883d43e6aed7ac456bb5ab6c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Adicionar ou remover um servidor front-end no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-01-21_

Ao adicionar um servidor de Front End a um pool, ou remover um servidor de Front End de um pool, você precisará reiniciar o pool. Para evitar interrupção do serviço aos usuários, siga o procedimento a seguir ao remover ou adicionar um servidor de Front End.

<div>


> [!NOTE]  
> Se você estiver adicionando novos servidores ao pool, atualize seus servidores de pool novos para que estejam no mesmo nível de atualização cumulativa que os servidores existentes no pool.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>Para adicionar ou remover servidores de front-end

1.  Se estiver removendo servidores de Front End, primeiro interrompa novas conexões a esses servidores. Para fazer isso, é possível usar o seguinte cmdlet:
    
        Stop-CsWindowsServices -Graceful

2.  Quando os servidores sendo removidos não têm sessões atuais, interrompa os serviços do Lync Server neles.

3.  Abra o Construtor de Topologias, e adiciona ou remova os servidores necessários.

4.  Publique a topologia.

5.  Se o pool saiu de dois servidores front-end para mais de dois ou de mais de dois servidores para exatamente dois, você precisará digitar o seguinte cmdlet:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Se o pool tinha três ou mais servidores, então pelo menos três desses servidores deve ser executado ao digitar esse cmdlet.

6.  Reinicie todos os servidores front-end no pool, um de cada vez.

</div>

</div>

<span> </span>

</div>

</div>

</div>

