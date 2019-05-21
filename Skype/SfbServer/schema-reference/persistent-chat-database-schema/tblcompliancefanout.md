---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295500"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="40c1b-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="40c1b-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="40c1b-104">tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="40c1b-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="40c1b-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="40c1b-105">**Columns**</span></span>

|<span data-ttu-id="40c1b-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="40c1b-106">**Column**</span></span>|<span data-ttu-id="40c1b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="40c1b-107">**Type**</span></span>|<span data-ttu-id="40c1b-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="40c1b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="40c1b-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="40c1b-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="40c1b-110">int</span><span class="sxs-lookup"><span data-stu-id="40c1b-110">int</span></span>  <br/> |<span data-ttu-id="40c1b-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="40c1b-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="40c1b-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="40c1b-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="40c1b-113">int</span><span class="sxs-lookup"><span data-stu-id="40c1b-113">int</span></span>  <br/> |<span data-ttu-id="40c1b-114">Identidade do servidor (correspondente à tabela tblServerIdentity. ServerId).</span><span class="sxs-lookup"><span data-stu-id="40c1b-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="40c1b-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="40c1b-115">**Key**</span></span>

|<span data-ttu-id="40c1b-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="40c1b-116">**Column**</span></span>|<span data-ttu-id="40c1b-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="40c1b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40c1b-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="40c1b-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="40c1b-119">Chave estrangeira com Lookup na tabela tblComplianceData. cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="40c1b-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

