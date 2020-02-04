---
title: Cenário de migração padrão - nível alto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68ff7110cc7e14ccc76ab7d0c0125e723477934a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>Cenário de migração padrão - nível alto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-30_

Use os itens a seguir como ponto de partida ao migrar o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Grupo chat para o Lync Server 2013, servidor de chat persistente. O caminho de migração padrão do Lync Server 2013 é o seguinte:

  - Sua organização implantou anteriormente o Lync Server 2010, o chat em grupo ou o Office Communications Server 2007 R2 para o chat em grupo e você deseja implantar o Lync Server 2013, servidor de chat persistente.

  - Implante o Lync Server 2013 e, em seguida, implante os pools do servidor de chat persistente.

  - Prepare e planeje a migração de salas de chat persistentes e determine um tempo apropriado para desligar o sistema para a migração.

  - Execute os cmdlets do Windows PowerShell para a migração (**Export-CsPersistentChatData** e **Import-CsPersistentChatData**) para mover o conteúdo para o servidor de chat persistente.

  - Verifique se a migração foi bem-sucedida.

  - Descomissionar sua implantação herdada.

  - Configure o servidor de chat persistente para que os clientes herdados possam se conectar ao Lync Server 2013, servidor de chat persistente. Isso é necessário porque demora tempo para implantar novos clientes, e você deseja permitir que os usuários existentes com clientes herdados tenham acesso às suas salas de chat o mais rápido possível.

  - Implante novos clientes e continue a garantir que trabalhadores com o chat de grupo herdado possam acessar suas salas de chat.

</div>

<span> </span>

</div>

</div>

</div>

