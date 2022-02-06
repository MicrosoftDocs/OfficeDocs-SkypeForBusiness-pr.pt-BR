---
title: Tabela de servidor
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: A tabela Server é uma tabela de suporte. Cada registro representa um servidor.
---

# <a name="server-table"></a>Tabela de servidor
 
A tabela Server é uma tabela de suporte. Cada registro representa um servidor. 
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o servidor.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |Cadeia de caracteres de endereço MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Foreign  <br/> |1: Servidor de Mediação  <br/> 2: Servidor de Conferência A/V16394: Serviço de Borda A/V32769: Gateway  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Pool ao que o servidor pertence. Aplicável apenas ao Servidor de Conferência A/V.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Apenas para uso interno.  <br/> |
   

