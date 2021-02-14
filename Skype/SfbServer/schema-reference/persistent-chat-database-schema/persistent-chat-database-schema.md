---
title: Esquema do banco de dados de Chat Persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Isso documenta o esquema do banco de dados de Chat Persistente no Skype for Business Server.
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809871"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="c52ef-103">Esquema do banco de dados de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="c52ef-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="c52ef-104">Isso documenta o esquema do banco de dados de Chat Persistente no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c52ef-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="c52ef-105">O banco de dados de Chat Persistente refere-se ao banco de dados correspondente às funções servidor back-end do Skype for Business Server **PersistentChatStore** (correspondente ao banco de dados mgc) e **PersistentChatComplianceStore** (correspondente ao banco de dados mgccomp).</span><span class="sxs-lookup"><span data-stu-id="c52ef-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="c52ef-106">O objetivo da publicação desse esquema é permitir que você crie consultas e obtenha algumas ideias sobre a criação de relatórios úteis sobre uso de chat, salas ativas, pôsteres principais e etc.</span><span class="sxs-lookup"><span data-stu-id="c52ef-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c52ef-p102">Reservamo-nos o direito de desenvolver este esquema. A Microsoft não garante manter compatibilidade com versões anteriores completa para esse esquema publicado.</span><span class="sxs-lookup"><span data-stu-id="c52ef-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="c52ef-109">Sigas estas práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="c52ef-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="c52ef-110">Nenhum SELECT \* // é suportado porque a lista de colunas pode crescer.</span><span class="sxs-lookup"><span data-stu-id="c52ef-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="c52ef-111">Nenhuma modificação de esquema gerado pelo usuário é suportada.</span><span class="sxs-lookup"><span data-stu-id="c52ef-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="c52ef-112">Nenhuma operações de gravação é suportada.</span><span class="sxs-lookup"><span data-stu-id="c52ef-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="c52ef-113">Teste quaisquer consultas que você crie em bancos de dados de tamanho representativo para certificar-se de que as consultas podem ser executadas em um nível que atenda às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="c52ef-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="c52ef-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c52ef-114">In this section</span></span>

- [<span data-ttu-id="c52ef-115">Tabelas de lista de Servidores de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="c52ef-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="c52ef-116">Lista de tabelas de conformidade do Servidor de Chat Persistente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c52ef-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="c52ef-117">Detalhes da tabela do Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="c52ef-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="c52ef-118">Amostragem de consultas de banco de dados de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="c52ef-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

