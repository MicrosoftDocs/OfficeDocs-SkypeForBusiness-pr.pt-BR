---
title: Tabela pool
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela Pool é uma tabela de suporte que armazena informações sobre os diversos pools de Front-Ends. Cada registro da tabela representa um pool.
ms.openlocfilehash: fb79f21bd78c0c503da920eab04c30f45cdfc3d6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856398"
---
# <a name="pool-table"></a>Tabela pool
 
A tabela Pool é uma tabela de suporte que armazena informações sobre os diversos pools de Front-Ends. Cada registro da tabela representa um pool.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primário  <br/> |Número único que identifica este pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Unique  <br/> |FQDN do pool.  <br/> |
   

