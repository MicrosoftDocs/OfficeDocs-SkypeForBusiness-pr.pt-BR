---
title: Tabela Phones
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: A tabela de telefones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894639"
---
# <a name="phones-table"></a>Tabela Phones
 
A tabela de telefones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse telefone.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Número de telefone.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Carimbo de hora (somente para uso interno).  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
   

