---
title: Tabela pool
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: 501c35c6e3a8ded5d1a9c7cfab58395d91d0e653
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740257"
---
# <a name="pool-table"></a>Tabela pool
 
A tabela Pool é uma tabela de suporte que armazena informações sobre os diversos pools de Front-Ends. Cada registro da tabela representa um pool.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primário  <br/> |Número único que identifica este pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Unique  <br/> |FQDN do pool.  <br/> |
   

