---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal inclui os escopos atribuídos a nós.
ms.openlocfilehash: f682c8a2235ef30cda365bc5950cbfb123840595
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924924"
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
   

