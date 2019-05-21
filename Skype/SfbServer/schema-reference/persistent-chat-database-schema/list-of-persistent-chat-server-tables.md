---
title: Tabelas de lista de Servidores de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: O esquema de banco de dados de chat persistente consiste nas tabelas a seguir.
ms.openlocfilehash: 6a6c0bc2c2cc2d5e5ba59f9f636ed9cea2189bed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295647"
---
# <a name="list-of-persistent-chat-server-tables"></a>Tabelas de lista de Servidores de Chat Persistente
 
O esquema de banco de dados de chat persistente consiste nas tabelas a seguir.
  
## <a name="active-directory-sync"></a>Sincronização do Active Directory

|**Tabela**|**Descrição**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contém os atuais cookies de sincronização de LDAP (Lightweight Directory Access Protocol). Cada linha corresponde a um domínio de serviços de domínio do Active Directory que o servidor de chat persistente está monitorando ativamente para alterações. (Somente os domínios do Active Directory que são relevantes para o servidor de chat persistente são representados nesta tabela).  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory e é uma das tabelas temporárias (juntamente com a tabela tblADUpdates) que é usada na primeira etapa da sincronização do Active Directory.  <br/> As alterações de associação são armazenadas, processadas ou ambas, apenas para grupos listados na tabela tblPrincipal ou que já têm Membros listados ali.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contém alterações nos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory e é uma das tabelas temporárias (juntamente com a tabela tblPrincipalMemberDifference) que é usada na primeira etapa do Active Directory Sincronizar.  <br/> As alterações no Active Directory são armazenadas, processadas ou ambas somente para entidades que já estão listadas na tabela tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contém associações de entidades de segurança.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contém as entidades de segurança que devem ser atualizadas a partir do Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contém afiliações que não podem ser atualizadas por algum motivo, geralmente devido a erros de acesso ao Active Directory.  <br/> Esta tabela é apenas para fins informativos. Seu conteúdo não é usado.  <br/> As entidades de segurança com afiliações que não foram atualizadas corretamente são mantidas na tabela tblPrincipalMeta e recebem outra oportunidade de serem atualizadas.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entidades, afiliações, nós, escopos e funções

|**Tabela**|**Descrição**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contém tipos de principais para categorizar o que está na tabela tblPrincipal. Esta tabela é estática. Ele é configurado durante a criação do banco de dados e não é alterado.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contém todas as entidades (usuários, pastas, grupos e assim por diante). O servidor de chat persistente manipula isso como uma lista heterogênea e uniforme. Várias colunas baseiam-se no tipo de cada entidade.  <br/> A maioria dessas entidades são cópias em cache de objetos armazenados no Active Directory. A criação da cópia em cache na tabela principal desses objetos do Active Directory é chamada de provisionamento.  <br/> Algumas entidades de segurança são criadas de forma mais agressiva do que outras, e alguns objetos do Active Directory são ignorados completamente.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contém associações de entidades de segurança que descrevem associações nos grupos de segurança do Active Directory, contêineres do Active Directory e assim por diante.  <br/> |
|[tblNode](tblnode.md) <br/> |Contém o nó de categoria, conforme gerenciado no painel de controle.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contém tipos de função e seus conjuntos de permissões associados. Esta tabela de pesquisa é estática.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contém escopos atribuídos a nós.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contém funções atribuídas a nós.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contém os suplementos registrados que podem ser associados a nós.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contém somente os atributos de "visibilidade" e "comportamento" codificados que são usados na tabela tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contém os valores dos atributos "Visibility" e "Behavior" codificados que são usados na tabela tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Convites, chats e outros suporte ao cliente

|**Tabela**|**Descrição**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contém convites para todos os usuários provisionados no sistema para todos os nós com convite automático habilitado.  <br/> |
|[tblChat](tblchat.md) <br/> |Contém todas as mensagens de chat.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contém a ID do último convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contém as preferências do cliente do usuário (usadas somente por clientes herdados).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contém tokens temporários para fins de transferência de arquivo. Cada vez que um arquivo é carregado ou baixado, o serviço de chat persistente gera um token que o cliente usa para acessar o repositório de arquivos do serviço Web.  <br/> |
   
## <a name="server-support"></a>Suporte a servidor

|**Tabela**|**Descrição**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contém os servidores ativos no pool do servidor de chat persistente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contém o bloqueio do administrador para executar alguns comandos de administrador. A entrada de revisão do sistema na tabela tblSystemRevision é incrementada após cada liberação do bloqueio.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contém a entrada de número de revisão usada (juntamente com a tabela tblAdminLock) para obter consistência entre vários servidores.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contém conexões ponto-a-ponto atuais entre serviços de chat persistente.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contém a configuração sem suporte do servidor de chat persistente.  <br/> |
   

