---
title: Tabela ProgressReport
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Relatórios de andamento são baseados nos dados carregados pelo cliente no banco de dados após a conclusão de uma chamada ou sessão. Relatórios de progresso serão gravados apenas para chamadas e sessões que o Skype for Business Server 2015 determina que podem ser úteis para fins de diagnóstico.
ms.openlocfilehash: 4169ab029c0ce491b77b39735e309e102ac6e356
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823171"
---
# <a name="progressreport-table"></a>Tabela ProgressReport
 
Relatórios de andamento são baseados nos dados carregados pelo cliente no banco de dados após a conclusão de uma chamada ou sessão. Relatórios de progresso serão gravados apenas para chamadas e sessões que o Skype for Business Server 2015 determina que podem ser úteis para fins de diagnóstico.
  
Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primário, externo  <br/> |Data e hora do relatório de erros de andamento. Consulte a [tabela ErrorReport no Skype for Business Server 2015](errorreport.md) para obter mais informações. <br/> |
|**ErrorId** <br/> |int  <br/> |Primário, externo  <br/> |Número de ID usado junto com o ErrorTime, ProgressReportSeq para identificar exclusivamente um relatório de andamento. Consulte a [tabela ErrorReport no Skype for Business Server 2015](errorreport.md) para obter mais informações. <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primário, externo  <br/> |Número de ID que identifica o relatório de erros. O ErrorReporSeq é usado em conjunto com o ErrorTime para identificar exclusivamente um relatório de erros. Consulte a [tabela ErrorReport no Skype for Business Server 2015](errorreport.md) para obter mais informações <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primário  <br/> |Número de ID para identificar o relatório de andamento. Usado junto com ErrorTime e ErrorReportSeq para identificar exclusivamente um relatório de andamento.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||ID do diagnóstico do relatório de andamento.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Externo  <br/> |Servidor que enviou o relatório de erros (se o relatório foi enviado de um componente do servidor), Consulte a Servers Table para obter mais informações. Consulte a [tabela Servidores para](servers.md) obter mais informações. Este campo foi introduzido no Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||O processo do Lync Server do qual o relatório trata. Consulte a Application Table para obter mais informações  <br/> |
|**Ver os detalhes** <br/> |imagem  <br/> ||Detalhes do relatório de andamento armazenados em formato binário para economizar espaço. Esses dados podem ser convertidos em formato de texto usando essa sintaxe:  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificador exclusivo que correlaciona as informações da hora de ingresso com os diferentes componentes envolvidos em uma conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tempo (em milissegundos) para que um componente específico ingresse em uma conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
   

