---
title: Exibir ErrorReport
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: O modo de exibição ErrorReport armazena informações sobre erros informados. Cada registro é uma ocorrência de erro. Os erros são capturado pelo agente CDR executado no servidor front-end ou enviado pelo cliente. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: b1815d4420b5768b065a5695ea09174ecff91912
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="errorreport-view"></a>Exibir ErrorReport
 
O modo de exibição ErrorReport armazena informações sobre erros informados. Cada registro é uma ocorrência de erro. Os erros são capturado pelo agente CDR executado no servidor front-end ou enviado pelo cliente. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Hora do erro ocorreu. Usado em conjunto com ErrorReportSeq para identificar exclusivamente um erro.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Número de identificação para identificar o erro. Usado em conjunto com ErrorTime para identificar exclusivamente um erro.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnóstico do relatório de erro.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI do usuário que originou o erro.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que originou o erro. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que originou o erro. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI do usuário que foi o destino do relatório de erros.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que o destino do relatório de erros. Consulte a tabela UriTypes para obter mais informações.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que o destino do relatório de erros. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI da conferência que foi o destino do relatório de erros.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI da conferência que foi o destino do relatório de erros. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Hora da solicitação de sessão que originou o relatório de erros. Usado em conjunto com SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a solicitação de sessão que originou o relatório de erros. Usado em conjunto com SessionIdTime para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de diálogo SIP da sessão que originou o erro. O formato é:  <br/> diálogo; da marca; a marca  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/> cast (cast (ExternalId as varbinary(max)) como varchar  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usado pelo usuário que originou o erro.  <br/> |
|**ClientType** <br/> |int  <br/> |Cliente usado pelo usuário que originou o erro. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente usado pelo usuário que originou o erro.  <br/> |
|**Origem** <br/> |nvarchar(256)  <br/> |Nome do servidor que originou o erro (se o relatório foi enviado de um componente do servidor).  <br/> |
|**Aplicativo** <br/> |nvarchar(256)  <br/> |Nome do aplicativo que originou o erro (se o relatório foi enviado de um componente do servidor).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta para a sessão da mensagem SIP contendo o relatório de erros de SIP.  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |Tipo de solicitação que falhou.  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |Tipo de conteúdo da solicitação que falhou.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Tipo de sessão. Consulte a [tabela CallType Skype para Business Server 2015](calltype.md) para obter mais informações. <br/> |
|**TelemetryId** <br/> |Identificador exclusivo  <br/> |Identificador exclusivo correlacionando as informações de tempo de ingresso para os diferentes componentes envolvidos em uma conferência.  <br/> |
|**SetupTime** <br/> |int  <br/> |Tempo (em milissegundos) necessário para um componente específico ingresse em uma conferência.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indica se o relatório de erro foi capturado pelo agente de CDR em execução no servidor Front-End ou enviado pelo cliente.  <br/> |
|**Sinalizador** <br/> |smallint  <br/> |Reservado para uso futuro.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Informações adicionais sobre o erro.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nome de domínio totalmente qualificado do servidor Front-End que enviou o relatório.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Nome de domínio do pool que contém o servidor de Front-End que enviou o relatório totalmente qualificado.  <br/> |
   

