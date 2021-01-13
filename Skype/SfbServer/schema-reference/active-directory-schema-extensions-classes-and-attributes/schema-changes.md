---
title: Alterações de esquema no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implantar e operar o Skype for Business Server, você deve preparar os Serviços de Domínio Active Directory estendendo o esquema. As extensões de esquema adicionam as classes e atributos exigidos pelo Skype for Business Server.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813571"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="c7410-104">Alterações de esquema no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c7410-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="c7410-105">Antes de implantar e operar o Skype for Business Server, você deve preparar os Serviços de Domínio Active Directory estendendo o esquema.</span><span class="sxs-lookup"><span data-stu-id="c7410-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="c7410-106">As extensões de esquema adicionam as classes e atributos exigidos pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c7410-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="c7410-107">Se você estiver atualizando do Lync Server 2013 para o Skype for Business Server 2015, nenhuma alteração de esquema será feita e, portanto, este artigo não se aplica.</span><span class="sxs-lookup"><span data-stu-id="c7410-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="c7410-108">O Skype for Business Server requer várias classes e atributos novos e modifica algumas classes e atributos existentes.</span><span class="sxs-lookup"><span data-stu-id="c7410-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="c7410-109">Além disso, muitas informações de configuração do Skype for Business Server são armazenadas no armazenamento de Gerenciamento Central, e não no AD DS, como nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="c7410-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="c7410-110">As informações a seguir ainda são armazenadas no AD DS no Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="c7410-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="c7410-111">**Extensões de esquema**:</span><span class="sxs-lookup"><span data-stu-id="c7410-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="c7410-112">Extensões do objeto do usuário</span><span class="sxs-lookup"><span data-stu-id="c7410-112">User object extensions</span></span>
    
  - <span data-ttu-id="c7410-113">Extensões para classes para manter a compatibilidade com versões anteriores suportadas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7410-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="c7410-114">**Dados** (armazenados no esquema estendido do Skype for Business Server e em classes de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="c7410-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="c7410-115">URI (Uniform Resource Identifier) SIP do usuário e outras configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="c7410-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="c7410-116">Objetos de contato para aplicativos, como Grupo de Respostas e Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="c7410-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="c7410-117">Um ponteiro para o armazenamento de Gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="c7410-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="c7410-118">Conta de autenticação Kerberos (um objeto de computador opcional)</span><span class="sxs-lookup"><span data-stu-id="c7410-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="c7410-119">Este tópico descreve as alterações de esquema do Active Directory exigidas pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c7410-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="c7410-120">Ele não descreve as alterações de esquema introduzidas por versões anteriores do Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="c7410-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="c7410-121">Para uma lista de classes e suas descrições, consulte Classes e descrições de esquema [no Skype for Business Server.](schema-classes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="c7410-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="c7410-122">Para uma lista de atributos e suas descrições, consulte Atributos e descrições do esquema [no Skype for Business Server.](schema-attributes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="c7410-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="c7410-123">Para uma lista de classes com os atributos que elas podem conter, consulte Atributos de esquema por [classe no Skype for Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="c7410-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="c7410-124">O prefixo msRTCSIP identifica classes e atributos específicos do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c7410-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="c7410-125">Novos atributos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c7410-125">New Active Directory Attributes</span></span>

<span data-ttu-id="c7410-126">A tabela a seguir descreve os atributos do Active Directory adicionados pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c7410-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="c7410-127">**Atributos adicionados pelo Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="c7410-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="c7410-128">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="c7410-128">**Attribute**</span></span>|<span data-ttu-id="c7410-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c7410-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c7410-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="c7410-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="c7410-131">Este atributo de vários valores mantém identificadores para manter políticas aplicadas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="c7410-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="c7410-132">Políticas de retenção preservam os itens das caixas de correio para o usuário pela duração da retenção.</span><span class="sxs-lookup"><span data-stu-id="c7410-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="c7410-133">Esse atributo é compartilhado com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c7410-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="c7410-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="c7410-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="c7410-p106">Este é o ID do grupo de roteamento SIP. Os usuários no mesmo grupo irão ser registrados para o mesmo Servidor de Front-end.</span><span class="sxs-lookup"><span data-stu-id="c7410-p106">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="c7410-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="c7410-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="c7410-138">Esse atributo é usado para armazenar o back-end espelhado do SQL Server usado pelo pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="c7410-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="c7410-139">Classes do Active Directory modificadas</span><span class="sxs-lookup"><span data-stu-id="c7410-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="c7410-140">A tabela a seguir descreve as classes do Active Directory modificadas pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c7410-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="c7410-141">**Classes modificadas pelo Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="c7410-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="c7410-142">**Classe**</span><span class="sxs-lookup"><span data-stu-id="c7410-142">**Class**</span></span>|<span data-ttu-id="c7410-143">**Alteração**</span><span class="sxs-lookup"><span data-stu-id="c7410-143">**Change**</span></span>|<span data-ttu-id="c7410-144">**Classe ou atributo**</span><span class="sxs-lookup"><span data-stu-id="c7410-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c7410-145">Usuário</span><span class="sxs-lookup"><span data-stu-id="c7410-145">User</span></span>  <br/> |<span data-ttu-id="c7410-146">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="c7410-146">add: mayContain</span></span>  <br/> <span data-ttu-id="c7410-147">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="c7410-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="c7410-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="c7410-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="c7410-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="c7410-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="c7410-150">Contato</span><span class="sxs-lookup"><span data-stu-id="c7410-150">Contact</span></span>  <br/> |<span data-ttu-id="c7410-151">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="c7410-151">add: mayContain</span></span>  <br/> <span data-ttu-id="c7410-152">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="c7410-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="c7410-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="c7410-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="c7410-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="c7410-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="c7410-155">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="c7410-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="c7410-156">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="c7410-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="c7410-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="c7410-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="c7410-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="c7410-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="c7410-159">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="c7410-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="c7410-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="c7410-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

