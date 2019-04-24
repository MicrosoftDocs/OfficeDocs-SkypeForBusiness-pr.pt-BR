---
title: tblComplianceFanout
ms.reviewer: ''
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
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212625"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="58dad-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="58dad-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="58dad-104">a tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="58dad-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="58dad-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="58dad-105">**Columns**</span></span>

|<span data-ttu-id="58dad-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="58dad-106">**Column**</span></span>|<span data-ttu-id="58dad-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="58dad-107">**Type**</span></span>|<span data-ttu-id="58dad-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="58dad-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="58dad-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="58dad-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="58dad-110">int</span><span class="sxs-lookup"><span data-stu-id="58dad-110">int</span></span>  <br/> |<span data-ttu-id="58dad-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="58dad-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="58dad-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="58dad-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="58dad-113">int</span><span class="sxs-lookup"><span data-stu-id="58dad-113">int</span></span>  <br/> |<span data-ttu-id="58dad-114">Identidade do servidor (correspondente à tabela Tblserveridentity).</span><span class="sxs-lookup"><span data-stu-id="58dad-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="58dad-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="58dad-115">**Key**</span></span>

|<span data-ttu-id="58dad-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="58dad-116">**Column**</span></span>|<span data-ttu-id="58dad-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="58dad-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58dad-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="58dad-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="58dad-119">Chave estrangeira com pesquisa na tabela Tblcompliancedata.</span><span class="sxs-lookup"><span data-stu-id="58dad-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

