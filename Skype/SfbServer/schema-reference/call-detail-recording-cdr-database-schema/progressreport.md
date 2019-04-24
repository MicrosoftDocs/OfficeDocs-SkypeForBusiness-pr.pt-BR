---
title: Tabela ProgressReport
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Relatórios de progresso se baseiam em dados carregados pelo cliente ao banco de dados quando uma chamada ou sessão for concluída. Relatórios de progresso serão gravados apenas para chamadas e sessões Skype para Business Server 2015 determina que podem ser úteis para fins de diagnóstico.
ms.openlocfilehash: 6d638411f39956664c977e87785a1269ee788a5f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212863"
---
# <a name="progressreport-table"></a>Tabela ProgressReport
 
Relatórios de progresso se baseiam em dados carregados pelo cliente ao banco de dados quando uma chamada ou sessão for concluída. Relatórios de progresso serão gravados apenas para chamadas e sessões Skype para Business Server 2015 determina que podem ser úteis para fins de diagnóstico.
  
Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente aos erros, mas a mensagens que indicam o status das chamadas ou mensagens.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Data e hora do relatório de erro de andamento que contém o relatório de andamento. Consulte a [tabela ErrorReport Skype para Business Server 2015](errorreport.md) para obter mais informações. <br/> |
|**Identificação de erro** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação usado em conjunto com ErrorTime, ProgressReportSeq para identificar exclusivamente um relatório de andamento. Consulte a [tabela ErrorReport Skype para Business Server 2015](errorreport.md) para obter mais informações. <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação que identifica o relatório de erros. ErrorReporSeq é usado em conjunto com ErrorTime para identificar exclusivamente um relatório de erros. Consulte a [tabela ErrorReport Skype para Business Server 2015](errorreport.md) para obter mais informações <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primária  <br/> |Número de identificação para identificar o relatório de andamento. Usado em conjunto com o ErrorTime, ErrorReportSeq para identificar exclusivamente um relatório de andamento.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||ID de diagnóstico do relatório de andamento.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Externa  <br/> |Servidor que enviou o relatório de erro (se o relatório foi enviado de um componente do servidor). Consulte a [tabela de servidores](servers.md) para obter mais informações. Este campo foi introduzido no Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||O processo do Lync Server que o relatório é sobre. Consulte a tabela de aplicativo para obter mais informações.  <br/> |
|**Detalhe** <br/> |imagem  <br/> ||Detalhes de relatório de andamento, armazenados em formato binário para economizar espaço. Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/> cast (cast (Detail as varbinary(max)) como varchar  <br/> |
|**TelemetryId** <br/> |Identificador exclusivo  <br/> ||Identificador exclusivo que correlaciona ingresse em informações de tempo para os diferentes componentes envolvidos em uma conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tempo (em milissegundos) para um componente específico ingresse em uma conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
   

