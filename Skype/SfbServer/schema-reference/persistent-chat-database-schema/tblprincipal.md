---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal contém todas as entidades, incluindo usuários, pastas e grupos.
ms.openlocfilehash: 5a0b6535ace344951b75f7c5c9488f56a18564ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295360"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal contém todas as entidades, incluindo usuários, pastas e grupos.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|multiimprimir  <br/> |int, não nulo  <br/> |ID da entidade de segurança.  <br/> |
|prinGuid  <br/> |GUID, não nulo  <br/> |GUID principal. Isso é amplamente usado como uma chave primária alternativa porque o significado é cruzado para o espaço dos serviços de domínio Active Directory. (O GUID de uma entidade do cache é igual à GUID do objeto do Active Directory correspondente.)  <br/> |
|prinUri  <br/> |nvarchar (256), NOT NULL  <br/> |URI principal. O esquema SIP é usado para os usuários, e o ma-GRP é usado para praticamente tudo o mais.  <br/> |
|imprimir  <br/> |nvarchar (256)  <br/> |Nome comum. Usado apenas por tipos de usuário.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nome para exibição. Usado apenas por tipos de usuário.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nome da empresa. Usado apenas por tipos de usuário.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Email. Usado apenas por tipos de usuário.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nome do domínio do objeto do Active Directory que a entidade de segurança é uma versão em cache de. Pode ser NULL para tipos que não sejam objetos do Active Directory (como usuários do sistema).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nome UPN do usuário. Usado apenas por tipos de usuário regulares.  <br/> |
|prinDisabled  <br/> |smallint, não nulo  <br/> | 0: a entidade de segurança está ativa. <br/>  1: o principal está desabilitado porque as funcionalidades SIP do usuário estão desabilitadas. <br/>  2: o principal é excluído porque o objeto do anúncio associado foi excluído. <br/> |
|prinTypeID  <br/> |smallint, não nulo  <br/> |Tipo de entidade de segurança (da tabela tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Núm  <br/> |Atribuição de pool do cliente Skype for Business para o principal.  <br/> |
|prinPolicyID  <br/> |Núm  <br/> |Valor da política do servidor de chat persistente para o usuário, se a política de tipo de marca estiver presente.  <br/> |
|prinAddedBy  <br/> |int  <br/> |ID da entidade de segurança do criador.  <br/> |
|prinAddedOn  <br/> |bigint, e não nulo  <br/> |Carimbo de data/hora para a hora da criação.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID da entidade de segurança que atualizou pela última vez.  <br/> |
|prinUpdatedOn  <br/> |bigint, e não nulo  <br/> |Carimbo de data/hora para a última atualização.  <br/> |
|prinVerifiedOn  <br/> |DateTime, não nulo  <br/> |Data e hora da última atualização de sincronização do Active Directory para a entidade de segurança.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|multiimprimir  <br/> |Chave primária.  <br/> |
|prinTypeID  <br/> |Chave estrangeira com Lookup na tabela tblPrincipalType. ptypeID.  <br/> |
   

