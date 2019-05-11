---
title: Exibir ProgressReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: O modo de exibição ProgressReport armazena informações sobre as sessões concluídas. Relatórios de progresso serão gravados apenas para chamadas e sessões que determina de Lync Server 2013 podem ser úteis para fins de diagnóstico. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 4508b2f1772a3b21d51d561c310b31f00740973d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930627"
---
# <a name="progressreport-view"></a>Exibir ProgressReport
 
O modo de exibição ProgressReport armazena informações sobre as sessões concluídas. Relatórios de progresso serão gravados apenas para chamadas e sessões que determina de Lync Server 2013 podem ser úteis para fins de diagnóstico. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
> [!NOTE]
> Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente aos erros, mas a mensagens que indicam o status das chamadas ou mensagens. 
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Hora do erro ocorreu. Usado em conjunto com ErrorReportSeq para identificar exclusivamente um erro.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Número de identificação para identificar o erro. Usado em conjunto com ErrorTime para identificar exclusivamente um erro.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID para identificar o relatório de andamento. Usado para distinguir os relatórios de progresso do relatório de erros mesmo.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnóstico do relatório de erro.  <br/> |
|**Origem** <br/> |nvarchar(256)  <br/> |Nome do servidor que originou o erro (se o relatório foi enviado de um componente do servidor).  <br/> |
|**Aplicativo** <br/> |nvarchar(256)  <br/> |Nome do aplicativo que originou o erro (se o relatório foi enviado de um componente do servidor).  <br/> |
|**TelemetryId** <br/> |Identificador exclusivo  <br/> |Identificador exclusivo correlacionando as informações de tempo de ingresso para os diferentes componentes envolvidos em uma conferência.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Tempo (em milissegundos) necessário para um componente específico ingresse em uma conferência.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Informações de erro adicionais.  <br/> |
   

