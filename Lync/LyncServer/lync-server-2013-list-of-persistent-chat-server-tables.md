---
title: 'Lync Server 2013: Tabelas de lista de Servidores de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4902f0710752dd38c146b01bddcc44e135735201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="f263f-102">Tabelas de lista de Servidores de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f263f-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f263f-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f263f-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f263f-104">O esquema de banco de dados de chat persistente consiste nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f263f-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="f263f-105">Sincronização do Active Directory</span><span class="sxs-lookup"><span data-stu-id="f263f-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f263f-106">Tabela</span><span class="sxs-lookup"><span data-stu-id="f263f-106">Table</span></span></th>
<th><span data-ttu-id="f263f-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="f263f-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f263f-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-109">Contém os atuais cookies de sincronização de LDAP (Lightweight Directory Access Protocol).</span><span class="sxs-lookup"><span data-stu-id="f263f-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="f263f-110">Cada linha corresponde a um domínio de serviços de domínio do Active Directory que o servidor de chat persistente está monitorando ativamente para alterações.</span><span class="sxs-lookup"><span data-stu-id="f263f-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="f263f-111">(Somente os domínios do Active Directory que são relevantes para o servidor de chat persistente são representados nesta tabela).</span><span class="sxs-lookup"><span data-stu-id="f263f-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-113">Contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory e é uma das tabelas temporárias (juntamente com a tabela tblADUpdates) que é usada na primeira etapa da sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f263f-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="f263f-114">As alterações de associação são armazenadas, processadas ou ambas, apenas para grupos listados na tabela tblPrincipal ou que já têm Membros listados ali.</span><span class="sxs-lookup"><span data-stu-id="f263f-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f263f-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-116">Contém alterações nos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory e é uma das tabelas temporárias (juntamente com a tabela tblPrincipalMemberDifference) que é usada na primeira etapa do Active Directory Sincronizar.</span><span class="sxs-lookup"><span data-stu-id="f263f-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="f263f-117">As alterações no Active Directory são armazenadas, processadas ou ambas somente para entidades que já estão listadas na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="f263f-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-119">Contém associações de entidades de segurança.</span><span class="sxs-lookup"><span data-stu-id="f263f-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f263f-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-121">Contém as entidades de segurança que devem ser atualizadas a partir do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f263f-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-123">Contém afiliações que não podem ser atualizadas por algum motivo, geralmente devido a erros de acesso ao Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f263f-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="f263f-124">Esta tabela é apenas para fins informativos.</span><span class="sxs-lookup"><span data-stu-id="f263f-124">This table is for informational purposes only.</span></span> <span data-ttu-id="f263f-125">Seu conteúdo não é usado.</span><span class="sxs-lookup"><span data-stu-id="f263f-125">Its content is not used.</span></span></p>
<p><span data-ttu-id="f263f-126">As entidades de segurança com afiliações que não foram atualizadas corretamente são mantidas na tabela tblPrincipalMeta e recebem outra oportunidade de serem atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f263f-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="f263f-127">Entidades, afiliações, nós, escopos e funções</span><span class="sxs-lookup"><span data-stu-id="f263f-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f263f-128">Tabela</span><span class="sxs-lookup"><span data-stu-id="f263f-128">Table</span></span></th>
<th><span data-ttu-id="f263f-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="f263f-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f263f-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-131">Contém tipos de principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="f263f-131">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="f263f-132">Esta tabela é estática.</span><span class="sxs-lookup"><span data-stu-id="f263f-132">This table is static.</span></span> <span data-ttu-id="f263f-133">Ele é configurado durante a criação do banco de dados e não é alterado.</span><span class="sxs-lookup"><span data-stu-id="f263f-133">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-135">Contém todas as entidades (usuários, pastas, grupos e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="f263f-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="f263f-136">O servidor de chat persistente manipula isso como uma lista heterogênea e uniforme.</span><span class="sxs-lookup"><span data-stu-id="f263f-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="f263f-137">Várias colunas baseiam-se no tipo de cada entidade.</span><span class="sxs-lookup"><span data-stu-id="f263f-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="f263f-138">A maioria dessas entidades são cópias em cache de objetos armazenados no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f263f-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="f263f-139">A criação da cópia em cache na tabela principal desses objetos do Active Directory é chamada de <em>provisionamento</em>.</span><span class="sxs-lookup"><span data-stu-id="f263f-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="f263f-140">Algumas entidades de segurança são criadas de forma mais agressiva do que outras, e alguns objetos do Active Directory são ignorados completamente.</span><span class="sxs-lookup"><span data-stu-id="f263f-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f263f-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-142">Contém associações de entidades de segurança que descrevem associações nos grupos de segurança do Active Directory, contêineres do Active Directory e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="f263f-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-143"><a href="lync-server-2013-tblnode.md">tblNode no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-144">Contém o nó Category, conforme gerenciado no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f263f-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f263f-145"><a href="lync-server-2013-tblroletype.md">tblRoleType no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-146">Contém tipos de função e seus conjuntos de permissões associados.</span><span class="sxs-lookup"><span data-stu-id="f263f-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="f263f-147">Esta tabela de pesquisa é estática.</span><span class="sxs-lookup"><span data-stu-id="f263f-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-149">Contém escopos atribuídos a nós.</span><span class="sxs-lookup"><span data-stu-id="f263f-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f263f-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-151">Contém funções atribuídas a nós.</span><span class="sxs-lookup"><span data-stu-id="f263f-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-153">Contém os suplementos registrados que podem ser associados a nós.</span><span class="sxs-lookup"><span data-stu-id="f263f-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f263f-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-155">Contém somente os atributos de &quot;visibilidade&quot; e &quot;comportamento&quot; inseridos que são usados na tabela tblNode.</span><span class="sxs-lookup"><span data-stu-id="f263f-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-157">Contém os valores dos atributos de comportamento &quot;&quot; de visibilidade codificada "e" que são usados na tabela tblNode.</span><span class="sxs-lookup"><span data-stu-id="f263f-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="f263f-158">Convites, chats e outros suporte ao cliente</span><span class="sxs-lookup"><span data-stu-id="f263f-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f263f-159">Tabela</span><span class="sxs-lookup"><span data-stu-id="f263f-159">Table</span></span></th>
<th><span data-ttu-id="f263f-160">Descrição</span><span class="sxs-lookup"><span data-stu-id="f263f-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f263f-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-162">Contém convites para todos os usuários provisionados no sistema para todos os nós com convite automático habilitado.</span><span class="sxs-lookup"><span data-stu-id="f263f-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-163"><a href="lync-server-2013-tblchat.md">tblChat no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-164">Contém todas as mensagens de chat.</span><span class="sxs-lookup"><span data-stu-id="f263f-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f263f-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-166">Contém a ID do último convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="f263f-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-168">Contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="f263f-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f263f-169"><a href="lync-server-2013-tblpreference.md">tblPreference no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-170">Contém as preferências do cliente do usuário (usadas somente por clientes herdados).</span><span class="sxs-lookup"><span data-stu-id="f263f-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-172">Contém tokens temporários para fins de transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f263f-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="f263f-173">Cada vez que um arquivo é carregado ou baixado, o serviço de chat persistente gera um token que o cliente usa para acessar o repositório de arquivos do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="f263f-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="f263f-174">Suporte a servidor</span><span class="sxs-lookup"><span data-stu-id="f263f-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f263f-175">Tabela</span><span class="sxs-lookup"><span data-stu-id="f263f-175">Table</span></span></th>
<th><span data-ttu-id="f263f-176">Descrição</span><span class="sxs-lookup"><span data-stu-id="f263f-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f263f-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-178">Contém os servidores ativos no pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f263f-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-180">Contém o bloqueio do administrador para executar alguns comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="f263f-180">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="f263f-181">A entrada de revisão do sistema na tabela tblSystemRevision é incrementada após cada liberação do bloqueio.</span><span class="sxs-lookup"><span data-stu-id="f263f-181">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f263f-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-183">Contém a entrada de número de revisão usada (juntamente com a tabela tblAdminLock) para obter consistência entre vários servidores.</span><span class="sxs-lookup"><span data-stu-id="f263f-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f263f-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-185">Contém conexões ponto-a-ponto atuais entre serviços de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f263f-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f263f-186"><a href="lync-server-2013-tblconfig.md">tblConfig no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f263f-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f263f-187">Contém a configuração sem suporte do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f263f-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

