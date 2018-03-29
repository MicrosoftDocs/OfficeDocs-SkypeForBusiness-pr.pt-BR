---
title: tblPrincipalType
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
ms.openlocfilehash: 3d1ec9b83561f06d3f8b1871223aafdf5c0775cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipaltype"></a><span data-ttu-id="c822e-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="c822e-103">tblPrincipalType</span></span>
 
<span data-ttu-id="c822e-104">Principaltype contém os tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="c822e-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="c822e-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="c822e-105">**Columns**</span></span>

|<span data-ttu-id="c822e-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c822e-106">**Column**</span></span>|<span data-ttu-id="c822e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c822e-107">**Type**</span></span>|<span data-ttu-id="c822e-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c822e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c822e-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="c822e-109">ptypeID</span></span>  <br/> |<span data-ttu-id="c822e-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="c822e-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="c822e-111">ID do tipo de entidade.</span><span class="sxs-lookup"><span data-stu-id="c822e-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="c822e-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="c822e-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="c822e-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="c822e-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="c822e-114">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="c822e-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="c822e-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="c822e-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="c822e-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="c822e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="c822e-117">True se o type corresponde às entidades que são usadas para finalidades internas.</span><span class="sxs-lookup"><span data-stu-id="c822e-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="c822e-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="c822e-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="c822e-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="c822e-119">bit, not null</span></span>  <br/> |<span data-ttu-id="c822e-120">True se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="c822e-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="c822e-121">**Chave**</span><span class="sxs-lookup"><span data-stu-id="c822e-121">**Key**</span></span>

|<span data-ttu-id="c822e-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c822e-122">**Column**</span></span>|<span data-ttu-id="c822e-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c822e-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c822e-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="c822e-124">ptypeID</span></span>  <br/> |<span data-ttu-id="c822e-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="c822e-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="c822e-126">**Valores principais**</span><span class="sxs-lookup"><span data-stu-id="c822e-126">**Principal Values**</span></span>

|<span data-ttu-id="c822e-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="c822e-127">**ID**</span></span>|<span data-ttu-id="c822e-128">**Função**</span><span class="sxs-lookup"><span data-stu-id="c822e-128">**Role**</span></span>|<span data-ttu-id="c822e-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c822e-129">**Description**</span></span>|<span data-ttu-id="c822e-130">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="c822e-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c822e-131">1</span><span class="sxs-lookup"><span data-stu-id="c822e-131">1</span></span>  <br/> |<span data-ttu-id="c822e-132">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c822e-132">Any</span></span>  <br/> |<span data-ttu-id="c822e-133">Entidade genérica com nenhum tipo conhecido.</span><span class="sxs-lookup"><span data-stu-id="c822e-133">Generic principal with no known type.</span></span> <span data-ttu-id="c822e-134">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="c822e-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="c822e-135">2</span><span class="sxs-lookup"><span data-stu-id="c822e-135">2</span></span>  <br/> |<span data-ttu-id="c822e-136">Dopode</span><span class="sxs-lookup"><span data-stu-id="c822e-136">AnyUser</span></span>  <br/> |<span data-ttu-id="c822e-137">Entidade genérica do tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="c822e-137">Generic principal of user type.</span></span> <span data-ttu-id="c822e-138">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="c822e-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="c822e-139">Sim</span><span class="sxs-lookup"><span data-stu-id="c822e-139">Yes</span></span>  <br/> |
|<span data-ttu-id="c822e-140">3</span><span class="sxs-lookup"><span data-stu-id="c822e-140">3</span></span>  <br/> |<span data-ttu-id="c822e-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="c822e-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="c822e-142">Entidade genérica com semântica de grupo.</span><span class="sxs-lookup"><span data-stu-id="c822e-142">Generic principal with group semantic.</span></span> <span data-ttu-id="c822e-143">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="c822e-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="c822e-144">4</span><span class="sxs-lookup"><span data-stu-id="c822e-144">4</span></span>  <br/> |<span data-ttu-id="c822e-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="c822e-145">SystemUser</span></span>  <br/> |<span data-ttu-id="c822e-146">Entidade usada internamente pelo servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c822e-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="c822e-147">5</span><span class="sxs-lookup"><span data-stu-id="c822e-147">5</span></span>  <br/> |<span data-ttu-id="c822e-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="c822e-148">User</span></span>  <br/> |<span data-ttu-id="c822e-149">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="c822e-149">Regular user.</span></span>  <br/> |<span data-ttu-id="c822e-150">Sim</span><span class="sxs-lookup"><span data-stu-id="c822e-150">Yes</span></span>  <br/> |
|<span data-ttu-id="c822e-151">8</span><span class="sxs-lookup"><span data-stu-id="c822e-151">8</span></span>  <br/> |<span data-ttu-id="c822e-152">CONTROLADOR DE DOMÍNIO</span><span class="sxs-lookup"><span data-stu-id="c822e-152">DC</span></span>  <br/> |<span data-ttu-id="c822e-153">Controlador de domínio do Active Directory dos serviços de domínio.</span><span class="sxs-lookup"><span data-stu-id="c822e-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="c822e-154">9</span><span class="sxs-lookup"><span data-stu-id="c822e-154">9</span></span>  <br/> |<span data-ttu-id="c822e-155">Grupo</span><span class="sxs-lookup"><span data-stu-id="c822e-155">Group</span></span>  <br/> |<span data-ttu-id="c822e-156">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c822e-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="c822e-157">10</span><span class="sxs-lookup"><span data-stu-id="c822e-157">10</span></span>  <br/> |<span data-ttu-id="c822e-158">Pasta</span><span class="sxs-lookup"><span data-stu-id="c822e-158">Folder</span></span>  <br/> |<span data-ttu-id="c822e-159">Contêiner do Active Directory ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="c822e-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="c822e-160">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c822e-160">See also</span></span>

#### 

[<span data-ttu-id="c822e-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="c822e-161">tblPrincipal</span></span>](tblprincipal.md)

