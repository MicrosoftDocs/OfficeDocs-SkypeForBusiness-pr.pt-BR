---
title: 'Lync Server 2013: lista de tabelas de servidor de chat persistente'
description: 'Lync Server 2013: lista de tabelas de servidor de chat persistente.'
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
ms.openlocfilehash: 838e6d8f83b137923075851b29df4c602a487391
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550047"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="ac784-103">Lista de tabelas do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac784-103">List of Persistent Chat Server tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac784-104">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ac784-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ac784-105">O esquema do banco de dados de chat persistente consiste nas seguintes tabelas.</span><span class="sxs-lookup"><span data-stu-id="ac784-105">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="ac784-106">Sincronização do Active Directory</span><span class="sxs-lookup"><span data-stu-id="ac784-106">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac784-107">Tabela</span><span class="sxs-lookup"><span data-stu-id="ac784-107">Table</span></span></th>
<th><span data-ttu-id="ac784-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac784-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac784-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-110">Contém cookies de sincronização LDAP.</span><span class="sxs-lookup"><span data-stu-id="ac784-110">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="ac784-111">Cada linha corresponde a um domínio de serviços de domínio do Active Directory que o servidor de chat persistente está monitorando ativamente as alterações.</span><span class="sxs-lookup"><span data-stu-id="ac784-111">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="ac784-112">(Apenas os domínios do Active Directory que são relevantes para o servidor de chat persistente são representados nesta tabela.)</span><span class="sxs-lookup"><span data-stu-id="ac784-112">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-114">Contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processados pelas etapas de sincronização posteriores do Active Directory e é uma das tabelas temporárias (junto com a tabela tblADUpdates) que é usada na primeira etapa da sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ac784-114">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="ac784-115">As alterações de associação são armazenadas, processadas ou ambos, somente para grupos listados na tabela tblPrincipal ou que já possuem membros listados.</span><span class="sxs-lookup"><span data-stu-id="ac784-115">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac784-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-117">Contém alterações nos serviços de domínio do Active Directory que ainda não foram processados pelas etapas de sincronização posteriores do Active Directory e é uma das tabelas temporárias (junto com a tabela tblPrincipalMemberDifference) que é usada na primeira etapa da sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ac784-117">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="ac784-118">As alterações no Active Directory são armazenadas, processadas ou ambas somente para entidades de segurança que já estão listadas na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="ac784-118">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-120">Contém associações de entidade.</span><span class="sxs-lookup"><span data-stu-id="ac784-120">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac784-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-122">Contém as entidades de segurança que precisam ser atualizadas do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ac784-122">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-124">Contém afiliações que não podem ser atualizadas por algum motivo, geralmente devido a erros de acesso ao Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ac784-124">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="ac784-p102">Esta tabela é apenas para fins informativos. Seu conteúdo não é usado.</span><span class="sxs-lookup"><span data-stu-id="ac784-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="ac784-127">As entidades com afiliações que não podem ser atualizadas corretamente são mantidas na tabela tblPrincipalMeta e têm outra chance de serem atualizadas.</span><span class="sxs-lookup"><span data-stu-id="ac784-127">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="ac784-128">Entidades, afiliações, nós, escopos e funções</span><span class="sxs-lookup"><span data-stu-id="ac784-128">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac784-129">Tabela</span><span class="sxs-lookup"><span data-stu-id="ac784-129">Table</span></span></th>
<th><span data-ttu-id="ac784-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac784-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac784-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-p103">Contém tipos de entidades para categorizar o que está na tabela tblPrincipal. Esta tabela é estática. É configurada durante a criação do banco de dados e não muda.</span><span class="sxs-lookup"><span data-stu-id="ac784-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-136">Contém todas as entidades (usuários, pastas, grupos e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="ac784-136">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="ac784-137">O servidor de chat persistente trata isso como uma lista de heterogêneos simples.</span><span class="sxs-lookup"><span data-stu-id="ac784-137">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="ac784-138">Várias colunas são baseadas no tipo de cada entidade.</span><span class="sxs-lookup"><span data-stu-id="ac784-138">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="ac784-139">A maioria dessas entidades são cópias em cache de objetos armazenados no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ac784-139">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="ac784-140">A criação da cópia em cache na tabela principal desses objetos do Active Directory é chamada de <em>provisionamento</em>.</span><span class="sxs-lookup"><span data-stu-id="ac784-140">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="ac784-141">Algumas entidades são criadas mais agressivamente do que outras, e alguns objetos do Active Directory são ignorados completamente.</span><span class="sxs-lookup"><span data-stu-id="ac784-141">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac784-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-143">Contém as afiliações principais que descrevem associações nos grupos de segurança do Active Directory, contêineres do Active Directory e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="ac784-143">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-144"><a href="lync-server-2013-tblnode.md">tblNode no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-144"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-145">Contém o nó de categoria, conforme gerenciado no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ac784-145">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac784-146"><a href="lync-server-2013-tblroletype.md">tblRoleType no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-146"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-147">Contém tipos de função e seus conjuntos de permissões associadas.</span><span class="sxs-lookup"><span data-stu-id="ac784-147">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="ac784-148">A tabela de pesquisa é estática.</span><span class="sxs-lookup"><span data-stu-id="ac784-148">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-150">Contém escopos atribuídos aos nós.</span><span class="sxs-lookup"><span data-stu-id="ac784-150">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac784-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-152">Contêm funções atribuídas aos nós.</span><span class="sxs-lookup"><span data-stu-id="ac784-152">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-154">Contém os suplementos registrados que podem ser associados aos nós.</span><span class="sxs-lookup"><span data-stu-id="ac784-154">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac784-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-156">Contém apenas os atributos de &quot; visibilidade &quot; e &quot; comportamento codificados &quot; usados na tabela tblNode.</span><span class="sxs-lookup"><span data-stu-id="ac784-156">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-158">Contém os valores dos atributos de comportamento de visibilidade codificada &quot; "e" &quot; que são usados na tabela tblNode.</span><span class="sxs-lookup"><span data-stu-id="ac784-158">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="ac784-159">Convites, bate-papos e outro suporte ao cliente</span><span class="sxs-lookup"><span data-stu-id="ac784-159">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac784-160">Tabela</span><span class="sxs-lookup"><span data-stu-id="ac784-160">Table</span></span></th>
<th><span data-ttu-id="ac784-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac784-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac784-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-163">Contém convites para todos os usuários configurados no sistema para todos os nós com Convidar automaticamente habilitado.</span><span class="sxs-lookup"><span data-stu-id="ac784-163">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-164"><a href="lync-server-2013-tblchat.md">tblChat no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-164"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-165">Contém todas as mensagens de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="ac784-165">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac784-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-167">Contém a última ID de convite gerada (e usada na tabela tblPrincipalInvites) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="ac784-167">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-169">Contém a última ID de bate-papo gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="ac784-169">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac784-170"><a href="lync-server-2013-tblpreference.md">tblPreference no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-170"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-171">Contém preferências do cliente usuário (usado apenas por clientes herdados).</span><span class="sxs-lookup"><span data-stu-id="ac784-171">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-173">Contém tokens temporários para fins de transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ac784-173">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="ac784-174">Cada vez que um arquivo é carregado ou baixado, o serviço de chat persistente gera um token que o cliente usa para acessar o repositório de arquivos do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="ac784-174">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="ac784-175">Suporte a servidor</span><span class="sxs-lookup"><span data-stu-id="ac784-175">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac784-176">Tabela</span><span class="sxs-lookup"><span data-stu-id="ac784-176">Table</span></span></th>
<th><span data-ttu-id="ac784-177">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac784-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac784-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-179">Contém os servidores ativos no pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ac784-179">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-p108">Contém o bloqueio do administrador para executar alguns comandos do administrador. A entrada de revisão do sistema na tabela tblSystemRevision é incrementada após cada liberação do bloqueio.</span><span class="sxs-lookup"><span data-stu-id="ac784-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac784-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-184">Contém a entrada do número de revisão usada (juntamente com a tabela tblAdminLock) para obter consistência em vários clientes.</span><span class="sxs-lookup"><span data-stu-id="ac784-184">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac784-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-186">Contém as conexões ponto a ponto atuais entre serviços de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ac784-186">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac784-187"><a href="lync-server-2013-tblconfig.md">tblConfig no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac784-187"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac784-188">Contém a configuração não suportada do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ac784-188">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

