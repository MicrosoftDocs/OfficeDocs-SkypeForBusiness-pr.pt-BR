---
title: Tabela IMReportSummary no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: O IMReportSummaryTable fornece um relatório geral sobre as sessões de mensagens instantâneas contidas em uma organização. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815139"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabela IMReportSummary no Skype for Business Server 2015
 
O IMReportSummaryTable fornece um relatório geral sobre as sessões de mensagens instantâneas contidas em uma organização. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**StartTime ** <br/> |datetime  <br/> |Primária  <br/> |Data e hora de início da sessão de mensagens instantâneas.  <br/> |
|**Período de tempo** <br/> |caractere (1)  <br/> |Primária  <br/> ||
|**PoolFQDN** <br/> |nvarchar (257)  <br/> |Primária  <br/> |Nome de domínio totalmente qualificado do pool que hospeda a sessão.  <br/> |
|**AuthType** <br/> |int  <br/> |Primária  <br/> |Prioridade (por exemplo, urgente ou não urgente) da chamada. As informações de prioridade são armazenadas na [tabela CallPriorities no Skype for Business Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Número total de mensagens instantâneas trocadas durante a sessão.  <br/> |
   

