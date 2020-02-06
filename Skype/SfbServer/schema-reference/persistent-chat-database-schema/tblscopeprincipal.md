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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contém escopos atribuídos a nós.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812439"
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
   

