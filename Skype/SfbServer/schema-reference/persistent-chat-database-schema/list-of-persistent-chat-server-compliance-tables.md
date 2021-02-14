---
title: Lista de tabelas de conformidade do Servidor de Chat Persistente no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: O esquema de banco de dados de conformidade do Chat Persistente consiste nas tabelas a seguir.
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813051"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="08749-103">Lista de tabelas de conformidade do Servidor de Chat Persistente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="08749-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="08749-104">O esquema de banco de dados de conformidade do Chat Persistente consiste nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="08749-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="08749-105">Lista das tabelas de conformidade do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="08749-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="08749-106">**Table**</span><span class="sxs-lookup"><span data-stu-id="08749-106">**Table**</span></span>|<span data-ttu-id="08749-107">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="08749-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="08749-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="08749-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="08749-109">Contém eventos de conformidade que ainda não foram processados pelo adaptador configurado.</span><span class="sxs-lookup"><span data-stu-id="08749-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="08749-110">Esta tabela inclui eventos relacionados ao Chat Persistente, como mensagens de chat e downloads de arquivos.</span><span class="sxs-lookup"><span data-stu-id="08749-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="08749-111">(Os eventos de participantes são acompanhados pela tabela tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="08749-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="08749-112">Os servidores que processaram os eventos dessa tabela estão listados na tabela tblComplianceFanout.</span><span class="sxs-lookup"><span data-stu-id="08749-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="08749-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="08749-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="08749-114">Contém os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="08749-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="08749-115">Esta tabela está diretamente relacionada à tabela tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="08749-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="08749-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="08749-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="08749-117">Contém os participantes atuais por serviço de chat e por servidor.</span><span class="sxs-lookup"><span data-stu-id="08749-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="08749-118">Ele é mantido com base nos eventos de conformidade de participação e parte recebidos do serviço de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="08749-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="08749-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="08749-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="08749-120">Contém informações sobre o estado de conformidade de todo o pool.</span><span class="sxs-lookup"><span data-stu-id="08749-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

