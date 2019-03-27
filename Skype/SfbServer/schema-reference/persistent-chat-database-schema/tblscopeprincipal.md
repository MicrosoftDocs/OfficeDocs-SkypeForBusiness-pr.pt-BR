---
title: tblScopePrincipal
ms.reviewer: ''
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
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885621"
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
   

