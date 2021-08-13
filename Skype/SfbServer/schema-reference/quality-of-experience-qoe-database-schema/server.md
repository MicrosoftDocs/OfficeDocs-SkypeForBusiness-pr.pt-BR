---
title: Tabela de servidor
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: A tabela Server é uma tabela de suporte. Cada registro representa um servidor.
ms.openlocfilehash: e43e245e62b1b40f318d1920ae93d82ae9e8bad0e28436f31d9cc2f0fe54bac1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341616"
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
   

