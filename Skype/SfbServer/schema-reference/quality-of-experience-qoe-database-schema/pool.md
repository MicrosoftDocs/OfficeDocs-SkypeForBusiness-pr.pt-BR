---
title: Tabela Pool
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
ms.openlocfilehash: 8ce54d4b0a20fa405f34bb14b3eecb9ad395884e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="pool-table"></a>Tabela Pool
 
A tabela de Pool é uma tabela de suporte que armazena informações sobre os vários pools de Front-End. Cada registro na tabela representa um pool.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este pool.  <br/> |
|**Nome_conjunto** <br/> |nvarchar(256)  <br/> |Exclusivo  <br/> |FQDN do pool.  <br/> |
   

