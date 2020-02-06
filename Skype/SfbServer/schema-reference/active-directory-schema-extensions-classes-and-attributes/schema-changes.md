---
title: Alterações de esquema no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implantar e operar o Skype for Business Server, você deve preparar os serviços de domínio Active Directory estendendo o esquema. As extensões de esquema adicionam as classes e os atributos necessários para o Skype for Business Server.
ms.openlocfilehash: 0c3765fe36b252cc03218a3fa4365c5cc36c7f48
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815479"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="00d2b-104">Alterações de esquema no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00d2b-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="00d2b-105">Antes de implantar e operar o Skype for Business Server, você deve preparar os serviços de domínio Active Directory estendendo o esquema.</span><span class="sxs-lookup"><span data-stu-id="00d2b-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="00d2b-106">As extensões de esquema adicionam as classes e os atributos necessários para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00d2b-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="00d2b-107">Se você estiver atualizando do Lync Server 2013 para o Skype for Business Server 2015, nenhuma alteração de esquema será feita e, portanto, este artigo não se aplica.</span><span class="sxs-lookup"><span data-stu-id="00d2b-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="00d2b-108">O Skype for Business Server exige várias classes e atributos novos e modifica algumas classes e atributos existentes.</span><span class="sxs-lookup"><span data-stu-id="00d2b-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="00d2b-109">Além disso, muitas informações de configuração do Skype for Business Server são armazenadas no repositório de gerenciamento central, em vez de no AD DS, como nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="00d2b-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="00d2b-110">As informações a seguir ainda são armazenadas no AD DS no Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="00d2b-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="00d2b-111">**Extensões de esquema**:</span><span class="sxs-lookup"><span data-stu-id="00d2b-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="00d2b-112">Extensões de objetos de usuário</span><span class="sxs-lookup"><span data-stu-id="00d2b-112">User object extensions</span></span>
    
  - <span data-ttu-id="00d2b-113">Extensões para classes que mantêm a compatibilidade com versões anteriores do Lync Server com suporte.</span><span class="sxs-lookup"><span data-stu-id="00d2b-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="00d2b-114">**Dados** (armazenados no esquema estendido do Skype for Business Server e em classes de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="00d2b-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="00d2b-115">URI (Uniform Resource Identifier) do usuário SIP e outras configurações do usuário</span><span class="sxs-lookup"><span data-stu-id="00d2b-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="00d2b-116">Objetos de contato para aplicativos como o assistente de grupo de resposta e conferência</span><span class="sxs-lookup"><span data-stu-id="00d2b-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="00d2b-117">Um ponteiro para o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="00d2b-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="00d2b-118">Conta de autenticação Kerberos (um objeto de computador opcional)</span><span class="sxs-lookup"><span data-stu-id="00d2b-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="00d2b-119">Este tópico descreve as alterações de esquema do Active Directory exigidas pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00d2b-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="00d2b-120">Ele não descreve as alterações de esquema que foram introduzidas por versões anteriores do Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="00d2b-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="00d2b-121">Para obter uma lista de classes e suas descrições, consulte [classes e descrições de esquema no Skype for Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="00d2b-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="00d2b-122">Para obter uma lista de atributos e suas descrições, consulte [atributos e descrições do esquema no Skype for Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="00d2b-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="00d2b-123">Para obter uma lista de classes com os atributos que elas podem conter, consulte [atributos de esquema por classe no Skype for Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="00d2b-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="00d2b-124">O prefixo msRTCSIP identifica classes e atributos que são específicos do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00d2b-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="00d2b-125">Novos atributos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="00d2b-125">New Active Directory Attributes</span></span>

<span data-ttu-id="00d2b-126">A tabela a seguir descreve os atributos do Active Directory que são adicionados pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00d2b-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="00d2b-127">**Atributos adicionados pelo Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="00d2b-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="00d2b-128">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="00d2b-128">**Attribute**</span></span>|<span data-ttu-id="00d2b-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="00d2b-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="00d2b-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="00d2b-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="00d2b-131">Esse atributo de vários valores contém identificadores para políticas de retenção que se aplicam ao usuário.</span><span class="sxs-lookup"><span data-stu-id="00d2b-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="00d2b-132">As políticas de retenção preservam os itens da caixa de correio para o usuário durante o período de espera.</span><span class="sxs-lookup"><span data-stu-id="00d2b-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="00d2b-133">Esse atributo é compartilhado com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="00d2b-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="00d2b-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="00d2b-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="00d2b-135">Esta é a ID do grupo de roteamento SIP.</span><span class="sxs-lookup"><span data-stu-id="00d2b-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="00d2b-136">Os usuários no mesmo grupo serão registrados no mesmo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="00d2b-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="00d2b-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="00d2b-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="00d2b-138">Esse atributo é usado para armazenar o back-end do SQL Server espelhado usado pelo pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="00d2b-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="00d2b-139">Classes modificadas do Active Directory</span><span class="sxs-lookup"><span data-stu-id="00d2b-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="00d2b-140">A tabela a seguir descreve as classes do Active Directory modificadas pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00d2b-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="00d2b-141">**Classes modificadas pelo Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="00d2b-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="00d2b-142">**Classe**</span><span class="sxs-lookup"><span data-stu-id="00d2b-142">**Class**</span></span>|<span data-ttu-id="00d2b-143">**Alteração**</span><span class="sxs-lookup"><span data-stu-id="00d2b-143">**Change**</span></span>|<span data-ttu-id="00d2b-144">**Classe ou atributo**</span><span class="sxs-lookup"><span data-stu-id="00d2b-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="00d2b-145">Usuário</span><span class="sxs-lookup"><span data-stu-id="00d2b-145">User</span></span>  <br/> |<span data-ttu-id="00d2b-146">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="00d2b-146">add: mayContain</span></span>  <br/> <span data-ttu-id="00d2b-147">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="00d2b-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="00d2b-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="00d2b-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="00d2b-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="00d2b-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="00d2b-150">Entrando</span><span class="sxs-lookup"><span data-stu-id="00d2b-150">Contact</span></span>  <br/> |<span data-ttu-id="00d2b-151">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="00d2b-151">add: mayContain</span></span>  <br/> <span data-ttu-id="00d2b-152">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="00d2b-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="00d2b-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="00d2b-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="00d2b-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="00d2b-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="00d2b-155">E-mail-destinatário</span><span class="sxs-lookup"><span data-stu-id="00d2b-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="00d2b-156">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="00d2b-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="00d2b-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="00d2b-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="00d2b-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="00d2b-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="00d2b-159">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="00d2b-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="00d2b-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="00d2b-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

