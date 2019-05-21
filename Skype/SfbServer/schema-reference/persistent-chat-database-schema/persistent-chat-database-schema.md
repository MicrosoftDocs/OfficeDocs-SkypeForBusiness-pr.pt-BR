---
title: Esquema do banco de dados de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Isso documenta o esquema do banco de dados de chat persistente no Skype for Business Server.
ms.openlocfilehash: 9a3e09a03f764f8866865e08259cbaac12a1c554
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295612"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="57780-103">Esquema do banco de dados de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="57780-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="57780-104">Isso documenta o esquema do banco de dados de chat persistente no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="57780-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="57780-105">O banco de dados de chat persistente refere-se ao banco de dados correspondente às funções de servidor back-end do Skype for Business Server **PersistentChatStore** (correspondente ao banco de dados do MGC) e **PersistentChatComplianceStore** (correspondente à banco de dados do mgccomp).</span><span class="sxs-lookup"><span data-stu-id="57780-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="57780-106">O objetivo de publicar esse esquema é habilitá-lo para criar consultas e obter algumas ideias para criar relatórios úteis sobre uso de chat, salas ativas, principais pôsters e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="57780-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="57780-107">Reservamo-nos o direito de desenvolver este esquema.</span><span class="sxs-lookup"><span data-stu-id="57780-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="57780-108">A Microsoft não faz nenhuma garantia para manter a compatibilidade com versões anteriores do esquema publicado.</span><span class="sxs-lookup"><span data-stu-id="57780-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="57780-109">Siga estas práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="57780-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="57780-110">Não há\* suporte para Select//is porque a lista de colunas pode aumentar.</span><span class="sxs-lookup"><span data-stu-id="57780-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="57780-111">Não há suporte para modificações de esquema geradas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="57780-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="57780-112">Não há suporte para operações de gravação.</span><span class="sxs-lookup"><span data-stu-id="57780-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="57780-113">Teste todas as consultas que você cria em bancos de dados de tamanho representativo para ter certeza de que as consultas podem ser executadas em um nível para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="57780-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="57780-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="57780-114">In this section</span></span>

- [<span data-ttu-id="57780-115">Tabelas de lista de Servidores de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="57780-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="57780-116">Lista de tabelas de conformidade do servidor de chat persistente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="57780-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="57780-117">Detalhes da tabela do Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="57780-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="57780-118">Amostragem de consultas de banco de dados de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="57780-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

