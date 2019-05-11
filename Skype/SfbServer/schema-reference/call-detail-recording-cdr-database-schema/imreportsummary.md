---
title: Tabela IMReportSummary no Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: O IMReportSummaryTable fornece um relatório geral sobre a mantidos em uma organização de sessões de mensagens instantâneas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 3611243e49821e5fae211ce55858cdee555dd383
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901042"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabela IMReportSummary no Skype para Business Server 2015
 
O IMReportSummaryTable fornece um relatório geral sobre a mantidos em uma organização de sessões de mensagens instantâneas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**StartTime ** <br/> |datetime  <br/> |Primária  <br/> |Data e hora em que a sessão de mensagens instantâneas começou.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primária  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primária  <br/> |Nome de domínio totalmente qualificado do pool hospedando a sessão.  <br/> |
|**Tipo de autenticação** <br/> |int  <br/> |Primária  <br/> |Prioridade (por exemplo, urgente ou não urgente) da chamada. Informações de prioridade são armazenadas na [tabela CallPriorities do Skype para Business Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Número total de mensagens instantâneas trocadas durante a sessão.  <br/> |
   

