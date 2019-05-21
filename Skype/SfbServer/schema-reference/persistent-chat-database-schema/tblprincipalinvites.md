---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contém convites para todos os usuários provisionados para todos os nós com convite automático ativado.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295290"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contém convites para todos os usuários provisionados para todos os nós com convite automático ativado.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|multiimprimir  <br/> |int, não nulo  <br/> |ID da entidade de segurança.  <br/> |
|invID  <br/> |int, não nulo  <br/> |Número seqüencial exclusivo (por ID da entidade) gerado pela tabela tblLastInviteId.  <br/> |
|NodeId  <br/> |int, não nulo  <br/> |ID do nó (somente sala de chat).  <br/> |
|criar  <br/> |DateTime, não nulo  <br/> |Hora da criação.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<, NodeId\>  <br/> |Chave primária.  <br/> |
|multiimprimir  <br/> |Chave estrangeira com Lookup na tabela tblPrincipal. retoid.  <br/> |
|NodeId  <br/> |Chave estrangeira com Lookup na tabela tblNode. NodeId.  <br/> |
   

