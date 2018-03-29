---
title: tabela tblComplianceFanout
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: a tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="cf5a0-103">tabela tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="cf5a0-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="cf5a0-104">a tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="cf5a0-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="cf5a0-105">**Columns**</span></span>

|<span data-ttu-id="cf5a0-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cf5a0-106">**Column**</span></span>|<span data-ttu-id="cf5a0-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cf5a0-107">**Type**</span></span>|<span data-ttu-id="cf5a0-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cf5a0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cf5a0-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="cf5a0-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="cf5a0-110">int</span><span class="sxs-lookup"><span data-stu-id="cf5a0-110">int</span></span>  <br/> |<span data-ttu-id="cf5a0-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="cf5a0-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="cf5a0-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="cf5a0-113">int</span><span class="sxs-lookup"><span data-stu-id="cf5a0-113">int</span></span>  <br/> |<span data-ttu-id="cf5a0-114">Identidade do servidor (correspondente à tabela Tblserveridentity).</span><span class="sxs-lookup"><span data-stu-id="cf5a0-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="cf5a0-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="cf5a0-115">**Key**</span></span>

|<span data-ttu-id="cf5a0-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cf5a0-116">**Column**</span></span>|<span data-ttu-id="cf5a0-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cf5a0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf5a0-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="cf5a0-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="cf5a0-119">Chave estrangeira com pesquisa na tabela Tblcompliancedata.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

