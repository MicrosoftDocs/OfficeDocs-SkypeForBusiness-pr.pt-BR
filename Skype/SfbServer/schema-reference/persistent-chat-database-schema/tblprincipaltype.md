---
title: tblPrincipalType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: Principaltype contém os tipos principais para categorizar o que está na tabela tblPrincipal.
ms.openlocfilehash: ab2cb28971f0564a082e0caed01e7fc622c41201
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887432"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="221b7-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="221b7-103">tblPrincipalType</span></span>
 
<span data-ttu-id="221b7-104">Principaltype contém os tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="221b7-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="221b7-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="221b7-105">**Columns**</span></span>

|<span data-ttu-id="221b7-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="221b7-106">**Column**</span></span>|<span data-ttu-id="221b7-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="221b7-107">**Type**</span></span>|<span data-ttu-id="221b7-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="221b7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="221b7-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="221b7-109">ptypeID</span></span>  <br/> |<span data-ttu-id="221b7-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="221b7-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="221b7-111">ID do tipo de entidade.</span><span class="sxs-lookup"><span data-stu-id="221b7-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="221b7-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="221b7-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="221b7-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="221b7-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="221b7-114">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="221b7-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="221b7-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="221b7-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="221b7-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="221b7-116">bit, not null</span></span>  <br/> |<span data-ttu-id="221b7-117">True se o type corresponde às entidades que são usadas para finalidades internas.</span><span class="sxs-lookup"><span data-stu-id="221b7-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="221b7-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="221b7-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="221b7-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="221b7-119">bit, not null</span></span>  <br/> |<span data-ttu-id="221b7-120">True se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="221b7-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="221b7-121">**Chave**</span><span class="sxs-lookup"><span data-stu-id="221b7-121">**Key**</span></span>

|<span data-ttu-id="221b7-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="221b7-122">**Column**</span></span>|<span data-ttu-id="221b7-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="221b7-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="221b7-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="221b7-124">ptypeID</span></span>  <br/> |<span data-ttu-id="221b7-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="221b7-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="221b7-126">**Valores principais**</span><span class="sxs-lookup"><span data-stu-id="221b7-126">**Principal Values**</span></span>

|<span data-ttu-id="221b7-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="221b7-127">**ID**</span></span>|<span data-ttu-id="221b7-128">**Função**</span><span class="sxs-lookup"><span data-stu-id="221b7-128">**Role**</span></span>|<span data-ttu-id="221b7-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="221b7-129">**Description**</span></span>|<span data-ttu-id="221b7-130">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="221b7-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="221b7-131">1</span><span class="sxs-lookup"><span data-stu-id="221b7-131">1</span></span>  <br/> |<span data-ttu-id="221b7-132">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="221b7-132">Any</span></span>  <br/> |<span data-ttu-id="221b7-133">Entidade genérica com nenhum tipo conhecido.</span><span class="sxs-lookup"><span data-stu-id="221b7-133">Generic principal with no known type.</span></span> <span data-ttu-id="221b7-134">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="221b7-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="221b7-135">2</span><span class="sxs-lookup"><span data-stu-id="221b7-135">2</span></span>  <br/> |<span data-ttu-id="221b7-136">Dopode</span><span class="sxs-lookup"><span data-stu-id="221b7-136">AnyUser</span></span>  <br/> |<span data-ttu-id="221b7-137">Entidade genérica do tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="221b7-137">Generic principal of user type.</span></span> <span data-ttu-id="221b7-138">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="221b7-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="221b7-139">Sim</span><span class="sxs-lookup"><span data-stu-id="221b7-139">Yes</span></span>  <br/> |
|<span data-ttu-id="221b7-140">3</span><span class="sxs-lookup"><span data-stu-id="221b7-140">3</span></span>  <br/> |<span data-ttu-id="221b7-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="221b7-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="221b7-142">Entidade genérica com semântica de grupo.</span><span class="sxs-lookup"><span data-stu-id="221b7-142">Generic principal with group semantic.</span></span> <span data-ttu-id="221b7-143">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="221b7-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="221b7-144">4</span><span class="sxs-lookup"><span data-stu-id="221b7-144">4</span></span>  <br/> |<span data-ttu-id="221b7-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="221b7-145">SystemUser</span></span>  <br/> |<span data-ttu-id="221b7-146">Entidade usada internamente pelo servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="221b7-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="221b7-147">5</span><span class="sxs-lookup"><span data-stu-id="221b7-147">5</span></span>  <br/> |<span data-ttu-id="221b7-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="221b7-148">User</span></span>  <br/> |<span data-ttu-id="221b7-149">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="221b7-149">Regular user.</span></span>  <br/> |<span data-ttu-id="221b7-150">Sim</span><span class="sxs-lookup"><span data-stu-id="221b7-150">Yes</span></span>  <br/> |
|<span data-ttu-id="221b7-151">8</span><span class="sxs-lookup"><span data-stu-id="221b7-151">8</span></span>  <br/> |<span data-ttu-id="221b7-152">CONTROLADOR DE DOMÍNIO</span><span class="sxs-lookup"><span data-stu-id="221b7-152">DC</span></span>  <br/> |<span data-ttu-id="221b7-153">Controlador de domínio do Active Directory dos serviços de domínio.</span><span class="sxs-lookup"><span data-stu-id="221b7-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="221b7-154">9</span><span class="sxs-lookup"><span data-stu-id="221b7-154">9</span></span>  <br/> |<span data-ttu-id="221b7-155">Grupo</span><span class="sxs-lookup"><span data-stu-id="221b7-155">Group</span></span>  <br/> |<span data-ttu-id="221b7-156">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="221b7-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="221b7-157">10</span><span class="sxs-lookup"><span data-stu-id="221b7-157">10</span></span>  <br/> |<span data-ttu-id="221b7-158">Pasta</span><span class="sxs-lookup"><span data-stu-id="221b7-158">Folder</span></span>  <br/> |<span data-ttu-id="221b7-159">Contêiner do Active Directory ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="221b7-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="221b7-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="221b7-160">See also</span></span>

[<span data-ttu-id="221b7-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="221b7-161">tblPrincipal</span></span>](tblprincipal.md)
