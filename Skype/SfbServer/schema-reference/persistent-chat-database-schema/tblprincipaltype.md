---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: Principaltype contém os tipos principais para categorizar o que está na tabela tblPrincipal.
ms.openlocfilehash: 804997c0cb25dff6566d21a26626550982d0075f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924455"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="540db-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="540db-103">tblPrincipalType</span></span>
 
<span data-ttu-id="540db-104">Principaltype contém os tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="540db-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="540db-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="540db-105">**Columns**</span></span>

|<span data-ttu-id="540db-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="540db-106">**Column**</span></span>|<span data-ttu-id="540db-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="540db-107">**Type**</span></span>|<span data-ttu-id="540db-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="540db-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="540db-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="540db-109">ptypeID</span></span>  <br/> |<span data-ttu-id="540db-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="540db-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="540db-111">ID do tipo de entidade.</span><span class="sxs-lookup"><span data-stu-id="540db-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="540db-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="540db-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="540db-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="540db-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="540db-114">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="540db-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="540db-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="540db-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="540db-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="540db-116">bit, not null</span></span>  <br/> |<span data-ttu-id="540db-117">True se o type corresponde às entidades que são usadas para finalidades internas.</span><span class="sxs-lookup"><span data-stu-id="540db-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="540db-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="540db-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="540db-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="540db-119">bit, not null</span></span>  <br/> |<span data-ttu-id="540db-120">True se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="540db-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="540db-121">**Chave**</span><span class="sxs-lookup"><span data-stu-id="540db-121">**Key**</span></span>

|<span data-ttu-id="540db-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="540db-122">**Column**</span></span>|<span data-ttu-id="540db-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="540db-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="540db-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="540db-124">ptypeID</span></span>  <br/> |<span data-ttu-id="540db-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="540db-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="540db-126">**Valores principais**</span><span class="sxs-lookup"><span data-stu-id="540db-126">**Principal Values**</span></span>

|<span data-ttu-id="540db-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="540db-127">**ID**</span></span>|<span data-ttu-id="540db-128">**Função**</span><span class="sxs-lookup"><span data-stu-id="540db-128">**Role**</span></span>|<span data-ttu-id="540db-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="540db-129">**Description**</span></span>|<span data-ttu-id="540db-130">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="540db-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="540db-131">1</span><span class="sxs-lookup"><span data-stu-id="540db-131">1</span></span>  <br/> |<span data-ttu-id="540db-132">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="540db-132">Any</span></span>  <br/> |<span data-ttu-id="540db-133">Entidade genérica com nenhum tipo conhecido.</span><span class="sxs-lookup"><span data-stu-id="540db-133">Generic principal with no known type.</span></span> <span data-ttu-id="540db-134">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="540db-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="540db-135">2</span><span class="sxs-lookup"><span data-stu-id="540db-135">2</span></span>  <br/> |<span data-ttu-id="540db-136">Dopode</span><span class="sxs-lookup"><span data-stu-id="540db-136">AnyUser</span></span>  <br/> |<span data-ttu-id="540db-137">Entidade genérica do tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="540db-137">Generic principal of user type.</span></span> <span data-ttu-id="540db-138">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="540db-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="540db-139">Sim</span><span class="sxs-lookup"><span data-stu-id="540db-139">Yes</span></span>  <br/> |
|<span data-ttu-id="540db-140">3</span><span class="sxs-lookup"><span data-stu-id="540db-140">3</span></span>  <br/> |<span data-ttu-id="540db-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="540db-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="540db-142">Entidade genérica com semântica de grupo.</span><span class="sxs-lookup"><span data-stu-id="540db-142">Generic principal with group semantic.</span></span> <span data-ttu-id="540db-143">Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="540db-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="540db-144">4</span><span class="sxs-lookup"><span data-stu-id="540db-144">4</span></span>  <br/> |<span data-ttu-id="540db-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="540db-145">SystemUser</span></span>  <br/> |<span data-ttu-id="540db-146">Entidade usada internamente pelo servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="540db-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="540db-147">5</span><span class="sxs-lookup"><span data-stu-id="540db-147">5</span></span>  <br/> |<span data-ttu-id="540db-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="540db-148">User</span></span>  <br/> |<span data-ttu-id="540db-149">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="540db-149">Regular user.</span></span>  <br/> |<span data-ttu-id="540db-150">Sim</span><span class="sxs-lookup"><span data-stu-id="540db-150">Yes</span></span>  <br/> |
|<span data-ttu-id="540db-151">8</span><span class="sxs-lookup"><span data-stu-id="540db-151">8</span></span>  <br/> |<span data-ttu-id="540db-152">CONTROLADOR DE DOMÍNIO</span><span class="sxs-lookup"><span data-stu-id="540db-152">DC</span></span>  <br/> |<span data-ttu-id="540db-153">Controlador de domínio do Active Directory dos serviços de domínio.</span><span class="sxs-lookup"><span data-stu-id="540db-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="540db-154">9</span><span class="sxs-lookup"><span data-stu-id="540db-154">9</span></span>  <br/> |<span data-ttu-id="540db-155">Grupo</span><span class="sxs-lookup"><span data-stu-id="540db-155">Group</span></span>  <br/> |<span data-ttu-id="540db-156">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="540db-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="540db-157">10</span><span class="sxs-lookup"><span data-stu-id="540db-157">10</span></span>  <br/> |<span data-ttu-id="540db-158">Pasta</span><span class="sxs-lookup"><span data-stu-id="540db-158">Folder</span></span>  <br/> |<span data-ttu-id="540db-159">Contêiner do Active Directory ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="540db-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="540db-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="540db-160">See also</span></span>

[<span data-ttu-id="540db-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="540db-161">tblPrincipal</span></span>](tblprincipal.md)
