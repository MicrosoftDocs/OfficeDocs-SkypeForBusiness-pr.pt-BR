---
title: Tabela Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: A tabela de servidor é uma tabela de suporte. Cada registro representa um servidor.
ms.openlocfilehash: c0031e7181bb39895edadc40748f61626621f00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920128"
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
   

