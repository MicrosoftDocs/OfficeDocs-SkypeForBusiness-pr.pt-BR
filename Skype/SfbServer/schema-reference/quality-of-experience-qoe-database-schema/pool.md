---
title: Tabela pool
ms.reviewer: ''
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela Pool é uma tabela de suporte que armazena informações sobre os diversos pools de Front-Ends. Cada registro da tabela representa um pool.
ms.openlocfilehash: 7fe1b2aecfcf78ee033dc907a104d0384fda5d40
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62403625"
---
# <a name="pool-table"></a>Tabela pool
 
A tabela Pool é uma tabela de suporte que armazena informações sobre os diversos pools de Front-Ends. Cada registro da tabela representa um pool.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primário  <br/> |Número único que identifica este pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Unique  <br/> |FQDN do pool.  <br/> |
   

