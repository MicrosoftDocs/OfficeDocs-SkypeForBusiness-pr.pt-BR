---
title: 'Lync Server 2013: esquema de banco de dados de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e84ffc52b64823fcf1efd1213d0084a017e506f9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Esquema de banco de dados de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-18_

Isso documenta o esquema do banco de dados de chat persistente no software de comunicações do Lync Server 2013.

O banco de dados de chat persistente refere-se ao banco de dados correspondente às funções de servidor back-end do Lync Server 2013 **PersistentChatStore** (correspondente ao banco de dados MGC) e **PersistentChatComplianceStore** (correspondente ao banco de dados do mgccomp). O objetivo da publicação desse esquema é permitir que você crie consultas e obtenha algumas ideias sobre a criação de relatórios úteis sobre uso de chat, salas ativas, pôsteres principais e etc.

<div>


> [!IMPORTANT]  
> Reservamo-nos o direito de desenvolver este esquema. A Microsoft não garante manter compatibilidade com versões anteriores completa para esse esquema publicado.



</div>

Sigas estas práticas recomendadas:

  - Não há\* suporte para Select//is porque a lista de colunas pode aumentar.

  - Nenhuma modificação de esquema gerado pelo usuário é suportada.

  - Nenhuma operações de gravação é suportada.

  - Teste quaisquer consultas que você crie em bancos de dados de tamanho representativo para certificar-se de que as consultas podem ser executadas em um nível que atenda às suas necessidades.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Lista de tabelas do servidor de chat persistente no Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lista de tabelas de conformidade do servidor de chat persistente no Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Detalhes da tabela do servidor de chat persistente no Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Exemplo de consultas de banco de dados de chat persistente para Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

