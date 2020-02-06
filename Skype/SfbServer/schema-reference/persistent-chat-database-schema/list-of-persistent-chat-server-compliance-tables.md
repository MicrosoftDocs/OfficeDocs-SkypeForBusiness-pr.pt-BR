---
title: Lista de tabelas de conformidade do servidor de chat persistente no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: O esquema de banco de dados de conformidade de chat persistente consiste nas tabelas a seguir.
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814759"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="2edd1-103">Lista de tabelas de conformidade do servidor de chat persistente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2edd1-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="2edd1-104">O esquema de banco de dados de conformidade de chat persistente consiste nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="2edd1-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="2edd1-105">Lista de tabelas de conformidade do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2edd1-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="2edd1-106">**Tabela**</span><span class="sxs-lookup"><span data-stu-id="2edd1-106">**Table**</span></span>|<span data-ttu-id="2edd1-107">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2edd1-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2edd1-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="2edd1-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="2edd1-109">Contém os eventos de conformidade que ainda não foram processados pelo adaptador configurado.</span><span class="sxs-lookup"><span data-stu-id="2edd1-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="2edd1-110">Esta tabela inclui eventos persistentes relacionados a chats, como mensagens de chat e downloads de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2edd1-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="2edd1-111">(Os eventos do participante são rastreados pela tabela tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="2edd1-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="2edd1-112">(Os servidores que processaram os eventos nessa tabela estão listados na tabela tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="2edd1-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="2edd1-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="2edd1-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="2edd1-114">Contém os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="2edd1-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="2edd1-115">Esta tabela está rigidamente acoplada à tabela tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="2edd1-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="2edd1-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="2edd1-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="2edd1-117">Contém os participantes atuais por serviço de chat e por servidor.</span><span class="sxs-lookup"><span data-stu-id="2edd1-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="2edd1-118">Ele é mantido com base nos eventos de conformidade do ingresso e na parte recebidos do serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2edd1-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="2edd1-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="2edd1-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="2edd1-120">Contém informações de estado de conformidade em todo o pool.</span><span class="sxs-lookup"><span data-stu-id="2edd1-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

