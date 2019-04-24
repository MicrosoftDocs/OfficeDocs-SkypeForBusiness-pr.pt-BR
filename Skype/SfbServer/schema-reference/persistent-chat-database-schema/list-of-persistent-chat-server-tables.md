---
title: Tabelas de lista de Servidores de Chat Persistente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: O esquema de banco de dados de Chat persistente consiste as tabelas a seguir.
ms.openlocfilehash: e2ce24bb37c3ea4eaee0986f0243033ab4a8a18a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213218"
---
# <a name="list-of-persistent-chat-server-tables"></a>Tabelas de lista de Servidores de Chat Persistente
 
O esquema de banco de dados de Chat persistente consiste as tabelas a seguir.
  
## <a name="active-directory-sync"></a>Sincronização do Active Directory

|**Tabela**|**Descrição**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contém os cookies atuais de sincronização de Lightweight Directory Access Protocol (LDAP). Cada linha corresponde a um domínio do Active Directory Domain Services que o servidor de Chat persistente está monitorando ativamente para que as alterações. (Apenas aos domínios do Active Directory que são relevantes para o servidor de Chat persistente são representados nesta tabela).  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contém as alterações de associação do grupo (tanto adicionadas e removidas membros) que ainda não foram processadas pelas etapas posteriores de sincronização do Active Directory e é uma das tabelas (juntamente com a tabela tblADUpdates tabela) temporárias que é usado na primeira etapa da sincronização do Active Directory.  <br/> As alterações de associação são armazenadas, processadas ou ambos, somente para grupos listados na tabela tblPrincipal ou que já possuem membros listados.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contém alterações aos serviços de domínio Active Directory que ainda não foram processadas pelas etapas posteriores de sincronização do Active Directory e é uma das tabelas (juntamente com a tabela Principalmemberdifference) temporárias que é usado na primeira etapa do Active Directory Sincronizar.  <br/> Alterações ao Active Directory são armazenadas, processadas ou ambos somente para entidades já listadas na tabela tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contém associações de entidade.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contém as entidades que precisam ser atualizadas do Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contém afiliações que não podem ser atualizadas por algum motivo, geralmente devido a erros de acesso do Active Directory.  <br/> Esta tabela é apenas informativo. Seu conteúdo não é usado.  <br/> As entidades com afiliações que não podem ser atualizadas corretamente são mantidas na tabela tblPrincipalMeta e têm outra chance de serem atualizadas.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entidades, afiliações, nós, escopos e funções

|**Tabela**|**Descrição**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contém os tipos principais para categorizar o que está na tabela tblPrincipal. Esta tabela é estática. Ele está configurado durante a criação do banco de dados e não é alterado.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contém todas as entidades (usuários, pastas, grupos e assim por diante). Servidor de Chat persistente lida com isso como uma lista de plano heterogênea. Várias colunas baseiam-se ao tipo de cada entidade.  <br/> A maioria dessas entidades são cópias em cache de objetos armazenados no Active Directory. Criando a cópia em cache no Principal tabela desses objetos do Active Directory é conhecida como provisionamento.  <br/> Algumas entidades são criadas mais agressivamente do que outras e alguns objetos do Active Directory são ignorados.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contém as principais afiliações que descrevem as associações em grupos de segurança do Active Directory, contêineres do Active Directory e assim por diante.  <br/> |
|[tblNode](tblnode.md) <br/> |Contém o nó de categoria, como gerenciado no painel de controle.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contém os tipos de funções e suas permissões associados conjuntos. Esta tabela de pesquisa é estática.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contém escopos atribuídos a nós.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contém funções atribuídas a nós.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contém os Add-ins registrados que podem ser associados a nós.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contém apenas os atributos "Visibility" e "Behavior" codificados usados na tabela tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contém os valores dos atributos "Visibility" e "Behavior" codificados usados na tabela tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Convites, bate-papos e outro suporte ao cliente

|**Tabela**|**Descrição**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contém convites para todos os usuários provisionados no sistema de todos os nós com convidar automaticamente habilitado.  <br/> |
|[tblChat](tblchat.md) <br/> |Contém todas as mensagens de chat.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contém a última ID de convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contém preferências do cliente usuário (usadas apenas por clientes herdados).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Inclui tokens temporários para fins de transferência de arquivo. Sempre que um arquivo é carregado ou baixado, o serviço de Chat persistente gera um token que o cliente usa para acessar o repositório de arquivos do serviço Web.  <br/> |
   
## <a name="server-support"></a>Suporte a servidor

|**Tabela**|**Descrição**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contém os servidores ativos no pool do servidor de Chat persistente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contém o bloqueio do administrador para executar alguns comandos de administrador. A entrada de revisão do sistema na tabela tblSystemRevision é incrementada após cada versão do bloqueio.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contém a entrada de número de revisão usada (juntamente com a tabela tblAdminLock) para obter consistência em vários servidores.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contém conexões ponto-a-ponto atuais entre os serviços de Chat persistente.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contém a configuração de servidor de Chat persistente sem suporte.  <br/> |
   

