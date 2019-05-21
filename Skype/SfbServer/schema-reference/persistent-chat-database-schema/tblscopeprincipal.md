---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contém escopos atribuídos a nós.
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295192"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contém escopos atribuídos a nós.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, não nulo  <br/> |ID do nó ao qual o escopo se aplica.  <br/> |
|scopePrinID  <br/> |int, não nulo  <br/> |ID da entidade de segurança.  <br/> |
|scopeIsDenied  <br/> |bit, e não nulo  <br/> |Verdadeiro se o tipo de escopo for negar; Falso se permitir.  <br/> |
|scopeUpdatedBy  <br/> |int, não nulo  <br/> |ID da entidade de segurança que atualizou pela última vez esta entrada.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Chave primária.  <br/> |
|scopeNodeID  <br/> |Chave estrangeira com Lookup na tabela tblNode. NodeId.  <br/> |
|scopePrinID  <br/> |Chave estrangeira com Lookup na tabela tblPrincipal. retoid.  <br/> |
   

