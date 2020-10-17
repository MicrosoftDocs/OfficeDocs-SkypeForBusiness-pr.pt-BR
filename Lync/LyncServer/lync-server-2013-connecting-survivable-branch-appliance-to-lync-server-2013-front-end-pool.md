---
title: Conectando Aparelho de Filial Persistente ao pool Front End do Lync Server 2013
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
ms.openlocfilehash: b7a637716f1e5b1a2082f694554951d42f36978f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502018"
---
# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Conectando Aparelho de Filial Persistente ao pool Front End do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

Cada aparelho de filial persistente (SBA) é associado a um pool de front-ends, que funciona como um registrador de backup para o SBA. Quando o pool de front-ends é atualizado para o Lync Server 2013, o SBA deve ser desassociado do pool de front-ends enquanto o pool de front-ends é atualizado. Após a atualização do pool de front-ends, o SBA pode ser associado ao pool de front-ends. Isso envolve a exclusão do SBA da topologia no Construtor de Topologia e, então, adicionando o SBA novamente no Construtor de Topologia. Os usuários hospedados no SBA devem ser movidos para outro pool de front-ends antes da remoção do SBA da topologia. Depois que o SBA for adicionado novamente à topologia, tais usuários poderão ser movidos de volta ao SBA.

Essas etapas estão resumidas abaixo:

1.  Mover usuários de filial hospedados no SBA para outro pool de front-ends.

2.  Remova o SBA da sua topologia para desassociar o pool de front-ends existente como registrador de backup.

3.  Atualize o pool de front-ends para o Microsoft Lync Server 2013.

4.  Adicione o SBA novamente à topologia.

5.  Associe o novo pool de front-ends ao SBA como um registrador de backup.

6.  Mova os usuários da ramificação de volta para o SBA.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Adicionar site de filial de dispositivo de filial persistente do Lync Server 2013 à sua topologia](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Adicionar site de filial de dispositivo de filial persistente do Lync Server 2010 à sua topologia](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

