---
title: Tabela IMReportSummary no Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: O IMReportSummaryTable oferece um relatório geral sobre as sessões de mensagem instantânea mantidas em uma organização. Esta tabela foi introduzida no Microsoft Lync Server 2013.
---

# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabela IMReportSummary no Skype for Business Server 2015
 
O IMReportSummaryTable oferece um relatório geral sobre as sessões de mensagem instantânea mantidas em uma organização. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primário  <br/> |Data e hora que a sessão de mensagem instantânea começou.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primário  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primário  <br/> |Nome de domínio totalmente qualificado do pool hospedando a sessão.  <br/> |
|**AuthType** <br/> |int  <br/> |Primário  <br/> |Prioridade (por exemplo, urgente ou não urgente) da chamada. As informações de prioridade são armazenadas [na tabela CallPriorities Skype for Business Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Número total de mensagens instantâneas trocadas durante a sessão.  <br/> |
   

