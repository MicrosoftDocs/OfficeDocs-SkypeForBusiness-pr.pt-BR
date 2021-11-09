---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal contém todas as entidades, incluindo usuários, pastas e grupos.
ms.openlocfilehash: 91ac55a7d77c4225788a0fd1cb35b3fbbcf5e046
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846134"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal contém todas as entidades, incluindo usuários, pastas e grupos.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|prinGuid  <br/> |GUID, não nulo  <br/> |GUID da entidade. Isso é amplamente usado como uma chave primária alternativa porque seu significado se cruza para o espaço serviços de domínio do Active Directory. (O GUID de uma entidade em cache é igual ao GUID de objeto correspondente no Active Directory).  <br/> |
|prinUri  <br/> |nvarchar (256), não nulo  <br/> |URI de entidade. O esquema do SIP é usado para usuários e o ma-grp é usado para quase tudo.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nome comum. Usado apenas por tipos de usuário.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nome de exibição. Usado somente pelos tipos de usuário.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nome da empresa. Usado somente pelos tipos de usuário.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Email. Usado apenas pelos tipos de usuários.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nome de domínio do objeto do Active Directory do qual a entidade é uma versão em cache. Pode ser nulo para tipos que não são objetos do Active Directory (como os usuários do sistema).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nome principal do usuário (UPN). Usado somente pelos tipos de usuário regular.  <br/> |
|prinDisabled  <br/> |smallint, não nulo  <br/> | 0: a entidade está ativa. <br/>  1: Principal está desabilitado porque os recursos SIP do usuário estão desabilitados. <br/>  2: a entidade é excluída porque o objeto associado do AD foi excluído. <br/> |
|prinTypeID  <br/> |smallint, não nulo  <br/> |Tipo de entidade (da tabela tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype for Business pool de clientes para a entidade principal.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Valor da política do Servidor de Chat Persistente para o usuário, se a política de tipo de marca estiver presente.  <br/> |
|prinAddedBy  <br/> |int  <br/> |ID da entidade do criador.  <br/> |
|prinAddedOn  <br/> |bigint, não nulo  <br/> |Carimbo de data/hora para a hora da criação.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID da entidade que atualizou esta entrada pela última vez.  <br/> |
|prinUpdatedOn  <br/> |bigint, não nulo  <br/> |Carimbo de data/hora da última atualização.  <br/> |
|prinVerifiedOn  <br/> |datetime, não nulo  <br/> |Data e hora da última atualização de Sincronização do Active Directory para a entidade.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|prinID  <br/> |Chave primária.  <br/> |
|prinTypeID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipalType.ptypeID.  <br/> |
   

