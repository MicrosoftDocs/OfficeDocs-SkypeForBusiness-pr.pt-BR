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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814649"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="490eb-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="490eb-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="490eb-104">tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="490eb-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="490eb-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="490eb-105">**Columns**</span></span>

|<span data-ttu-id="490eb-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="490eb-106">**Column**</span></span>|<span data-ttu-id="490eb-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="490eb-107">**Type**</span></span>|<span data-ttu-id="490eb-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="490eb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="490eb-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="490eb-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="490eb-110">int</span><span class="sxs-lookup"><span data-stu-id="490eb-110">int</span></span>  <br/> |<span data-ttu-id="490eb-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="490eb-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="490eb-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="490eb-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="490eb-113">int</span><span class="sxs-lookup"><span data-stu-id="490eb-113">int</span></span>  <br/> |<span data-ttu-id="490eb-114">Identidade do servidor (correspondente à tabela tblServerIdentity. ServerId).</span><span class="sxs-lookup"><span data-stu-id="490eb-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="490eb-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="490eb-115">**Key**</span></span>

|<span data-ttu-id="490eb-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="490eb-116">**Column**</span></span>|<span data-ttu-id="490eb-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="490eb-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="490eb-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="490eb-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="490eb-119">Chave estrangeira com Lookup na tabela tblComplianceData. cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="490eb-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

