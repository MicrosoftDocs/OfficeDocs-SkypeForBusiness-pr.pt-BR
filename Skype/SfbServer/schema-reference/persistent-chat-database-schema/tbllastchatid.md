---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814579"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|NodeId  <br/> |int, não nulo  <br/> |ID do nó (somente sala de chat-tipo).  <br/> |
|lastChatID  <br/> |bigint, e não nulo  <br/> |ID do Chat usado pela última vez.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<NodeId, lastChatID\>  <br/> |Chave primária (apenas NodeId é suficiente para processamento).  <br/> |
|NodeId  <br/> |Chave estrangeira com Lookup na tabela tblNode. NodeId.  <br/> |
   
## <a name="see-also"></a>Confira também

[tblChat](tblchat.md)
