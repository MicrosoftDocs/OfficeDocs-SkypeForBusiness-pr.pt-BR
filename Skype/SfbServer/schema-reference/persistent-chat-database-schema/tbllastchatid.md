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
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505082"
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

[tblChat](tblchat.md)