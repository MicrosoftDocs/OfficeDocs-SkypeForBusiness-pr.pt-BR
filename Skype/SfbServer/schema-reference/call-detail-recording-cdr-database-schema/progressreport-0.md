---
title: Exibição ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: A exibição ProgressReport armazena informações sobre sessões concluídas. Os relatórios de progresso será gravados somente para chamadas e sessões que o Lync Server 2013 determina como úteis para diagnósticos. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823181"
---
# <a name="progressreport-view"></a>Exibição ProgressReport
 
A exibição ProgressReport armazena informações sobre sessões concluídas. Os relatórios de progresso será gravados somente para chamadas e sessões que o Lync Server 2013 determina como úteis para diagnósticos. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
> [!NOTE]
> Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens. 
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Hora do erro. Usada com o ErrorReportSeq para identificar um erro.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Um número de ID para identificar o erro. Usado com ErrorTime para identificar um erro.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID para identificar o relatórios de progresso. Usado para distinguir relatórios de progresso do mesmo relatório de erro.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnóstico do relatório de erro.  <br/> |
|**Fonte** <br/> |nvarchar(256)  <br/> |Nome do servidor que originou o erro (se o relatório foi enviado de um componente do servidor).  <br/> |
|**Aplicativo** <br/> |nvarchar(256)  <br/> |Nome de um aplicativo que originou o erro (se o relatório foi enviado de um componente do servidor).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Informações de erro adicionais.  <br/> |
   

