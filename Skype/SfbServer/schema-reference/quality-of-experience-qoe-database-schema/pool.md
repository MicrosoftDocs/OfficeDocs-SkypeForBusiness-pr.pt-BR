---
title: Tabela pool
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
ms.localizationpriority: medium
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela Pool é uma tabela de suporte que armazena informações sobre os diversos pools de Front-Ends. Cada registro da tabela representa um pool.
ms.openlocfilehash: 058bda36020b739388dec63b063402d8891663ee
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626413"
---
# <a name="pool-table"></a>Tabela pool
 
A tabela Pool é uma tabela de suporte que armazena informações sobre os diversos pools de Front-Ends. Cada registro da tabela representa um pool.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primário  <br/> |Número único que identifica este pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Unique  <br/> |FQDN do pool.  <br/> |
   

