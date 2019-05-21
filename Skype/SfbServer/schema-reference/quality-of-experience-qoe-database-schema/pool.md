---
title: Tabela Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela de pool é uma tabela de suporte que armazena informações sobre os vários pools de front-end. Cada registro na tabela representa um pool.
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294800"
---
# <a name="pool-table"></a>Tabela Pool
 
A tabela de pool é uma tabela de suporte que armazena informações sobre os vários pools de front-end. Cada registro na tabela representa um pool.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Exclusividade  <br/> |FQDN do pool.  <br/> |
   

