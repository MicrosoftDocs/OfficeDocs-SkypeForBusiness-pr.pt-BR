---
title: 'Lync Server 2013: alterações de esquema no Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bbe1c08b7d03042be2c03511103bfa4e43d39d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="a4c89-102">Alterações de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4c89-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4c89-103">_**Tópico da última modificação:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="a4c89-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a4c89-104">Antes de implantar e operar o Lync Server 2013, você deve preparar os serviços de domínio Active Directory estendendo o esquema.</span><span class="sxs-lookup"><span data-stu-id="a4c89-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="a4c89-105">As extensões de esquema adicionam as classes e os atributos necessários para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4c89-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="a4c89-106">O Lync Server 2013 requer várias novas classes e atributos e modifica algumas classes e atributos existentes.</span><span class="sxs-lookup"><span data-stu-id="a4c89-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="a4c89-107">Além disso, muitas informações de configuração para o Lync Server 2013 são armazenadas no repositório de gerenciamento central, em vez de no AD DS, como nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="a4c89-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="a4c89-108">As informações a seguir ainda são armazenadas no AD DS no Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="a4c89-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="a4c89-109">**Extensões de esquema**:</span><span class="sxs-lookup"><span data-stu-id="a4c89-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="a4c89-110">Extensões de objetos de usuário</span><span class="sxs-lookup"><span data-stu-id="a4c89-110">User object extensions</span></span>
    
      - <span data-ttu-id="a4c89-111">Extensões para o Office Communications Server 2007 e o Office Communications Server 2007 R2 classes para manter a compatibilidade com versões anteriores com suporte</span><span class="sxs-lookup"><span data-stu-id="a4c89-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="a4c89-112">**Dados** do (armazenado no esquema estendido do Lync Server e em classes de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="a4c89-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="a4c89-113">URI (Uniform Resource Identifier) do usuário SIP e outras configurações do usuário</span><span class="sxs-lookup"><span data-stu-id="a4c89-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="a4c89-114">Objetos de contato para aplicativos como o assistente de grupo de resposta e conferência</span><span class="sxs-lookup"><span data-stu-id="a4c89-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="a4c89-115">Um ponteiro para o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="a4c89-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="a4c89-116">Conta de autenticação Kerberos (um objeto de computador opcional)</span><span class="sxs-lookup"><span data-stu-id="a4c89-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="a4c89-117">Este tópico descreve as alterações de esquema do Active Directory exigidas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4c89-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="a4c89-118">Ele não descreve as alterações de esquema que foram introduzidas por versões anteriores do Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="a4c89-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="a4c89-119">Para obter uma lista de classes e suas descrições, consulte [classes de esquema e descrições no Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="a4c89-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="a4c89-120">Para obter uma lista de atributos e suas descrições, consulte [atributos e descrições do esquema no Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="a4c89-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="a4c89-121">Para obter uma lista de classes com os atributos que elas podem conter, consulte [atributos de esquema por classe no Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="a4c89-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="a4c89-122">O prefixo msRTCSIP identifica classes e atributos que são específicos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4c89-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="a4c89-123">Novos atributos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="a4c89-123">New Active Directory Attributes</span></span>

<span data-ttu-id="a4c89-124">A tabela a seguir descreve os atributos do Active Directory que são adicionados pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4c89-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="a4c89-125">Atributos adicionados pelo Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4c89-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4c89-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="a4c89-126">Attribute</span></span></th>
<th><span data-ttu-id="a4c89-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4c89-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4c89-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a4c89-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="a4c89-129">Esse atributo de vários valores contém identificadores para políticas de retenção que se aplicam ao usuário.</span><span class="sxs-lookup"><span data-stu-id="a4c89-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="a4c89-130">As políticas de retenção preservam os itens da caixa de correio para o usuário durante o período de espera.</span><span class="sxs-lookup"><span data-stu-id="a4c89-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="a4c89-131">Esse atributo é compartilhado com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a4c89-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c89-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a4c89-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="a4c89-133">Esta é a ID do grupo de roteamento SIP.</span><span class="sxs-lookup"><span data-stu-id="a4c89-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="a4c89-134">Os usuários no mesmo grupo serão registrados no mesmo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="a4c89-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c89-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="a4c89-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="a4c89-136">Esse atributo é usado para armazenar o back-end do SQL Server espelhado usado pelo pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="a4c89-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="a4c89-137">Classes modificadas do Active Directory</span><span class="sxs-lookup"><span data-stu-id="a4c89-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="a4c89-138">A tabela a seguir descreve as classes do Active Directory modificadas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4c89-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="a4c89-139">Classes modificadas pelo Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4c89-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4c89-140">Classe</span><span class="sxs-lookup"><span data-stu-id="a4c89-140">Class</span></span></th>
<th><span data-ttu-id="a4c89-141">Alteração</span><span class="sxs-lookup"><span data-stu-id="a4c89-141">Change</span></span></th>
<th><span data-ttu-id="a4c89-142">Classe ou atributo</span><span class="sxs-lookup"><span data-stu-id="a4c89-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4c89-143">Usuário</span><span class="sxs-lookup"><span data-stu-id="a4c89-143">User</span></span></p></td>
<td><p><span data-ttu-id="a4c89-144">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="a4c89-144">add: mayContain</span></span></p>
<p><span data-ttu-id="a4c89-145">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="a4c89-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="a4c89-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a4c89-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="a4c89-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a4c89-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c89-148">Entrando</span><span class="sxs-lookup"><span data-stu-id="a4c89-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="a4c89-149">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="a4c89-149">add: mayContain</span></span></p>
<p><span data-ttu-id="a4c89-150">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="a4c89-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="a4c89-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a4c89-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="a4c89-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a4c89-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c89-153">E-mail-destinatário</span><span class="sxs-lookup"><span data-stu-id="a4c89-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="a4c89-154">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="a4c89-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="a4c89-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a4c89-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c89-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="a4c89-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="a4c89-157">Adicionar: mayContain</span><span class="sxs-lookup"><span data-stu-id="a4c89-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="a4c89-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="a4c89-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

