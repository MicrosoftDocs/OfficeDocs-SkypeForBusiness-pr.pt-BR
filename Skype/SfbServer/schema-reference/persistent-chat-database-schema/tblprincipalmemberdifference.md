---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: TblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processadas pelas etapas posteriores de Sincronização dos Serviços de Domínio Active Directory.
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809701"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="2e36e-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="2e36e-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="2e36e-104">TblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processadas pelas etapas posteriores de Sincronização dos Serviços de Domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2e36e-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="2e36e-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="2e36e-105">**Columns**</span></span>

|<span data-ttu-id="2e36e-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2e36e-106">**Column**</span></span>|<span data-ttu-id="2e36e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2e36e-107">**Type**</span></span>|<span data-ttu-id="2e36e-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2e36e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e36e-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2e36e-109">prinGuid</span></span>  <br/> |<span data-ttu-id="2e36e-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="2e36e-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="2e36e-111">GUID principal do grupo que mudou.</span><span class="sxs-lookup"><span data-stu-id="2e36e-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="2e36e-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="2e36e-112">memberADPath</span></span>  <br/> |<span data-ttu-id="2e36e-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2e36e-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="2e36e-114">Nome distinto do membro.</span><span class="sxs-lookup"><span data-stu-id="2e36e-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="2e36e-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="2e36e-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="2e36e-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="2e36e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="2e36e-p101">Falso se o membro tiver sido adicionado. Verdadeiro se o membro tiver sido removido.</span><span class="sxs-lookup"><span data-stu-id="2e36e-p101">False if the member was added. True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="2e36e-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="2e36e-119">**Key**</span></span>

|<span data-ttu-id="2e36e-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2e36e-120">**Column**</span></span>|<span data-ttu-id="2e36e-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2e36e-121">**Description**</span></span>|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |<span data-ttu-id="2e36e-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="2e36e-122">Primary key.</span></span>  <br/> |
   

