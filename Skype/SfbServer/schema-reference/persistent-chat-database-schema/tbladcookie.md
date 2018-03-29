---
title: a tabela tblADCookie
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: a tabela tblADCookie inclui os cookies atuais de sincronização de Lightweight Directory Access Protocol (LDAP).
ms.openlocfilehash: bc2c0657caa66a0420bc493bf4b688a2a081db36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tbladcookie"></a><span data-ttu-id="8f71e-103">a tabela tblADCookie</span><span class="sxs-lookup"><span data-stu-id="8f71e-103">tblADCookie</span></span>
 
<span data-ttu-id="8f71e-104">a tabela tblADCookie inclui os cookies atuais de sincronização de Lightweight Directory Access Protocol (LDAP).</span><span class="sxs-lookup"><span data-stu-id="8f71e-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="8f71e-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="8f71e-105">**Columns**</span></span>

|<span data-ttu-id="8f71e-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8f71e-106">**Column**</span></span>|<span data-ttu-id="8f71e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8f71e-107">**Type**</span></span>|<span data-ttu-id="8f71e-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8f71e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8f71e-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8f71e-109">prinGuid</span></span>  <br/> |<span data-ttu-id="8f71e-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="8f71e-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="8f71e-111">GUID principal do domínio sendo monitorado.</span><span class="sxs-lookup"><span data-stu-id="8f71e-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="8f71e-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="8f71e-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="8f71e-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="8f71e-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="8f71e-114">Nome de domínio totalmente qualificado (FQDN) do controlador de domínio atual usado para sincronização de serviços de domínio do Active Directory. Tem valor informativo.</span><span class="sxs-lookup"><span data-stu-id="8f71e-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="8f71e-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="8f71e-115">adcContent</span></span>  <br/> |<span data-ttu-id="8f71e-116">imagem (binário)</span><span class="sxs-lookup"><span data-stu-id="8f71e-116">image (binary)</span></span>  <br/> |<span data-ttu-id="8f71e-117">Cookie da sincronização de diretório ativo.</span><span class="sxs-lookup"><span data-stu-id="8f71e-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="8f71e-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="8f71e-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="8f71e-119">datetime</span><span class="sxs-lookup"><span data-stu-id="8f71e-119">datetime</span></span>  <br/> |<span data-ttu-id="8f71e-120">Carimbo de hora com a hora de atualização da linha.</span><span class="sxs-lookup"><span data-stu-id="8f71e-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="8f71e-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="8f71e-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="8f71e-122">datetime</span><span class="sxs-lookup"><span data-stu-id="8f71e-122">datetime</span></span>  <br/> |<span data-ttu-id="8f71e-123">Tempo até que a linha é bloqueada para alterações.</span><span class="sxs-lookup"><span data-stu-id="8f71e-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="8f71e-124">Isso faz parte de um mecanismo de travamento de software que garante que apenas um dos serviços do chat faz a sincronização do Active Directory ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8f71e-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="8f71e-125">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="8f71e-125">**Keys**</span></span>

|<span data-ttu-id="8f71e-126">**Coluna (s)**</span><span class="sxs-lookup"><span data-stu-id="8f71e-126">**Column(s)**</span></span>|<span data-ttu-id="8f71e-127">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8f71e-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f71e-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8f71e-128">prinGuid</span></span>  <br/> |<span data-ttu-id="8f71e-129">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="8f71e-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8f71e-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8f71e-130">prinGuid</span></span>  <br/> |<span data-ttu-id="8f71e-131">Chave estrangeira com pesquisa na tabela pringuid.</span><span class="sxs-lookup"><span data-stu-id="8f71e-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

