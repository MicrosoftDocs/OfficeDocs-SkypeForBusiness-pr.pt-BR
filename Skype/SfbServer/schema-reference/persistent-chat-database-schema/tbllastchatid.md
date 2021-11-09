---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
ms.openlocfilehash: a69c8ee112d507359a5582464ce39b7cbae89f4c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838433"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, não nulo  <br/> |ID de nó (apenas para tipo de sala de chat).  <br/> |
|lastChatID  <br/> |bigint, não nulo  <br/> |Último ID de chat usado.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Chave primária (apenas o nodeID é suficiente para o processamento).  <br/> |
|nodeID  <br/> |Chave estrangeira com pesquisa na tabela tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>Confira também

[tblChat](tblchat.md)
