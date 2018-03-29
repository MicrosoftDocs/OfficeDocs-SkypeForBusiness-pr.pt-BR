---
title: Tabela UserStatistics
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: A tabela UserStatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a>Tabela UserStatistics
 
A tabela UserStatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este usuário.  <br/> |
|**Hora do último login** <br/> |datetime  <br/> ||Última vez em que o usuário conectado.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Última vez que o usuário organizou uma conferência.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez em que o usuário enfrentou uma falha de ligação.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez em que o usuário enfrentou uma falha de ligação como um organizador da conferência.  <br/> |
   

