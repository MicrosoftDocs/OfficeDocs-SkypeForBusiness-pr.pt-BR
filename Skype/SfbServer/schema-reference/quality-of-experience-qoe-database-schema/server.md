---
title: Tabela Server
ms.reviewer: ''
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
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874305"
---
# <a name="server-table"></a>Tabela Server
 
A tabela de servidor é uma tabela de suporte. Cada registro representa um servidor. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o servidor.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |índice  <br/> |Cadeia de caracteres de endereço MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Externa  <br/> |1: servidor de mediação  <br/> 2: A / V Conferencing Server16394: uma borda a / V v32769: Gateway  <br/> |
|**Nome_conjunto** <br/> |nvarchar(512)  <br/> ||Pool que ao qual o servidor pertence. Só se aplica A / V Conferencing Server.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Somente para uso interno.  <br/> |
   

