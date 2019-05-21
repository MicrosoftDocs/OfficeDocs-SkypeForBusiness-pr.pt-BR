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
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295395"
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
