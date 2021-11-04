---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal inclui os escopos atribuídos aos nós.
ms.openlocfilehash: 4f2bcb7734badde8f734c30f074ba6dda82cc7eb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745707"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal inclui os escopos atribuídos aos nós.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, not null  <br/> |Identificação do nó ao qual o escopo se aplica.  <br/> |
|scopePrinID  <br/> |int, not null  <br/> |ID da Entidade de Segurança.  <br/> |
|scopeIsDenied  <br/> |bit, não vazio  <br/> |Verdadeiro se o tipo de escopo for Negar; falso se for Permitir.  <br/> |
|scopeUpdatedBy  <br/> |int, not null  <br/> |ID da entidade de segurança da última atualização dessa entrada.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Chave primária.  <br/> |
|scopeNodeID  <br/> |Chave estrangeira com pesquisa na tabela tblNode.nodeID.  <br/> |
|scopePrinID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.  <br/> |
   

