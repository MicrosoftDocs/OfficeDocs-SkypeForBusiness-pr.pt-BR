---
title: tblPrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal contém todas as entidades, incluindo usuários, pastas e grupos.
ms.openlocfilehash: adeb4e52ea9bd276de09d90945443431fb3be94f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880970"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal contém todas as entidades, incluindo usuários, pastas e grupos.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|prinGuid  <br/> |GUID, não nulo  <br/> |GUID principal. Isso é amplamente usado como uma chave primária alternativa porque seu significado entrará no espaço de serviços de domínio Active Directory. (O GUID de uma entidade de segurança em cache é igual ao objeto do Active Directory correspondente GUID.)  <br/> |
|prinUri  <br/> |nvarchar (256), não nulo  <br/> |URI de entidade. O esquema do SIP é usado para usuários e ma-grp é usado para praticamente todo o resto.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nome comum. Usado somente pelo usuário digita.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nome para exibição. Usado somente pelo usuário digita.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nome da empresa. Usado somente pelo usuário digita.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Email. Usado somente pelo usuário digita.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nome de domínio do que a entidade é uma versão em cache de objeto do Active Directory. Pode ser Null para tipos que não são objetos do Active Directory (por exemplo, os usuários do sistema).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nome principal do usuário do usuário (UPN). Usado somente por tipos de usuário regular.  <br/> |
|prinDisabled  <br/> |smallint, não nulo  <br/> | 0: entidade está ativa. <br/>  1: entidade é desabilitada porque os recursos SIP do usuário estão desabilitados. <br/>  2: entidade é excluída porque o objeto associado do AD foi excluído. <br/> |
|prinTypeID  <br/> |smallint, não nulo  <br/> |Tipo de entidade (da tabela tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype para atribuição de pool de cliente de negócios para a entidade.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Valor de diretiva de servidor de Chat persistente para o usuário, se a política de tipo de marca estiver presente.  <br/> |
|prinAddedBy  <br/> |int  <br/> |ID da entidade do criador.  <br/> |
|prinAddedOn  <br/> |bigint, não nulo  <br/> |Carimbo de hora para a hora da criação.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID da entidade que a última atualização isso.  <br/> |
|prinUpdatedOn  <br/> |bigint, não nulo  <br/> |Carimbo de hora da última atualização.  <br/> |
|prinVerifiedOn  <br/> |DateTime, não nulo  <br/> |Data e hora da sincronização do Active Directory última atualização para a entidade.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|prinID  <br/> |Chave primária.  <br/> |
|prinTypeID  <br/> |Chave estrangeira com pesquisa na tabela Tblprincipaltype.  <br/> |
   

