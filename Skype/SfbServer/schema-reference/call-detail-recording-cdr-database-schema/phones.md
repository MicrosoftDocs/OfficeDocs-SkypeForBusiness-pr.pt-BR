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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: A tabela Phones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que possuem registros no banco de dados.
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823261"
---
# <a name="phones-table"></a>Tabela Phones
 
A tabela Phones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que possuem registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica este telefone.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Número de telefone.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Carimbo de data/hora (somente para uso interno).  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
   

