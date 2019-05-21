---
title: Tabela Phones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: A tabela de telefones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295941"
---
# <a name="phones-table"></a>Tabela Phones
 
A tabela de telefones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PHONEID** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este telefone.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |Número de telefone.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Carimbo de data/hora (apenas para uso interno).  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
   

