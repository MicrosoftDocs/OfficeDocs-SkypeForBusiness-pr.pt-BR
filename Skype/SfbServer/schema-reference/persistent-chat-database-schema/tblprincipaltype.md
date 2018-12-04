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
ms.openlocfilehash: d5c710e1301344c853ef39aeff3b57f62c630c95
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505122"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="e155e-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="e155e-103">tblPrincipalType</span></span>
 
<span data-ttu-id="e155e-104">Principaltype contém os tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="e155e-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="e155e-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="e155e-105">**Columns**</span></span>

|<span data-ttu-id="e155e-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e155e-106">**Column**</span></span>|<span data-ttu-id="e155e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e155e-107">**Type**</span></span>|<span data-ttu-id="e155e-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e155e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e155e-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="e155e-109">ptypeID</span></span>  <br/> |<span data-ttu-id="e155e-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="e155e-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="e155e-111">ID do tipo de entidade.</span><span class="sxs-lookup"><span data-stu-id="e155e-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="e155e-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="e155e-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="e155e-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="e155e-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e155e-114">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="e155e-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="e155e-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="e155e-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="e155e-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="e155e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="e155e-117">True se o type corresponde às entidades que são usadas para finalidades internas.</span><span class="sxs-lookup"><span data-stu-id="e155e-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="e155e-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="e155e-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="e155e-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="e155e-119">bit, not null</span></span>  <br/> |<span data-ttu-id="e155e-120">True se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="e155e-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="e155e-121">**Chave**</span><span class="sxs-lookup"><span data-stu-id="e155e-121">**Key**</span></span>

|<span data-ttu-id="e155e-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e155e-122">**Column**</span></span>|<span data-ttu-id="e155e-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e155e-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e155e-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="e155e-124">ptypeID</span></span>  <br/> |<span data-ttu-id="e155e-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="e155e-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="e155e-126">**Valores principais**</span><span class="sxs-lookup"><span data-stu-id="e155e-126">**Principal Values**</span></span>

|<span data-ttu-id="e155e-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="e155e-127">**ID**</span></span>|<span data-ttu-id="e155e-128">**Função**</span><span class="sxs-lookup"><span data-stu-id="e155e-128">**Role**</span></span>|<span data-ttu-id="e155e-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e155e-129">**Description**</span></span>|<span data-ttu-id="e155e-130">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="e155e-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e155e-131">1</span><span class="sxs-lookup"><span data-stu-id="e155e-131">1</span></span>  <br/> |<span data-ttu-id="e155e-132">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e155e-132">Any</span></span>  <br/> |<span data-ttu-id="e155e-133">Entidade genérica com nenhum tipo conhecido.</span><span class="sxs-lookup"><span data-stu-id="e155e-133">Generic principal with no known type.</span></span> <span data-ttu-id="e155e-134">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="e155e-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="e155e-135">2</span><span class="sxs-lookup"><span data-stu-id="e155e-135">2</span></span>  <br/> |<span data-ttu-id="e155e-136">Dopode</span><span class="sxs-lookup"><span data-stu-id="e155e-136">AnyUser</span></span>  <br/> |<span data-ttu-id="e155e-137">Entidade genérica do tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="e155e-137">Generic principal of user type.</span></span> <span data-ttu-id="e155e-138">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="e155e-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="e155e-139">Sim</span><span class="sxs-lookup"><span data-stu-id="e155e-139">Yes</span></span>  <br/> |
|<span data-ttu-id="e155e-140">3</span><span class="sxs-lookup"><span data-stu-id="e155e-140">3</span></span>  <br/> |<span data-ttu-id="e155e-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="e155e-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="e155e-142">Entidade genérica com semântica de grupo.</span><span class="sxs-lookup"><span data-stu-id="e155e-142">Generic principal with group semantic.</span></span> <span data-ttu-id="e155e-143">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="e155e-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="e155e-144">4</span><span class="sxs-lookup"><span data-stu-id="e155e-144">4</span></span>  <br/> |<span data-ttu-id="e155e-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="e155e-145">SystemUser</span></span>  <br/> |<span data-ttu-id="e155e-146">Entidade usada internamente pelo servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e155e-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="e155e-147">5</span><span class="sxs-lookup"><span data-stu-id="e155e-147">5</span></span>  <br/> |<span data-ttu-id="e155e-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="e155e-148">User</span></span>  <br/> |<span data-ttu-id="e155e-149">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="e155e-149">Regular user.</span></span>  <br/> |<span data-ttu-id="e155e-150">Sim</span><span class="sxs-lookup"><span data-stu-id="e155e-150">Yes</span></span>  <br/> |
|<span data-ttu-id="e155e-151">8</span><span class="sxs-lookup"><span data-stu-id="e155e-151">8</span></span>  <br/> |<span data-ttu-id="e155e-152">CONTROLADOR DE DOMÍNIO</span><span class="sxs-lookup"><span data-stu-id="e155e-152">DC</span></span>  <br/> |<span data-ttu-id="e155e-153">Controlador de domínio do Active Directory dos serviços de domínio.</span><span class="sxs-lookup"><span data-stu-id="e155e-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="e155e-154">9</span><span class="sxs-lookup"><span data-stu-id="e155e-154">9</span></span>  <br/> |<span data-ttu-id="e155e-155">Grupo</span><span class="sxs-lookup"><span data-stu-id="e155e-155">Group</span></span>  <br/> |<span data-ttu-id="e155e-156">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e155e-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="e155e-157"> 10</span><span class="sxs-lookup"><span data-stu-id="e155e-157">10</span></span>  <br/> |<span data-ttu-id="e155e-158">Pasta</span><span class="sxs-lookup"><span data-stu-id="e155e-158">Folder</span></span>  <br/> |<span data-ttu-id="e155e-159">Contêiner do Active Directory ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="e155e-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="e155e-160">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e155e-160">See also</span></span>

[<span data-ttu-id="e155e-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="e155e-161">tblPrincipal</span></span>](tblprincipal.md)