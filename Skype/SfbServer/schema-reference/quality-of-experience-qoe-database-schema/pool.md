---
title: Tabela Pool
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela de Pool é uma tabela de suporte que armazena informações sobre os vários pools de Front-End. Cada registro na tabela representa um pool.
ms.openlocfilehash: ae8695316bdea6ba858bf9a4d334dc6075b99d50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874015"
---
# <a name="pool-table"></a>Tabela Pool
 
A tabela de Pool é uma tabela de suporte que armazena informações sobre os vários pools de Front-End. Cada registro na tabela representa um pool.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este pool.  <br/> |
|**Nome_conjunto** <br/> |nvarchar(256)  <br/> |Exclusivo  <br/> |FQDN do pool.  <br/> |
   

