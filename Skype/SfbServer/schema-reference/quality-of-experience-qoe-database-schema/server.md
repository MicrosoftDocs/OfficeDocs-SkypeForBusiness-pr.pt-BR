---
title: Tabela de servidor
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: c061176c7a3dbb30fbbe696241fccd54db8dc9b2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834919"
---
# <a name="server-table"></a>Tabela de servidor
 
A tabela Server é uma tabela de suporte. Cada registro representa um servidor. 
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o servidor.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |Cadeia de caracteres de endereço MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Foreign  <br/> |1: Servidor de Mediação  <br/> 2: Servidor de Conferência A/V16394: Serviço de Borda A/V32769: Gateway  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Pool ao que o servidor pertence. Aplicável apenas ao Servidor de Conferência A/V.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Apenas para uso interno.  <br/> |
   

