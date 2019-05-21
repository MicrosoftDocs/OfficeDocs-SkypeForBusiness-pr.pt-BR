---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contém os atuais cookies de sincronização de LDAP (Lightweight Directory Access Protocol).
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295528"
---
# <a name="tbladcookie"></a><span data-ttu-id="f3d0d-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="f3d0d-103">tblADCookie</span></span>
 
<span data-ttu-id="f3d0d-104">tblADCookie contém os atuais cookies de sincronização de LDAP (Lightweight Directory Access Protocol).</span><span class="sxs-lookup"><span data-stu-id="f3d0d-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="f3d0d-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="f3d0d-105">**Columns**</span></span>

|<span data-ttu-id="f3d0d-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f3d0d-106">**Column**</span></span>|<span data-ttu-id="f3d0d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f3d0d-107">**Type**</span></span>|<span data-ttu-id="f3d0d-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f3d0d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3d0d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f3d0d-109">prinGuid</span></span>  <br/> |<span data-ttu-id="f3d0d-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="f3d0d-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="f3d0d-111">GUID principal do domínio que está sendo monitorado.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="f3d0d-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="f3d0d-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="f3d0d-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="f3d0d-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="f3d0d-114">FQDN (nome de domínio totalmente qualificado) do controlador de domínio atual usado para a sincronização dos serviços de domínio Active Directory. Tem valor informativo.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="f3d0d-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="f3d0d-115">adcContent</span></span>  <br/> |<span data-ttu-id="f3d0d-116">imagem (binário)</span><span class="sxs-lookup"><span data-stu-id="f3d0d-116">image (binary)</span></span>  <br/> |<span data-ttu-id="f3d0d-117">Cookie de sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="f3d0d-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="f3d0d-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="f3d0d-119">datetime</span><span class="sxs-lookup"><span data-stu-id="f3d0d-119">datetime</span></span>  <br/> |<span data-ttu-id="f3d0d-120">Carimbo de data/hora com o tempo de atualização de linha.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="f3d0d-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="f3d0d-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="f3d0d-122">datetime</span><span class="sxs-lookup"><span data-stu-id="f3d0d-122">datetime</span></span>  <br/> |<span data-ttu-id="f3d0d-123">Tempo até que a linha esteja bloqueada para alterações.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="f3d0d-124">Isso faz parte de um mecanismo de travamento do software que garante que apenas um dos serviços de chat faça a sincronização do Active Directory de cada vez.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="f3d0d-125">**As**</span><span class="sxs-lookup"><span data-stu-id="f3d0d-125">**Keys**</span></span>

|<span data-ttu-id="f3d0d-126">**Coluna (s)**</span><span class="sxs-lookup"><span data-stu-id="f3d0d-126">**Column(s)**</span></span>|<span data-ttu-id="f3d0d-127">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f3d0d-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f3d0d-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f3d0d-128">prinGuid</span></span>  <br/> |<span data-ttu-id="f3d0d-129">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f3d0d-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f3d0d-130">prinGuid</span></span>  <br/> |<span data-ttu-id="f3d0d-131">Chave estrangeira com pesquisa na tabela principal. prinGuid.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

