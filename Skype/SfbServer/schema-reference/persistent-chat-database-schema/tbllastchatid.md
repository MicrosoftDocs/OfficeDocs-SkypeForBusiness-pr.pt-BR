---
title: tblLastChatId
ms.reviewer: ''
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
ms.openlocfilehash: 3208ada77643957295f9894cb58187c2b4bc7493
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212562"
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
   
## <a name="see-also"></a>Confira também

[tblChat](tblchat.md)
