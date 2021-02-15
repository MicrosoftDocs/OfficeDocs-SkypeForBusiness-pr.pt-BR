---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: PrincipalType contém os tipos principais para categorizar o que está na tabela tblPrincipal.
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831531"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="b4421-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="b4421-103">tblPrincipalType</span></span>
 
<span data-ttu-id="b4421-104">PrincipalType contém os tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="b4421-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="b4421-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="b4421-105">**Columns**</span></span>

|<span data-ttu-id="b4421-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b4421-106">**Column**</span></span>|<span data-ttu-id="b4421-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b4421-107">**Type**</span></span>|<span data-ttu-id="b4421-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b4421-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4421-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b4421-109">ptypeID</span></span>  <br/> |<span data-ttu-id="b4421-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="b4421-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b4421-111">ID do tipo principal.</span><span class="sxs-lookup"><span data-stu-id="b4421-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="b4421-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="b4421-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="b4421-113">não nulo nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b4421-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b4421-114">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="b4421-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="b4421-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="b4421-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="b4421-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="b4421-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b4421-117">True se o tipo corresponder às entidades que são usadas para fins internos.</span><span class="sxs-lookup"><span data-stu-id="b4421-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="b4421-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="b4421-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="b4421-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="b4421-119">bit, not null</span></span>  <br/> |<span data-ttu-id="b4421-120">True se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="b4421-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="b4421-121">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b4421-121">**Key**</span></span>

|<span data-ttu-id="b4421-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b4421-122">**Column**</span></span>|<span data-ttu-id="b4421-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b4421-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4421-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b4421-124">ptypeID</span></span>  <br/> |<span data-ttu-id="b4421-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="b4421-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="b4421-126">**Valores principais**</span><span class="sxs-lookup"><span data-stu-id="b4421-126">**Principal Values**</span></span>

|<span data-ttu-id="b4421-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="b4421-127">**ID**</span></span>|<span data-ttu-id="b4421-128">**Função**</span><span class="sxs-lookup"><span data-stu-id="b4421-128">**Role**</span></span>|<span data-ttu-id="b4421-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b4421-129">**Description**</span></span>|<span data-ttu-id="b4421-130">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="b4421-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b4421-131">1 </span><span class="sxs-lookup"><span data-stu-id="b4421-131">1</span></span>  <br/> |<span data-ttu-id="b4421-132">Qualquer</span><span class="sxs-lookup"><span data-stu-id="b4421-132">Any</span></span>  <br/> |<span data-ttu-id="b4421-p101">Entidade genérica sem um tipo conhecido. Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="b4421-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="b4421-135">2 </span><span class="sxs-lookup"><span data-stu-id="b4421-135">2</span></span>  <br/> |<span data-ttu-id="b4421-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="b4421-136">AnyUser</span></span>  <br/> |<span data-ttu-id="b4421-p102">Entidade de segurança genérica do tipo de usuário. Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="b4421-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="b4421-139">Sim</span><span class="sxs-lookup"><span data-stu-id="b4421-139">Yes</span></span>  <br/> |
|<span data-ttu-id="b4421-140">3 </span><span class="sxs-lookup"><span data-stu-id="b4421-140">3</span></span>  <br/> |<span data-ttu-id="b4421-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="b4421-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="b4421-p103">Entidade de segurança genérica com semântica de grupo. Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="b4421-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="b4421-144">4 </span><span class="sxs-lookup"><span data-stu-id="b4421-144">4</span></span>  <br/> |<span data-ttu-id="b4421-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="b4421-145">SystemUser</span></span>  <br/> |<span data-ttu-id="b4421-146">Entidade de segurança usada internamente pelo Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="b4421-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="b4421-147">5 </span><span class="sxs-lookup"><span data-stu-id="b4421-147">5</span></span>  <br/> |<span data-ttu-id="b4421-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="b4421-148">User</span></span>  <br/> |<span data-ttu-id="b4421-149">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="b4421-149">Regular user.</span></span>  <br/> |<span data-ttu-id="b4421-150">Sim</span><span class="sxs-lookup"><span data-stu-id="b4421-150">Yes</span></span>  <br/> |
|<span data-ttu-id="b4421-151">8 </span><span class="sxs-lookup"><span data-stu-id="b4421-151">8</span></span>  <br/> |<span data-ttu-id="b4421-152">DC</span><span class="sxs-lookup"><span data-stu-id="b4421-152">DC</span></span>  <br/> |<span data-ttu-id="b4421-153">Controlador de domínio dos Serviços de Domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4421-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="b4421-154">9 </span><span class="sxs-lookup"><span data-stu-id="b4421-154">9</span></span>  <br/> |<span data-ttu-id="b4421-155">Group</span><span class="sxs-lookup"><span data-stu-id="b4421-155">Group</span></span>  <br/> |<span data-ttu-id="b4421-156">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4421-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="b4421-157">10 </span><span class="sxs-lookup"><span data-stu-id="b4421-157">10</span></span>  <br/> |<span data-ttu-id="b4421-158">Folder</span><span class="sxs-lookup"><span data-stu-id="b4421-158">Folder</span></span>  <br/> |<span data-ttu-id="b4421-159">Unidade organizacional ou recipiente do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4421-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="b4421-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="b4421-160">See also</span></span>

[<span data-ttu-id="b4421-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="b4421-161">tblPrincipal</span></span>](tblprincipal.md)
