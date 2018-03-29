---
title: Alterações de esquema no Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implantar e operar o Skype para Business Server, você deve preparar o Active Directory Domain Services estendendo o esquema. As extensões de esquema adicionam as classes e atributos que são exigidos pelo Skype para Business Server.
ms.openlocfilehash: 42b4417311c557323535aa03053ccb03d95cc840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="b389d-104">Alterações de esquema no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b389d-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="b389d-105">Antes de implantar e operar o Skype para Business Server, você deve preparar o Active Directory Domain Services estendendo o esquema.</span><span class="sxs-lookup"><span data-stu-id="b389d-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="b389d-106">As extensões de esquema adicionam as classes e atributos que são exigidos pelo Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b389d-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span> 
  
<span data-ttu-id="b389d-107">Skype para Business Server requer várias novas classes e atributos e modifica alguns atributos e classes existentes.</span><span class="sxs-lookup"><span data-stu-id="b389d-107">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="b389d-108">Além disso, a quantidade informações de configuração de Skype para Business Server são armazenadas no repositório de gerenciamento Central ao invés de no AD DS como nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="b389d-108">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="b389d-109">As seguintes informações ainda estão armazenadas no AD DS em Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="b389d-109">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="b389d-110">**Extensões de esquema**:</span><span class="sxs-lookup"><span data-stu-id="b389d-110">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="b389d-111">Extensões de objetos de usuário</span><span class="sxs-lookup"><span data-stu-id="b389d-111">User object extensions</span></span>
    
  - <span data-ttu-id="b389d-112">Extensões para classes manter compatibilidade com versões anteriores do Microsoft Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b389d-112">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="b389d-113">**Dados** (armazenados no Skype para esquema estendido do servidor de negócios e nas classes de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="b389d-113">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="b389d-114">Usuário SIP URI Uniform Resource Identifier () e outras configurações do usuário</span><span class="sxs-lookup"><span data-stu-id="b389d-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="b389d-115">Objetos de contato para aplicativos, como o grupo de resposta e Atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="b389d-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="b389d-116">Um ponteiro para o repositório de gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="b389d-116">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="b389d-117">Conta de autenticação Kerberos (um objeto de computador opcional)</span><span class="sxs-lookup"><span data-stu-id="b389d-117">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="b389d-118">Este tópico descreve as alterações de esquema do Active Directory exigidas pelo Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b389d-118">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="b389d-119">Alterações de esquema introduzidas por versões anteriores do Office Communications Server não são descritos.</span><span class="sxs-lookup"><span data-stu-id="b389d-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="b389d-120">Para obter uma lista das classes e suas descrições, consulte [classes de esquema e descrições Skype para Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="b389d-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="b389d-121">Para obter uma lista de atributos e suas descrições, consulte [atributos de esquema e descrições Skype para Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="b389d-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="b389d-122">Para obter uma lista das classes com os atributos, eles podem conter, consulte [atributos de esquema por classe no Skype para Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="b389d-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="b389d-123">O prefixo msRTCSIP identifica classes e atributos específicos do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b389d-123">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="b389d-124">Novos atributos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="b389d-124">New Active Directory Attributes</span></span>

<span data-ttu-id="b389d-125">A tabela a seguir descreve os atributos do Active Directory que são adicionados pelo Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b389d-125">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="b389d-126">**Atributos adicionados pelo Skype para Business Server**</span><span class="sxs-lookup"><span data-stu-id="b389d-126">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="b389d-127">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="b389d-127">**Attribute**</span></span>|<span data-ttu-id="b389d-128">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b389d-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b389d-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="b389d-129">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="b389d-130">Este atributo de valor múltiplos contém identificadores para manter as políticas que se aplicam ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b389d-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="b389d-131">Mantenha políticas preservem itens de caixa de correio para o usuário para a duração da retenção.</span><span class="sxs-lookup"><span data-stu-id="b389d-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="b389d-132">Este atributo é compartilhado com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b389d-132">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="b389d-133">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="b389d-133">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="b389d-134">Este é o SIP roteamento identificação do grupo.</span><span class="sxs-lookup"><span data-stu-id="b389d-134">This is the SIP routing group ID.</span></span> <span data-ttu-id="b389d-135">Os usuários no mesmo grupo, registre-se para o mesmo servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="b389d-135">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="b389d-136">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="b389d-136">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="b389d-137">Este atributo é usado para armazenar o backend do SQL Server espelhado usado pelo pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="b389d-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="b389d-138">Classes do Active Directory modificadas</span><span class="sxs-lookup"><span data-stu-id="b389d-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="b389d-139">A tabela a seguir descreve as classes do Active Directory que são modificadas pelo Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b389d-139">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="b389d-140">**Classes modificadas pelo Skype para Business Server**</span><span class="sxs-lookup"><span data-stu-id="b389d-140">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="b389d-141">**Classe**</span><span class="sxs-lookup"><span data-stu-id="b389d-141">**Class**</span></span>|<span data-ttu-id="b389d-142">**Alteração**</span><span class="sxs-lookup"><span data-stu-id="b389d-142">**Change**</span></span>|<span data-ttu-id="b389d-143">**Classe ou atributo**</span><span class="sxs-lookup"><span data-stu-id="b389d-143">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b389d-144">Usuário</span><span class="sxs-lookup"><span data-stu-id="b389d-144">User</span></span>  <br/> |<span data-ttu-id="b389d-145">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="b389d-145">add: mayContain</span></span>  <br/> <span data-ttu-id="b389d-146">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="b389d-146">add: mayContain</span></span>  <br/> |<span data-ttu-id="b389d-147">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b389d-147">ProxyAddresses</span></span>  <br/> <span data-ttu-id="b389d-148">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="b389d-148">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="b389d-149">Contato</span><span class="sxs-lookup"><span data-stu-id="b389d-149">Contact</span></span>  <br/> |<span data-ttu-id="b389d-150">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="b389d-150">add: mayContain</span></span>  <br/> <span data-ttu-id="b389d-151">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="b389d-151">add: mayContain</span></span>  <br/> |<span data-ttu-id="b389d-152">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b389d-152">ProxyAddresses</span></span>  <br/> <span data-ttu-id="b389d-153">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="b389d-153">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="b389d-154">Destinatário do email</span><span class="sxs-lookup"><span data-stu-id="b389d-154">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="b389d-155">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="b389d-155">add: mayContain</span></span>  <br/> |<span data-ttu-id="b389d-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="b389d-156">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="b389d-157">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="b389d-157">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="b389d-158">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="b389d-158">add: mayContain</span></span>  <br/> |<span data-ttu-id="b389d-159">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="b389d-159">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

