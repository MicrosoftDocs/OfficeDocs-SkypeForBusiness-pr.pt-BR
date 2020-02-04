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

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Tabelas de lista de Servidores de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

O esquema de banco de dados de chat persistente consiste nas tabelas a seguir.

<div>

## <a name="active-directory-sync"></a>Sincronização do Active Directory


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie no Lync Server 2013</a></p></td>
<td><p>Contém os atuais cookies de sincronização de LDAP (Lightweight Directory Access Protocol). Cada linha corresponde a um domínio de serviços de domínio do Active Directory que o servidor de chat persistente está monitorando ativamente para alterações. (Somente os domínios do Active Directory que são relevantes para o servidor de chat persistente são representados nesta tabela).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference no Lync Server 2013</a></p></td>
<td><p>Contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory e é uma das tabelas temporárias (juntamente com a tabela tblADUpdates) que é usada na primeira etapa da sincronização do Active Directory.</p>
<p>As alterações de associação são armazenadas, processadas ou ambas, apenas para grupos listados na tabela tblPrincipal ou que já têm Membros listados ali.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates no Lync Server 2013</a></p></td>
<td><p>Contém alterações nos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory e é uma das tabelas temporárias (juntamente com a tabela tblPrincipalMemberDifference) que é usada na primeira etapa do Active Directory Sincronizar.</p>
<p>As alterações no Active Directory são armazenadas, processadas ou ambas somente para entidades que já estão listadas na tabela tblPrincipal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers no Lync Server 2013</a></p></td>
<td><p>Contém associações de entidades de segurança.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta no Lync Server 2013</a></p></td>
<td><p>Contém as entidades de segurança que devem ser atualizadas a partir do Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations no Lync Server 2013</a></p></td>
<td><p>Contém afiliações que não podem ser atualizadas por algum motivo, geralmente devido a erros de acesso ao Active Directory.</p>
<p>Esta tabela é apenas para fins informativos. Seu conteúdo não é usado.</p>
<p>As entidades de segurança com afiliações que não foram atualizadas corretamente são mantidas na tabela tblPrincipalMeta e recebem outra oportunidade de serem atualizadas.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entidades, afiliações, nós, escopos e funções


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType no Lync Server 2013</a></p></td>
<td><p>Contém tipos de principais para categorizar o que está na tabela tblPrincipal. Esta tabela é estática. Ele é configurado durante a criação do banco de dados e não é alterado.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal no Lync Server 2013</a></p></td>
<td><p>Contém todas as entidades (usuários, pastas, grupos e assim por diante). O servidor de chat persistente manipula isso como uma lista heterogênea e uniforme. Várias colunas baseiam-se no tipo de cada entidade.</p>
<p>A maioria dessas entidades são cópias em cache de objetos armazenados no Active Directory. A criação da cópia em cache na tabela principal desses objetos do Active Directory é chamada de <em>provisionamento</em>.</p>
<p>Algumas entidades de segurança são criadas de forma mais agressiva do que outras, e alguns objetos do Active Directory são ignorados completamente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations no Lync Server 2013</a></p></td>
<td><p>Contém associações de entidades de segurança que descrevem associações nos grupos de segurança do Active Directory, contêineres do Active Directory e assim por diante.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode no Lync Server 2013</a></p></td>
<td><p>Contém o nó Category, conforme gerenciado no painel de controle do Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType no Lync Server 2013</a></p></td>
<td><p>Contém tipos de função e seus conjuntos de permissões associados. Esta tabela de pesquisa é estática.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal no Lync Server 2013</a></p></td>
<td><p>Contém escopos atribuídos a nós.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole no Lync Server 2013</a></p></td>
<td><p>Contém funções atribuídas a nós.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList no Lync Server 2013</a></p></td>
<td><p>Contém os suplementos registrados que podem ser associados a nós.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute no Lync Server 2013</a></p></td>
<td><p>Contém somente os atributos de &quot;visibilidade&quot; e &quot;comportamento&quot; inseridos que são usados na tabela tblNode.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue no Lync Server 2013</a></p></td>
<td><p>Contém os valores dos atributos de comportamento &quot;&quot; de visibilidade codificada "e" que são usados na tabela tblNode.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>Convites, chats e outros suporte ao cliente


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites no Lync Server 2013</a></p></td>
<td><p>Contém convites para todos os usuários provisionados no sistema para todos os nós com convite automático habilitado.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat no Lync Server 2013</a></p></td>
<td><p>Contém todas as mensagens de chat.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId no Lync Server 2013</a></p></td>
<td><p>Contém a ID do último convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId no Lync Server 2013</a></p></td>
<td><p>Contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference no Lync Server 2013</a></p></td>
<td><p>Contém as preferências do cliente do usuário (usadas somente por clientes herdados).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken no Lync Server 2013</a></p></td>
<td><p>Contém tokens temporários para fins de transferência de arquivo. Cada vez que um arquivo é carregado ou baixado, o serviço de chat persistente gera um token que o cliente usa para acessar o repositório de arquivos do serviço Web.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>Suporte a servidor


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity no Lync Server 2013</a></p></td>
<td><p>Contém os servidores ativos no pool do servidor de chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock no Lync Server 2013</a></p></td>
<td><p>Contém o bloqueio do administrador para executar alguns comandos de administrador. A entrada de revisão do sistema na tabela tblSystemRevision é incrementada após cada liberação do bloqueio.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision no Lync Server 2013</a></p></td>
<td><p>Contém a entrada de número de revisão usada (juntamente com a tabela tblAdminLock) para obter consistência entre vários servidores.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers no Lync Server 2013</a></p></td>
<td><p>Contém conexões ponto-a-ponto atuais entre serviços de chat persistente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig no Lync Server 2013</a></p></td>
<td><p>Contém a configuração sem suporte do servidor de chat persistente.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

