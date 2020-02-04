---
title: 'Lync Server 2013: Esquema do banco de dados de Chat Persistente'
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
ms.openlocfilehash: 73f3b21fe8ea7f9fc71aa5432a601e9fa3ad2425
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="220b5-102">Esquema do banco de dados de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="220b5-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="220b5-103">_**Tópico da última modificação:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="220b5-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="220b5-104">Isso documenta o esquema do banco de dados de chat persistente no software de comunicação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="220b5-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="220b5-105">O banco de dados de chat persistente refere-se ao banco de dados correspondente às funções de servidor back-end **PersistentChatStore** do Lync Server 2013 (correspondente ao banco de dados do MGC) e **PersistentChatComplianceStore** (correspondente ao banco de dados do mgccomp).</span><span class="sxs-lookup"><span data-stu-id="220b5-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="220b5-106">O objetivo de publicar esse esquema é habilitá-lo para criar consultas e obter algumas ideias para criar relatórios úteis sobre uso de chat, salas ativas, principais pôsters e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="220b5-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="220b5-107">Reservamo-nos o direito de desenvolver este esquema.</span><span class="sxs-lookup"><span data-stu-id="220b5-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="220b5-108">A Microsoft não faz nenhuma garantia para manter a compatibilidade com versões anteriores do esquema publicado.</span><span class="sxs-lookup"><span data-stu-id="220b5-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="220b5-109">Siga estas práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="220b5-109">Follow these best practices:</span></span>

  - <span data-ttu-id="220b5-110">Não há\* suporte para Select//is porque a lista de colunas pode aumentar.</span><span class="sxs-lookup"><span data-stu-id="220b5-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="220b5-111">Não há suporte para modificações de esquema geradas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="220b5-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="220b5-112">Não há suporte para operações de gravação.</span><span class="sxs-lookup"><span data-stu-id="220b5-112">No write operations are supported.</span></span>

  - <span data-ttu-id="220b5-113">Teste todas as consultas que você cria em bancos de dados de tamanho representativo para ter certeza de que as consultas podem ser executadas em um nível para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="220b5-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="220b5-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="220b5-114">In This Section</span></span>

  - [<span data-ttu-id="220b5-115">Tabelas de lista de Servidores de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="220b5-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="220b5-116">Lista de tabelas de conformidade do Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="220b5-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="220b5-117">Detalhes da tabela do Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="220b5-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="220b5-118">Amostragem de consultas de banco de dados de Chat Persistente para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="220b5-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

