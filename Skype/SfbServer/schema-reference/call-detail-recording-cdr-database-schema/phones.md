---
title: Tabela Phones
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: A tabela Phones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
ms.openlocfilehash: 249b2a08e0751b6e8746f2da27a13e1151c375f7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836099"
---
# <a name="phones-table"></a>Tabela Phones
 
A tabela Phones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse telefone.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Telefone número.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Carimbo de data/hora (somente para uso interno).  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
   

