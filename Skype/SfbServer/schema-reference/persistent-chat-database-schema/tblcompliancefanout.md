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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874045"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="d9e86-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="d9e86-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="d9e86-104">a tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="d9e86-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="d9e86-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d9e86-105">**Columns**</span></span>

|<span data-ttu-id="d9e86-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d9e86-106">**Column**</span></span>|<span data-ttu-id="d9e86-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d9e86-107">**Type**</span></span>|<span data-ttu-id="d9e86-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d9e86-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d9e86-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="d9e86-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="d9e86-110">int</span><span class="sxs-lookup"><span data-stu-id="d9e86-110">int</span></span>  <br/> |<span data-ttu-id="d9e86-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="d9e86-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="d9e86-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="d9e86-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="d9e86-113">int</span><span class="sxs-lookup"><span data-stu-id="d9e86-113">int</span></span>  <br/> |<span data-ttu-id="d9e86-114">Identidade do servidor (correspondente à tabela Tblserveridentity).</span><span class="sxs-lookup"><span data-stu-id="d9e86-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="d9e86-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="d9e86-115">**Key**</span></span>

|<span data-ttu-id="d9e86-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d9e86-116">**Column**</span></span>|<span data-ttu-id="d9e86-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d9e86-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d9e86-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="d9e86-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="d9e86-119">Chave estrangeira com pesquisa na tabela Tblcompliancedata.</span><span class="sxs-lookup"><span data-stu-id="d9e86-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

