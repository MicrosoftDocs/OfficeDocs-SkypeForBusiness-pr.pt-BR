---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: A tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809791"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="79b28-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="79b28-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="79b28-104">A tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="79b28-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="79b28-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="79b28-105">**Columns**</span></span>

|<span data-ttu-id="79b28-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="79b28-106">**Column**</span></span>|<span data-ttu-id="79b28-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="79b28-107">**Type**</span></span>|<span data-ttu-id="79b28-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="79b28-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79b28-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="79b28-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="79b28-110">int</span><span class="sxs-lookup"><span data-stu-id="79b28-110">int</span></span>  <br/> |<span data-ttu-id="79b28-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="79b28-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="79b28-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="79b28-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="79b28-113">int</span><span class="sxs-lookup"><span data-stu-id="79b28-113">int</span></span>  <br/> |<span data-ttu-id="79b28-114">Identidade do servidor (correspondente à tabela tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="79b28-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="79b28-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="79b28-115">**Key**</span></span>

|<span data-ttu-id="79b28-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="79b28-116">**Column**</span></span>|<span data-ttu-id="79b28-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="79b28-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="79b28-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="79b28-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="79b28-119">Chave estrangeira com pesquisa na tabela tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="79b28-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

