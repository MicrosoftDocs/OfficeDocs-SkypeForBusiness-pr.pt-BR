---
title: Tabela Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: A tabela de servidor é uma tabela de suporte. Cada registro representa um servidor.
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a>Tabela Server
 
A tabela de servidor é uma tabela de suporte. Cada registro representa um servidor. 
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o servidor.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |índice  <br/> |Cadeia de caracteres de endereço MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Externa  <br/> |1: servidor de mediação  <br/> 2: A / V Conferencing Server16394: uma borda a / V v32769: Gateway  <br/> |
|**Nome_conjunto** <br/> |nvarchar(512)  <br/> ||Pool que ao qual o servidor pertence. Só se aplica A / V Conferencing Server.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Somente para uso interno.  <br/> |
   

