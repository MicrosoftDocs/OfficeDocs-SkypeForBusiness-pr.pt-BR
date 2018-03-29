---
title: tblScopePrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal inclui os escopos atribuídos a nós.
ms.openlocfilehash: ba2927598cdff07368cb017866ec41bfa7540f48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal inclui os escopos atribuídos a nós.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, não nulo  <br/> |ID do nó de escopo se aplica.  <br/> |
|scopePrinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|scopeIsDenied  <br/> |bit, não nulo  <br/> |True se o tipo de escopo for negar; FALSO se for permitir.  <br/> |
|scopeUpdatedBy  <br/> |int, não nulo  <br/> |ID da entidade que atualizada pela última vez essa entrada.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Chave primária.  <br/> |
|scopeNodeID  <br/> |Chave estrangeira com pesquisa na tabela Tblnode.  <br/> |
|scopePrinID  <br/> |Chave estrangeira com pesquisa na tabela Tblprincipal.  <br/> |
   

