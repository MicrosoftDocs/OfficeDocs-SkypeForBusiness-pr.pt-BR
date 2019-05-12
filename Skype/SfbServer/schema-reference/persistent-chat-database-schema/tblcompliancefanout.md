---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: a tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
ms.openlocfilehash: 002ffe3fd825dd90a5223dca06316ff3a60fddd9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929916"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="ec3f0-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="ec3f0-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="ec3f0-104">a tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="ec3f0-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="ec3f0-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="ec3f0-105">**Columns**</span></span>

|<span data-ttu-id="ec3f0-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ec3f0-106">**Column**</span></span>|<span data-ttu-id="ec3f0-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ec3f0-107">**Type**</span></span>|<span data-ttu-id="ec3f0-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ec3f0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ec3f0-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="ec3f0-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="ec3f0-110">int</span><span class="sxs-lookup"><span data-stu-id="ec3f0-110">int</span></span>  <br/> |<span data-ttu-id="ec3f0-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="ec3f0-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="ec3f0-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="ec3f0-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="ec3f0-113">int</span><span class="sxs-lookup"><span data-stu-id="ec3f0-113">int</span></span>  <br/> |<span data-ttu-id="ec3f0-114">Identidade do servidor (correspondente à tabela Tblserveridentity).</span><span class="sxs-lookup"><span data-stu-id="ec3f0-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="ec3f0-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="ec3f0-115">**Key**</span></span>

|<span data-ttu-id="ec3f0-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ec3f0-116">**Column**</span></span>|<span data-ttu-id="ec3f0-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ec3f0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec3f0-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="ec3f0-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="ec3f0-119">Chave estrangeira com pesquisa na tabela Tblcompliancedata.</span><span class="sxs-lookup"><span data-stu-id="ec3f0-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

