---
title: Alterações de esquema no Skype para Business Server
ms.reviewer: ''
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
ms.openlocfilehash: ba76f57197e9cd812163c8abac5f51005933eace
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874637"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="c2ecc-104">Alterações de esquema no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c2ecc-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="c2ecc-105">Antes de implantar e operar o Skype para Business Server, você deve preparar o Active Directory Domain Services estendendo o esquema.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="c2ecc-106">As extensões de esquema adicionam as classes e atributos que são exigidos pelo Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="c2ecc-107">Se você estiver atualizando do Lync Server 2013 para Skype para Business Server 2015, sem alterações de esquema são feitas e, portanto, este artigo não se aplica.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="c2ecc-108">Skype para Business Server requer várias novas classes e atributos e modifica alguns atributos e classes existentes.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="c2ecc-109">Além disso, a quantidade informações de configuração de Skype para Business Server são armazenadas no repositório de gerenciamento Central ao invés de no AD DS como nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="c2ecc-110">As seguintes informações ainda estão armazenadas no AD DS em Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="c2ecc-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="c2ecc-111">**Extensões de esquema**:</span><span class="sxs-lookup"><span data-stu-id="c2ecc-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="c2ecc-112">Extensões de objetos de usuário</span><span class="sxs-lookup"><span data-stu-id="c2ecc-112">User object extensions</span></span>
    
  - <span data-ttu-id="c2ecc-113">Extensões para classes manter compatibilidade com versões anteriores do Microsoft Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="c2ecc-114">**Dados** (armazenados no Skype para esquema estendido do servidor de negócios e nas classes de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="c2ecc-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="c2ecc-115">Usuário SIP URI Uniform Resource Identifier () e outras configurações do usuário</span><span class="sxs-lookup"><span data-stu-id="c2ecc-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="c2ecc-116">Objetos de contato para aplicativos, como o grupo de resposta e Atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="c2ecc-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="c2ecc-117">Um ponteiro para o repositório de gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="c2ecc-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="c2ecc-118">Conta de autenticação Kerberos (um objeto de computador opcional)</span><span class="sxs-lookup"><span data-stu-id="c2ecc-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="c2ecc-119">Este tópico descreve as alterações de esquema do Active Directory exigidas pelo Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="c2ecc-120">Alterações de esquema introduzidas por versões anteriores do Office Communications Server não são descritos.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="c2ecc-121">Para obter uma lista das classes e suas descrições, consulte [classes de esquema e descrições Skype para Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="c2ecc-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="c2ecc-122">Para obter uma lista de atributos e suas descrições, consulte [atributos de esquema e descrições Skype para Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="c2ecc-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="c2ecc-123">Para obter uma lista das classes com os atributos, eles podem conter, consulte [atributos de esquema por classe no Skype para Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="c2ecc-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="c2ecc-124">O prefixo msRTCSIP identifica classes e atributos específicos do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="c2ecc-125">Novos atributos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c2ecc-125">New Active Directory Attributes</span></span>

<span data-ttu-id="c2ecc-126">A tabela a seguir descreve os atributos do Active Directory que são adicionados pelo Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="c2ecc-127">**Atributos adicionados pelo Skype para Business Server**</span><span class="sxs-lookup"><span data-stu-id="c2ecc-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="c2ecc-128">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="c2ecc-128">**Attribute**</span></span>|<span data-ttu-id="c2ecc-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c2ecc-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c2ecc-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="c2ecc-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="c2ecc-131">Este atributo de valor múltiplos contém identificadores para manter as políticas que se aplicam ao usuário.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="c2ecc-132">Mantenha políticas preservem itens de caixa de correio para o usuário para a duração da retenção.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="c2ecc-133">Este atributo é compartilhado com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="c2ecc-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="c2ecc-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="c2ecc-135">Este é o SIP roteamento identificação do grupo.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="c2ecc-136">Os usuários no mesmo grupo, registre-se para o mesmo servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="c2ecc-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="c2ecc-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="c2ecc-138">Este atributo é usado para armazenar o backend do SQL Server espelhado usado pelo pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="c2ecc-139">Classes do Active Directory modificadas</span><span class="sxs-lookup"><span data-stu-id="c2ecc-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="c2ecc-140">A tabela a seguir descreve as classes do Active Directory que são modificadas pelo Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2ecc-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="c2ecc-141">**Classes modificadas pelo Skype para Business Server**</span><span class="sxs-lookup"><span data-stu-id="c2ecc-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="c2ecc-142">**Classe**</span><span class="sxs-lookup"><span data-stu-id="c2ecc-142">**Class**</span></span>|<span data-ttu-id="c2ecc-143">**Alteração**</span><span class="sxs-lookup"><span data-stu-id="c2ecc-143">**Change**</span></span>|<span data-ttu-id="c2ecc-144">**Classe ou atributo**</span><span class="sxs-lookup"><span data-stu-id="c2ecc-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2ecc-145">Usuário</span><span class="sxs-lookup"><span data-stu-id="c2ecc-145">User</span></span>  <br/> |<span data-ttu-id="c2ecc-146">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="c2ecc-146">add: mayContain</span></span>  <br/> <span data-ttu-id="c2ecc-147">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="c2ecc-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="c2ecc-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="c2ecc-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="c2ecc-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="c2ecc-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="c2ecc-150">Contato</span><span class="sxs-lookup"><span data-stu-id="c2ecc-150">Contact</span></span>  <br/> |<span data-ttu-id="c2ecc-151">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="c2ecc-151">add: mayContain</span></span>  <br/> <span data-ttu-id="c2ecc-152">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="c2ecc-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="c2ecc-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="c2ecc-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="c2ecc-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="c2ecc-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="c2ecc-155">Destinatário do email</span><span class="sxs-lookup"><span data-stu-id="c2ecc-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="c2ecc-156">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="c2ecc-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="c2ecc-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="c2ecc-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="c2ecc-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="c2ecc-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="c2ecc-159">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="c2ecc-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="c2ecc-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="c2ecc-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

