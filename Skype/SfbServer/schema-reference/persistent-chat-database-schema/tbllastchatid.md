---
title: tblLastChatId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, não nulo  <br/> |ID do nó (somente tipo sala de chat).  <br/> |
|lastChatID  <br/> |bigint, não nulo  <br/> |Último ID de chat usado.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Chave primária (apenas o nodeID é suficiente para o processamento).  <br/> |
|nodeID  <br/> |Chave estrangeira com pesquisa na tabela Tblnode.  <br/> |
   
## <a name="see-also"></a>Consulte também

#### 

[tblChat](tblchat.md)

