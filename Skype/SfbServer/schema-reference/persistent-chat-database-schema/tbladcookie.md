---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: A tabela tblADCookie inclui os cookies atuais de sincronização do Protocolo LDAP.
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814751"
---
# <a name="tbladcookie"></a><span data-ttu-id="20442-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="20442-103">tblADCookie</span></span>
 
<span data-ttu-id="20442-104">A tabela tblADCookie inclui os cookies atuais de sincronização do Protocolo LDAP.</span><span class="sxs-lookup"><span data-stu-id="20442-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="20442-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="20442-105">**Columns**</span></span>

|<span data-ttu-id="20442-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="20442-106">**Column**</span></span>|<span data-ttu-id="20442-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="20442-107">**Type**</span></span>|<span data-ttu-id="20442-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="20442-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20442-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="20442-109">prinGuid</span></span>  <br/> |<span data-ttu-id="20442-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="20442-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="20442-111">GUID principal do domínio em monitoramento.</span><span class="sxs-lookup"><span data-stu-id="20442-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="20442-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="20442-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="20442-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="20442-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="20442-114">Nome de domínio totalmente qualificado (FQDN) do controlador de domínio atual usado para a Sincronização de Serviços de Domínio do Active Directory. Tem valor informacional.</span><span class="sxs-lookup"><span data-stu-id="20442-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="20442-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="20442-115">adcContent</span></span>  <br/> |<span data-ttu-id="20442-116">imagem (binário)</span><span class="sxs-lookup"><span data-stu-id="20442-116">image (binary)</span></span>  <br/> |<span data-ttu-id="20442-117">Cookie da Sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="20442-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="20442-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="20442-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="20442-119">datetime</span><span class="sxs-lookup"><span data-stu-id="20442-119">datetime</span></span>  <br/> |<span data-ttu-id="20442-120">Carimbo de data/hora com a data/hora de atualização da linha.</span><span class="sxs-lookup"><span data-stu-id="20442-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="20442-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="20442-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="20442-122">datetime</span><span class="sxs-lookup"><span data-stu-id="20442-122">datetime</span></span>  <br/> |<span data-ttu-id="20442-p101">Tempo até que a linha seja bloqueada para alterações. Isso faz parte de um mecanismo de interloque do software que garante que apenas um dos Servidores de Chat faça a sincronização do Active Directory por vez.</span><span class="sxs-lookup"><span data-stu-id="20442-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="20442-125">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="20442-125">**Keys**</span></span>

|<span data-ttu-id="20442-126">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="20442-126">**Column(s)**</span></span>|<span data-ttu-id="20442-127">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="20442-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20442-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="20442-128">prinGuid</span></span>  <br/> |<span data-ttu-id="20442-129">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="20442-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="20442-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="20442-130">prinGuid</span></span>  <br/> |<span data-ttu-id="20442-131">Chave estrangeira com pesquisa na tabela Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="20442-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

