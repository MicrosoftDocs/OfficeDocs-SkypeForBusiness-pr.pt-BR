---
title: Exibição ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: A exibição ProgressReport armazena informações sobre sessões concluídas. Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Lync Server 2013 determina que podem ser úteis para fins de diagnóstico. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814979"
---
# <a name="progressreport-view"></a>Exibição ProgressReport
 
A exibição ProgressReport armazena informações sobre sessões concluídas. Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Lync Server 2013 determina que podem ser úteis para fins de diagnóstico. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
> [!NOTE]
> Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens. 
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Ocorreu um erro de hora. Usado em conjunto com ErrorReportSeq para identificar um erro exclusivamente.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Número de identificação para identificar o erro. Usado em conjunto com ErrorTime para identificar um erro com exclusividade.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID para identificar o relatório de progresso. Usado para distinguir relatórios de progresso do mesmo relatório de erro.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnóstico do relatório de erros.  <br/> |
|**Origem** <br/> |nvarchar(256)  <br/> |Nome do servidor que originou o erro (se o relatório foi enviado a partir de um componente de servidor).  <br/> |
|**Aplicativo** <br/> |nvarchar(256)  <br/> |Nome do aplicativo que originou o erro (se o relatório foi enviado a partir de um componente de servidor).  <br/> |
|**Telemetria** <br/> |identificador  <br/> |Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Informações adicionais sobre o erro.  <br/> |
   

