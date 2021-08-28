---
title: Tabela Phones
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 37adaaa1885d91c84ee657c422b19debad294c01
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584855"
---
# <a name="phones-table"></a>Tabela Phones
 
A tabela Phones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse telefone.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Telefone número.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Carimbo de data/hora (somente para uso interno).  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
   

