---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contém tipos principais para categorizar o que está na tabela tblPrincipal.
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812929"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="2fc7a-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="2fc7a-103">tblPrincipalType</span></span>
 
<span data-ttu-id="2fc7a-104">tblPrincipalType contém tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="2fc7a-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-105">**Columns**</span></span>

|<span data-ttu-id="2fc7a-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-106">**Column**</span></span>|<span data-ttu-id="2fc7a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-107">**Type**</span></span>|<span data-ttu-id="2fc7a-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2fc7a-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="2fc7a-109">ptypeID</span></span>  <br/> |<span data-ttu-id="2fc7a-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="2fc7a-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="2fc7a-111">ID do tipo principal.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="2fc7a-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="2fc7a-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="2fc7a-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="2fc7a-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="2fc7a-114">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="2fc7a-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="2fc7a-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="2fc7a-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="2fc7a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="2fc7a-117">Verdadeiro se o tipo corresponder às entidades de segurança usadas para fins internos.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="2fc7a-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="2fc7a-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="2fc7a-119">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="2fc7a-119">bit, not null</span></span>  <br/> |<span data-ttu-id="2fc7a-120">Verdadeiro se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="2fc7a-121">**Chave**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-121">**Key**</span></span>

|<span data-ttu-id="2fc7a-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-122">**Column**</span></span>|<span data-ttu-id="2fc7a-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2fc7a-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="2fc7a-124">ptypeID</span></span>  <br/> |<span data-ttu-id="2fc7a-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="2fc7a-126">**Valores principais**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-126">**Principal Values**</span></span>

|<span data-ttu-id="2fc7a-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-127">**ID**</span></span>|<span data-ttu-id="2fc7a-128">**Função**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-128">**Role**</span></span>|<span data-ttu-id="2fc7a-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-129">**Description**</span></span>|<span data-ttu-id="2fc7a-130">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2fc7a-131">1</span><span class="sxs-lookup"><span data-stu-id="2fc7a-131">1</span></span>  <br/> |<span data-ttu-id="2fc7a-132">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="2fc7a-132">Any</span></span>  <br/> |<span data-ttu-id="2fc7a-133">Entidade de segurança genérica sem tipo conhecido.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-133">Generic principal with no known type.</span></span> <span data-ttu-id="2fc7a-134">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="2fc7a-135">2</span><span class="sxs-lookup"><span data-stu-id="2fc7a-135">2</span></span>  <br/> |<span data-ttu-id="2fc7a-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="2fc7a-136">AnyUser</span></span>  <br/> |<span data-ttu-id="2fc7a-137">Entidade de usuário genérica do tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-137">Generic principal of user type.</span></span> <span data-ttu-id="2fc7a-138">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="2fc7a-139">Sim</span><span class="sxs-lookup"><span data-stu-id="2fc7a-139">Yes</span></span>  <br/> |
|<span data-ttu-id="2fc7a-140">3</span><span class="sxs-lookup"><span data-stu-id="2fc7a-140">3</span></span>  <br/> |<span data-ttu-id="2fc7a-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="2fc7a-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="2fc7a-142">Entidade de segurança genérica com semântica de grupo.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-142">Generic principal with group semantic.</span></span> <span data-ttu-id="2fc7a-143">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="2fc7a-144">4</span><span class="sxs-lookup"><span data-stu-id="2fc7a-144">4</span></span>  <br/> |<span data-ttu-id="2fc7a-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="2fc7a-145">SystemUser</span></span>  <br/> |<span data-ttu-id="2fc7a-146">Principal usado internamente pelo servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="2fc7a-147">5</span><span class="sxs-lookup"><span data-stu-id="2fc7a-147">5</span></span>  <br/> |<span data-ttu-id="2fc7a-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="2fc7a-148">User</span></span>  <br/> |<span data-ttu-id="2fc7a-149">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-149">Regular user.</span></span>  <br/> |<span data-ttu-id="2fc7a-150">Sim</span><span class="sxs-lookup"><span data-stu-id="2fc7a-150">Yes</span></span>  <br/> |
|<span data-ttu-id="2fc7a-151">8</span><span class="sxs-lookup"><span data-stu-id="2fc7a-151">8</span></span>  <br/> |<span data-ttu-id="2fc7a-152">CLONA</span><span class="sxs-lookup"><span data-stu-id="2fc7a-152">DC</span></span>  <br/> |<span data-ttu-id="2fc7a-153">Controlador de domínio dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="2fc7a-154">9</span><span class="sxs-lookup"><span data-stu-id="2fc7a-154">9</span></span>  <br/> |<span data-ttu-id="2fc7a-155">Grupos</span><span class="sxs-lookup"><span data-stu-id="2fc7a-155">Group</span></span>  <br/> |<span data-ttu-id="2fc7a-156">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="2fc7a-157">254</span><span class="sxs-lookup"><span data-stu-id="2fc7a-157">10</span></span>  <br/> |<span data-ttu-id="2fc7a-158">La</span><span class="sxs-lookup"><span data-stu-id="2fc7a-158">Folder</span></span>  <br/> |<span data-ttu-id="2fc7a-159">Contêiner ou unidade organizacional do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2fc7a-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="2fc7a-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="2fc7a-160">See also</span></span>

[<span data-ttu-id="2fc7a-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="2fc7a-161">tblPrincipal</span></span>](tblprincipal.md)
