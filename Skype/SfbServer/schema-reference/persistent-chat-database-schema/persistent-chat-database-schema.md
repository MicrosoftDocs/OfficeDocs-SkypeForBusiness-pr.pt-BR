---
title: Esquema do banco de dados de Chat Persistente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Documenta o esquema do banco de dados de Chat persistente no Skype para Business Server.
ms.openlocfilehash: 37b22077157def7ea25a5cf70b23a0272a58956e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212688"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="b0ce0-103">Esquema do banco de dados de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="b0ce0-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="b0ce0-104">Documenta o esquema do banco de dados de Chat persistente no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b0ce0-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="b0ce0-105">O banco de dados de Chat persistente refere-se ao banco de dados correspondente para o Skype para funções de negócios Server servidor Back-End **PersistentChatStore** (correspondente ao banco de dados mgc) e **PersistentChatComplianceStore** (correspondente para o banco de dados mgccomp).</span><span class="sxs-lookup"><span data-stu-id="b0ce0-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="b0ce0-106">O objetivo deste esquema de publicação é para habilitá-lo construir consultas e obter algumas ideias para criar relatórios úteis ao redor do uso de chat, salas ativas, cartazes superior e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="b0ce0-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b0ce0-107">Reservamos o direito de evoluir este esquema.</span><span class="sxs-lookup"><span data-stu-id="b0ce0-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="b0ce0-108">A Microsoft não faz nenhuma garantia para manter compatibilidade total com esse esquema publicada.</span><span class="sxs-lookup"><span data-stu-id="b0ce0-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="b0ce0-109">Siga estas práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="b0ce0-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="b0ce0-110">Nenhum selecione\* / / é suportado, pois a lista de colunas pode crescer.</span><span class="sxs-lookup"><span data-stu-id="b0ce0-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="b0ce0-111">Nenhuma modificação de esquema gerado pelo usuário é suportadas.</span><span class="sxs-lookup"><span data-stu-id="b0ce0-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="b0ce0-112">Nenhuma operações de gravação são suportadas.</span><span class="sxs-lookup"><span data-stu-id="b0ce0-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="b0ce0-113">Teste quaisquer consultas que você crie em bancos de dados de tamanho representativo para certificar-se de que as consultas podem ser executadas em um nível que atenda às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="b0ce0-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="b0ce0-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b0ce0-114">In this section</span></span>

- [<span data-ttu-id="b0ce0-115">Tabelas de lista de Servidores de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="b0ce0-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="b0ce0-116">Lista das tabelas de conformidade do servidor de Chat persistente no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b0ce0-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="b0ce0-117">Detalhes da tabela do Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="b0ce0-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="b0ce0-118">Amostragem de consultas de banco de dados de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="b0ce0-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

