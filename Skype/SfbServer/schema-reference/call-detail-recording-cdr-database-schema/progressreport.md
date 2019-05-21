---
title: Tabela ProgressReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Os relatórios de progresso são baseados em dados carregados pelo cliente para o banco de dados após a conclusão de uma chamada ou sessão. Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Skype for Business Server 2015 determina pode ser útil para fins de diagnóstico.
ms.openlocfilehash: 9022c7707e0d2f0a4346ed629bf51420c312b10a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295899"
---
# <a name="progressreport-table"></a>Tabela ProgressReport
 
Os relatórios de progresso são baseados em dados carregados pelo cliente para o banco de dados após a conclusão de uma chamada ou sessão. Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Skype for Business Server 2015 determina pode ser útil para fins de diagnóstico.
  
Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primário, estrangeiro  <br/> |Data e hora do relatório de erro de progresso que contém este relatório de progresso. Consulte a [tabela errorreport no Skype for Business Server 2015](errorreport.md) para obter mais informações. <br/> |
|**ErrorID** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação usado em conjunto com ErrorTime, ProgressReportSeq para identificar exclusivamente um relatório de progresso. Consulte a [tabela errorreport no Skype for Business Server 2015](errorreport.md) para obter mais informações. <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação que identifica o relatório de erros. ErrorReporSeq é usado em conjunto com ErrorTime para identificar com exclusividade um relatório de erro. Consulte a [tabela errorreport no Skype for Business Server 2015](errorreport.md) para obter mais informações <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primária  <br/> |Número de identificação para identificar o relatório de progresso. Usado em conjunto com ErrorTime e ErrorReportSeq para identificar com exclusividade um relatório de progresso.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||ID de diagnóstico do relatório de progresso.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**SourceID** <br/> |int  <br/> |Exterior  <br/> |Servidor que enviou o relatório de erro (se o relatório foi enviado de um componente de servidor). Consulte a [tabela servidores](servers.md) para obter mais informações. Este campo foi apresentado no Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||O processo do Lync Server no qual o relatório se encontra. Consulte a tabela de aplicativos para obter mais informações.  <br/> |
|**Detalhe** <br/> |imagem  <br/> ||Detalhes do relatório de progresso armazenados em formato binário para economizar espaço. Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:  <br/> Cast (Cast (detalhes como varbinary (max)) as varchar (max))  <br/> |
|**Telemetria** <br/> |Identificador  <br/> ||Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tempo (em milissegundos) para um componente específico para ingressar em uma conferência.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
   

