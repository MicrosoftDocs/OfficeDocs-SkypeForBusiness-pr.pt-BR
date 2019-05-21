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
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contém tipos principais para categorizar o que está na tabela tblPrincipal.
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295241"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="cd47a-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="cd47a-103">tblPrincipalType</span></span>
 
<span data-ttu-id="cd47a-104">tblPrincipalType contém tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="cd47a-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="cd47a-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="cd47a-105">**Columns**</span></span>

|<span data-ttu-id="cd47a-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cd47a-106">**Column**</span></span>|<span data-ttu-id="cd47a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cd47a-107">**Type**</span></span>|<span data-ttu-id="cd47a-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cd47a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cd47a-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="cd47a-109">ptypeID</span></span>  <br/> |<span data-ttu-id="cd47a-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="cd47a-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="cd47a-111">ID do tipo principal.</span><span class="sxs-lookup"><span data-stu-id="cd47a-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="cd47a-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="cd47a-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="cd47a-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="cd47a-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="cd47a-114">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="cd47a-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="cd47a-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="cd47a-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="cd47a-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="cd47a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="cd47a-117">Verdadeiro se o tipo corresponder às entidades de segurança usadas para fins internos.</span><span class="sxs-lookup"><span data-stu-id="cd47a-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="cd47a-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="cd47a-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="cd47a-119">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="cd47a-119">bit, not null</span></span>  <br/> |<span data-ttu-id="cd47a-120">Verdadeiro se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="cd47a-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="cd47a-121">**Chave**</span><span class="sxs-lookup"><span data-stu-id="cd47a-121">**Key**</span></span>

|<span data-ttu-id="cd47a-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cd47a-122">**Column**</span></span>|<span data-ttu-id="cd47a-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cd47a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cd47a-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="cd47a-124">ptypeID</span></span>  <br/> |<span data-ttu-id="cd47a-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="cd47a-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="cd47a-126">**Valores principais**</span><span class="sxs-lookup"><span data-stu-id="cd47a-126">**Principal Values**</span></span>

|<span data-ttu-id="cd47a-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="cd47a-127">**ID**</span></span>|<span data-ttu-id="cd47a-128">**Função**</span><span class="sxs-lookup"><span data-stu-id="cd47a-128">**Role**</span></span>|<span data-ttu-id="cd47a-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cd47a-129">**Description**</span></span>|<span data-ttu-id="cd47a-130">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="cd47a-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cd47a-131">1</span><span class="sxs-lookup"><span data-stu-id="cd47a-131">1</span></span>  <br/> |<span data-ttu-id="cd47a-132">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="cd47a-132">Any</span></span>  <br/> |<span data-ttu-id="cd47a-133">Entidade de segurança genérica sem tipo conhecido.</span><span class="sxs-lookup"><span data-stu-id="cd47a-133">Generic principal with no known type.</span></span> <span data-ttu-id="cd47a-134">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="cd47a-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="cd47a-135">2</span><span class="sxs-lookup"><span data-stu-id="cd47a-135">2</span></span>  <br/> |<span data-ttu-id="cd47a-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="cd47a-136">AnyUser</span></span>  <br/> |<span data-ttu-id="cd47a-137">Entidade de usuário genérica do tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="cd47a-137">Generic principal of user type.</span></span> <span data-ttu-id="cd47a-138">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="cd47a-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="cd47a-139">Sim</span><span class="sxs-lookup"><span data-stu-id="cd47a-139">Yes</span></span>  <br/> |
|<span data-ttu-id="cd47a-140">3</span><span class="sxs-lookup"><span data-stu-id="cd47a-140">3</span></span>  <br/> |<span data-ttu-id="cd47a-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="cd47a-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="cd47a-142">Entidade de segurança genérica com semântica de grupo.</span><span class="sxs-lookup"><span data-stu-id="cd47a-142">Generic principal with group semantic.</span></span> <span data-ttu-id="cd47a-143">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="cd47a-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="cd47a-144">4</span><span class="sxs-lookup"><span data-stu-id="cd47a-144">4</span></span>  <br/> |<span data-ttu-id="cd47a-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="cd47a-145">SystemUser</span></span>  <br/> |<span data-ttu-id="cd47a-146">Principal usado internamente pelo servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cd47a-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="cd47a-147">5</span><span class="sxs-lookup"><span data-stu-id="cd47a-147">5</span></span>  <br/> |<span data-ttu-id="cd47a-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="cd47a-148">User</span></span>  <br/> |<span data-ttu-id="cd47a-149">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="cd47a-149">Regular user.</span></span>  <br/> |<span data-ttu-id="cd47a-150">Sim</span><span class="sxs-lookup"><span data-stu-id="cd47a-150">Yes</span></span>  <br/> |
|<span data-ttu-id="cd47a-151">08</span><span class="sxs-lookup"><span data-stu-id="cd47a-151">8</span></span>  <br/> |<span data-ttu-id="cd47a-152">CLONA</span><span class="sxs-lookup"><span data-stu-id="cd47a-152">DC</span></span>  <br/> |<span data-ttu-id="cd47a-153">Controlador de domínio dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cd47a-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="cd47a-154">222</span><span class="sxs-lookup"><span data-stu-id="cd47a-154">9</span></span>  <br/> |<span data-ttu-id="cd47a-155">Grupos</span><span class="sxs-lookup"><span data-stu-id="cd47a-155">Group</span></span>  <br/> |<span data-ttu-id="cd47a-156">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cd47a-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="cd47a-157">254</span><span class="sxs-lookup"><span data-stu-id="cd47a-157">10</span></span>  <br/> |<span data-ttu-id="cd47a-158">La</span><span class="sxs-lookup"><span data-stu-id="cd47a-158">Folder</span></span>  <br/> |<span data-ttu-id="cd47a-159">Contêiner ou unidade organizacional do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cd47a-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="cd47a-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="cd47a-160">See also</span></span>

[<span data-ttu-id="cd47a-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="cd47a-161">tblPrincipal</span></span>](tblprincipal.md)
