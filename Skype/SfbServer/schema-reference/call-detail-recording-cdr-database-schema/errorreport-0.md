---
title: Exibição ErrorReport
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
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: A exibição ErrorReport armazena informações sobre erros relatados. Cada registro é uma ocorrência de erro. Os erros são capturados pelo agente CDR em execução no servidor front-end ou enviados do cliente. Esta exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: e00e2bddaea34be6b09bc211991539ad6123603e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821711"
---
# <a name="errorreport-view"></a>Exibição ErrorReport
 
A exibição ErrorReport armazena informações sobre erros relatados. Cada registro é uma ocorrência de erro. Os erros são capturados pelo agente CDR em execução no servidor front-end ou enviados do cliente. Esta exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Hora do erro. Usada com o ErrorReportSeq para identificar um erro.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Um número de ID para identificar o erro. Usado com ErrorTime para identificar um erro.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnóstico do relatório de erro.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI do usuário que originou o erro.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que originou o erro. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que originou o erro. Consulte a [tabela Tenants para](tenants.md) obter mais informações. <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI do usuário que era o destino do relatório de erros.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário alvo do relatório de erros. Consulte o UriTypes Table para obter mais informações.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário alvo do relatório de erros. Consulte a [tabela Tenants para](tenants.md) obter mais informações. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI da conferência que foi o destino do relatório de erros.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI da conferência que foi o destino do relatório de erros. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Hora da solicitação de sessão que originou o relatório de erros. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a solicitação de sessão que originou o relatório de erros. Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID da caixa de diálogo SIP da sessão que originou o erro. O formato é:  <br/> dialog;from-tag;to-tag  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/> cast(cast(ExternalId as varbinary(max)) as varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usada pelo usuário que originou o erro.  <br/> |
|**ClientType** <br/> |int  <br/> |Cliente usado pelo usuário que originou o erro. Consulte a [tabela UserAgentDef para](useragentdef.md) obter mais detalhes. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente usado pelo usuário que originou o erro.  <br/> |
|**Fonte** <br/> |nvarchar(256)  <br/> |Nome do servidor que originou o erro (se o relatório foi enviado de um componente do servidor).  <br/> |
|**Aplicativo** <br/> |nvarchar(256)  <br/> |Nome de um aplicativo que originou o erro (se o relatório foi enviado de um componente do servidor).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para a sessão da mensagem SIP que contém o relatório de erros.  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |Tipo de solicitação que falhou.  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |Tipo de conteúdo da solicitação que falhou.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Tipo de sessão. Consulte a [tabela CallType no Skype for Business Server 2015](calltype.md) para obter mais informações. <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.  <br/> |
|**SetupTime** <br/> |int  <br/> |Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indica se o relatório de erros foi capturado pelo agente CDR em execução no servidor front-end ou enviado pelo cliente.  <br/> |
|**Flag** <br/> |smallint  <br/> |Reserved for future use.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Informações adicionais sobre o erro.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nome de domínio totalmente qualificado do servidor front-end que enviou o relatório.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Nome de domínio totalmente qualificado do pool que contém o servidor front-end que enviou o relatório.  <br/> |
   

