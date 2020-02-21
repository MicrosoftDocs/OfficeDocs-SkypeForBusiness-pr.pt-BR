---
title: 'Lync Server 2013: alterações de esquema no Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70b090f59c0a0f8510d778ef659def77cfd0747
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="6eb3b-102">Alterações de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb3b-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eb3b-103">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6eb3b-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6eb3b-104">Antes de implantar e operar o Lync Server 2013, você deve preparar os serviços de domínio do Active Directory, estendendo o esquema.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="6eb3b-105">As extensões de esquema adicionam as classes e os atributos necessários para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="6eb3b-106">O Lync Server 2013 requer várias classes e atributos novos e modifica algumas classes e atributos existentes.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="6eb3b-107">Além disso, muitas informações de configuração para o Lync Server 2013 são armazenadas no repositório de gerenciamento central, em vez de no AD DS, como nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="6eb3b-108">As informações a seguir ainda são armazenadas no AD DS no Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6eb3b-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="6eb3b-109">**Extensões de esquema**:</span><span class="sxs-lookup"><span data-stu-id="6eb3b-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="6eb3b-110">Extensões do objeto do usuário</span><span class="sxs-lookup"><span data-stu-id="6eb3b-110">User object extensions</span></span>
    
      - <span data-ttu-id="6eb3b-111">Extensões para o Office Communications Server 2007 e o Office Communications Server 2007 R2 classes para manter a compatibilidade com versões anteriores com suporte</span><span class="sxs-lookup"><span data-stu-id="6eb3b-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="6eb3b-112">**Dados** (armazenados no esquema estendido do Lync Server e nas classes de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="6eb3b-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="6eb3b-113">URI (Uniform Resource Identifier) SIP do usuário e outras configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="6eb3b-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="6eb3b-114">Objetos de contato para aplicativos, como Grupo de Respostas e Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="6eb3b-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="6eb3b-115">Um ponteiro para o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="6eb3b-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="6eb3b-116">Conta de autenticação Kerberos (um objeto de computador opcional)</span><span class="sxs-lookup"><span data-stu-id="6eb3b-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="6eb3b-117">Este tópico descreve as alterações de esquema do Active Directory exigidas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="6eb3b-118">Ela não descreve as alterações de esquema que foram introduzidas por versões anteriores do Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="6eb3b-119">Para obter uma lista de classes e suas descrições, consulte [classes e descrições de esquema no Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="6eb3b-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="6eb3b-120">Para obter uma lista de atributos e suas descrições, consulte [atributos e descrições de esquema no Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="6eb3b-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="6eb3b-121">Para obter uma lista de classes com os atributos que eles podem conter, confira [atributos de esquema por classe no Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="6eb3b-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="6eb3b-122">O prefixo msRTCSIP identifica classes e atributos específicos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="6eb3b-123">Novos atributos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="6eb3b-123">New Active Directory Attributes</span></span>

<span data-ttu-id="6eb3b-124">A tabela a seguir descreve os atributos do Active Directory que são adicionados pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="6eb3b-125">Atributos adicionados pelo Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb3b-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6eb3b-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="6eb3b-126">Attribute</span></span></th>
<th><span data-ttu-id="6eb3b-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="6eb3b-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6eb3b-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="6eb3b-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-129">Este atributo de vários valores mantém identificadores para manter políticas aplicadas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="6eb3b-130">Políticas de retenção preservam os itens das caixas de correio para o usuário pela duração da retenção.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="6eb3b-131">Este atributo é compartilhado com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb3b-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6eb3b-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-p105">Este é o ID do grupo de roteamento SIP. Os usuários no mesmo grupo irão ser registrados para o mesmo Servidor de Front-end.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb3b-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="6eb3b-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-136">Este atributo é usado para armazenar o backend do SQL Server espelhado usado pelo pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="6eb3b-137">Classes do Active Directory modificadas</span><span class="sxs-lookup"><span data-stu-id="6eb3b-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="6eb3b-138">A tabela a seguir descreve as classes do Active Directory modificadas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="6eb3b-139">Classes modificadas pelo Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb3b-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6eb3b-140">Classe</span><span class="sxs-lookup"><span data-stu-id="6eb3b-140">Class</span></span></th>
<th><span data-ttu-id="6eb3b-141">Alteração</span><span class="sxs-lookup"><span data-stu-id="6eb3b-141">Change</span></span></th>
<th><span data-ttu-id="6eb3b-142">Classe ou atributo</span><span class="sxs-lookup"><span data-stu-id="6eb3b-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6eb3b-143">Usuário</span><span class="sxs-lookup"><span data-stu-id="6eb3b-143">User</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-144">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="6eb3b-144">add: mayContain</span></span></p>
<p><span data-ttu-id="6eb3b-145">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="6eb3b-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="6eb3b-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="6eb3b-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6eb3b-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb3b-148">Contato</span><span class="sxs-lookup"><span data-stu-id="6eb3b-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-149">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="6eb3b-149">add: mayContain</span></span></p>
<p><span data-ttu-id="6eb3b-150">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="6eb3b-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="6eb3b-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="6eb3b-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6eb3b-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb3b-153">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="6eb3b-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-154">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="6eb3b-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="6eb3b-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb3b-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="6eb3b-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-157">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="6eb3b-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="6eb3b-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="6eb3b-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

