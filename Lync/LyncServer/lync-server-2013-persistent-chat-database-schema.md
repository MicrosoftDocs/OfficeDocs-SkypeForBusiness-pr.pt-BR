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
ms.openlocfilehash: a18cd17686133219ccc60d5e85fd149df190665a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="2e2f3-102">Esquema de banco de dados de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e2f3-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e2f3-103">_**Última modificação do tópico:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="2e2f3-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="2e2f3-104">Isso documenta o esquema do banco de dados de chat persistente no software de comunicações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="2e2f3-105">O banco de dados de chat persistente refere-se ao banco de dados correspondente às funções de servidor back-end do Lync Server 2013 **PersistentChatStore** (correspondente ao banco de dados MGC) e **PersistentChatComplianceStore** (correspondente ao banco de dados do mgccomp).</span><span class="sxs-lookup"><span data-stu-id="2e2f3-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="2e2f3-106">O objetivo da publicação desse esquema é permitir que você crie consultas e obtenha algumas ideias sobre a criação de relatórios úteis sobre uso de chat, salas ativas, pôsteres principais e etc.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2e2f3-p102">Reservamo-nos o direito de desenvolver este esquema. A Microsoft não garante manter compatibilidade com versões anteriores completa para esse esquema publicado.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="2e2f3-109">Sigas estas práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="2e2f3-109">Follow these best practices:</span></span>

  - <span data-ttu-id="2e2f3-110">Não há\* suporte para Select//is porque a lista de colunas pode aumentar.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="2e2f3-111">Nenhuma modificação de esquema gerado pelo usuário é suportada.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="2e2f3-112">Nenhuma operações de gravação é suportada.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-112">No write operations are supported.</span></span>

  - <span data-ttu-id="2e2f3-113">Teste quaisquer consultas que você crie em bancos de dados de tamanho representativo para certificar-se de que as consultas podem ser executadas em um nível que atenda às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2e2f3-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2e2f3-114">In This Section</span></span>

  - [<span data-ttu-id="2e2f3-115">Lista de tabelas do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e2f3-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="2e2f3-116">Lista de tabelas de conformidade do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e2f3-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="2e2f3-117">Detalhes da tabela do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e2f3-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="2e2f3-118">Exemplo de consultas de banco de dados de chat persistente para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e2f3-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

