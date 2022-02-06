---
title: Lista de tabelas de Servidores de Chat Persistente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: O esquema de banco de dados de Chat Persistente consiste nas tabelas a seguir.
---

# <a name="list-of-persistent-chat-server-tables"></a>Lista de tabelas de Servidores de Chat Persistente
 
O esquema de banco de dados de Chat Persistente consiste nas tabelas a seguir.
  
## <a name="active-directory-sync"></a>Sincronização do Active Directory

|**Table**|**Descrição**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contém cookies de sincronização LDAP. Cada linha corresponde a um domínio dos Serviços de Domínio do Active Directory que o Servidor de Chat Persistente está monitorando ativamente as alterações. (Somente os domínios do Active Directory relevantes para o Servidor de Chat Persistente são representados nesta tabela.)  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processadas pelas etapas posteriores de Sincronização do Active Directory e é uma das tabelas temporárias (juntamente com a tabela tblADUpdates) que é usada na primeira etapa da Sincronização do Active Directory.  <br/> As alterações de associação são armazenadas, processadas ou ambos, somente para grupos listados na tabela tblPrincipal ou que já possuem membros listados.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contém alterações nos Serviços de Domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de Sincronização do Active Directory e é uma das tabelas temporárias (juntamente com a tabela tblPrincipalMemberDifference) que é usada na primeira etapa da Sincronização do Active Directory.  <br/> As alterações no Active Directory são armazenadas, processadas ou ambas apenas para entidades que já estão listadas na tabela tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contém associações de entidade.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contém as entidades que devem ser atualizadas do Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contém afiliações que não puderam ser atualizadas por algum motivo, geralmente devido a erros de acesso do Active Directory.  <br/> Esta tabela é apenas para fins informativos. Seu conteúdo não é usado.  <br/> As entidades com afiliações que não podem ser atualizadas corretamente são mantidas na tabela tblPrincipalMeta e têm outra chance de serem atualizadas.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entidades, afiliações, nós, escopos e funções

|**Table**|**Descrição**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contém tipos de entidades para categorizar o que está na tabela tblPrincipal. Esta tabela é estática. É configurada durante a criação do banco de dados e não muda.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contém todas as entidades (usuários, pastas, grupos e assim por diante). O Servidor de Chat Persistente lida com isso como uma lista simples heterogênea. Várias colunas são baseadas no tipo de cada entidade.  <br/> A maioria dessas entidades são cópias armazenadas em cache de objetos armazenados no Active Directory. A criação da cópia em cache na tabela Principal desses objetos do Active Directory é chamada de provisionamento.  <br/> Algumas entidades são criadas de forma mais agressiva do que outras, e alguns objetos do Active Directory são ignorados completamente.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contém afiliações principais que descrevem associações em grupos de segurança do Active Directory, contêineres do Active Directory e assim por diante.  <br/> |
|[tblNode](tblnode.md) <br/> |Contém o nó categoria, conforme gerenciado no painel de controle.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contém tipos de função e seus conjuntos de permissões associadas. A tabela de pesquisa é estática.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contém escopos atribuídos aos nós.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contêm funções atribuídas aos nós.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contém os suplementos registrados que podem ser associados aos nós.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contém apenas os atributos de "Visibility" e "Behavior" codificados usados na tabela tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contém os valores dos atributos "Visibility" e "Behavior" de código que são usados na tabela tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Convites, bate-papos e outro suporte ao cliente

|**Table**|**Descrição**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contém convites para todos os usuários configurados no sistema para todos os nós com Convidar automaticamente habilitado.  <br/> |
|[tblChat](tblchat.md) <br/> |Contém todas as mensagens de bate-papo.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contém a última ID de convite gerada (e usada na tabela tblPrincipalInvites) para cada usuário.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contém a última ID de bate-papo gerada (e usada na tabela tblChat) para cada usuário.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contém preferências do cliente usuário (usado apenas por clientes herdados).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contém tokens temporários para fins de transferência de arquivo. Sempre que um arquivo é carregado ou baixado, o serviço de Chat Persistente gera um token que o cliente usa para acessar o armazenamento de arquivos do serviço Web.  <br/> |
   
## <a name="server-support"></a>Suporte a servidor

|**Table**|**Descrição**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contém os servidores ativos no pool do Servidor de Chat Persistente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contém o bloqueio do administrador para executar alguns comandos do administrador. A entrada de revisão do sistema na tabela tblSystemRevision é incrementada após cada liberação do bloqueio.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contém a entrada do número de revisão usada (juntamente com a tabela tblAdminLock) para obter consistência em vários clientes.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contém conexões ponto a ponto atuais entre os serviços de Chat Persistente.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contém a configuração sem suporte do Servidor de Chat Persistente.  <br/> |
   

