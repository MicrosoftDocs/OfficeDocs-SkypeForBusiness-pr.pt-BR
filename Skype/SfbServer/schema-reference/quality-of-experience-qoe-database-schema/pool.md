---
title: Tabela Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela de Pool é uma tabela de suporte que armazena informações sobre os vários pools de Front-End. Cada registro na tabela representa um pool.
ms.openlocfilehash: c4451f274e9afadbb7903e4095be22120c430689
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920058"
---
# <a name="pool-table"></a>Tabela Pool
 
A tabela de Pool é uma tabela de suporte que armazena informações sobre os vários pools de Front-End. Cada registro na tabela representa um pool.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este pool.  <br/> |
|**Nome_conjunto** <br/> |nvarchar(256)  <br/> |Exclusivo  <br/> |FQDN do pool.  <br/> |
   

