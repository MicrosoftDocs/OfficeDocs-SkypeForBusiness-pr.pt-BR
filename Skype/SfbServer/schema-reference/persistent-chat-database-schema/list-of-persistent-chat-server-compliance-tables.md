---
title: Lista das tabelas de conformidade do servidor de Chat persistente no Skype para Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: O esquema de banco de dados de conformidade Chat persistente consiste as tabelas a seguir.
ms.openlocfilehash: 18c35cc71da43dcf25bb477e81a2471b483ee86d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212695"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="cab80-103">Lista das tabelas de conformidade do servidor de Chat persistente no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="cab80-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="cab80-104">O esquema de banco de dados de conformidade Chat persistente consiste as tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="cab80-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="cab80-105">Lista das tabelas de conformidade do servidor de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="cab80-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="cab80-106">**Tabela**</span><span class="sxs-lookup"><span data-stu-id="cab80-106">**Table**</span></span>|<span data-ttu-id="cab80-107">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cab80-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="cab80-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="cab80-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="cab80-109">Contém eventos de conformidade que ainda não foram processados pelo adaptador configurado.</span><span class="sxs-lookup"><span data-stu-id="cab80-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="cab80-110">Esta tabela inclui eventos de bate-papo persistente relacionados, como mensagens de chat e downloads de arquivo.</span><span class="sxs-lookup"><span data-stu-id="cab80-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="cab80-111">(Os eventos do participante são controlados pela tabela tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="cab80-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="cab80-112">(Os servidores que processaram os eventos nessa tabela são listados na tabela tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="cab80-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="cab80-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="cab80-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="cab80-114">Contém os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="cab80-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="cab80-115">Esta tabela está estreitamente ligada a tabela tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="cab80-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="cab80-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="cab80-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="cab80-117">Contém os participantes atuais por serviço de bate-papo e por servidor.</span><span class="sxs-lookup"><span data-stu-id="cab80-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="cab80-118">Ele é mantido com base nos eventos de conformidade de participação e parte recebidos do serviço do Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cab80-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="cab80-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="cab80-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="cab80-120">Contém informações de estado de conformidade de todo o pool.</span><span class="sxs-lookup"><span data-stu-id="cab80-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

