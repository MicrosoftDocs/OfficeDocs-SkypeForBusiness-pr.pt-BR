---
title: Conectando Aparelho de Filial Persistente ao pool Front-End do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d73806f481cfe7c44a5eb9507d043565765a08f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Conectando Aparelho de Filial Persistente ao pool Front-End do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

Cada aplicativo de ramificação sobreviventes (SBA) está associado a um pool de front-end, que atua como um registrador de backup para o SBA. Quando o pool de front-ends é atualizado para o Lync Server 2013, o SBA deve ser desassociado do pool de front-ends enquanto o pool de front-end é atualizado. Depois que o pool de front-ends é atualizado, o SBA pode ser associado novamente ao pool de front-ends. Isso envolve excluir o SBA da topologia no construtor de topologias e, em seguida, adicionar SBA, novamente, ao construtor de topologias. Os usuários hospedados no SBA devem ser movidos para outro pool de front-end antes da remoção do SBA da topologia. Depois que o SBA é adicionado novamente à topologia, esses usuários podem retornar ao SBA.

Estas etapas estão resumidas abaixo:

1.  Mova os usuários da ramificação hospedados no SBA para outro pool de front-ends.

2.  Remova o SBA da sua topologia para desassociar o pool de front-end existente como registrador de backup.

3.  Atualize o pool de front-ends para o Microsoft Lync Server 2013.

4.  Adicione SBA de volta à sua topologia.

5.  Associe o novo pool de front-ends ao SBA como um registrador de backup.

6.  Mova os usuários da ramificação de volta para o SBA.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Adicionar Aparelho de Filial Persistente do Lync Server 2013 a sua topologia](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Adicionar site de Aparelho de Filial Persistente do Lync Server 2010 a sua topologia](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

