---
title: Tabela ConferenceMessageCount Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro desta tabela representa um usuário em uma conferência de mensagem Instantânea e inclui o número de mensagens enviadas pelo usuário. Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.
ms.openlocfilehash: 6b9dfcf0743c03e69726bb501cc7a4a961bf5df8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabela ConferenceMessageCount Skype para Business Server 2015
 
Cada registro desta tabela representa um usuário em uma conferência de mensagem Instantânea e inclui o número de mensagens enviadas pelo usuário. Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Hora da ocorrência de conferência. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma instância de conferência. Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação para identificar a instância de conferência. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência. Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**UserId** <br/> |int  <br/> |Externa  <br/> |Número exclusivo que identifica este usuário, referenciado de [Users table](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |O número de mensagens enviadas por esse usuário durante esta conferência.  <br/> |
   

