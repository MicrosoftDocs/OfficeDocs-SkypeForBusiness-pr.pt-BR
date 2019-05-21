---
title: Exibição ErrorReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: A exibição ErrorReport armazena informações sobre erros relatados. Cada registro é uma ocorrência de um erro. Os erros são capturados pelo agente CDR executado no servidor front-end ou enviados do cliente. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: a95d3d1e99fc41727c10ecef7beaafddc213dd17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296270"
---
# <a name="errorreport-view"></a>Exibição ErrorReport
 
A exibição ErrorReport armazena informações sobre erros relatados. Cada registro é uma ocorrência de um erro. Os erros são capturados pelo agente CDR executado no servidor front-end ou enviados do cliente. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Ocorreu um erro de hora. Usado em conjunto com ErrorReportSeq para identificar um erro exclusivamente.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Número de identificação para identificar o erro. Usado em conjunto com ErrorTime para identificar um erro com exclusividade.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnóstico do relatório de erros.  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |URL do usuário que originou o erro.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que originou o erro. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que originou o erro. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**ToUri** <br/> |nvarchar (450)  <br/> |URI do usuário que foi o destino do relatório de erros.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que direciona o relatório de erros. Consulte a tabela UriTypes para obter mais informações.  <br/> |
|**Tolocatário** <br/> |nvarchar(256)  <br/> |Locatário do usuário que direciona o relatório de erros. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URL da conferência que foi o alvo do relatório de erros.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI da conferência que foi o destino do relatório de erros. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**Id_da_sessãotime** <br/> |datetime  <br/> |Tempo de solicitação de sessão que originou o relatório de erros. Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a solicitação de sessão que originou o relatório de erros. Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**Caixa de diálogo** <br/> |VARSTRING (775)  <br/> |ID da caixa de diálogo SIP da sessão que originou o erro. O formato é:  <br/> caixa de diálogo; de-marca; até-marca  <br/> Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:  <br/> Cast (castid (externalId como varbinary (max)) como varchar (max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usada pelo usuário que originou o erro.  <br/> |
|**ClientType** <br/> |int  <br/> |Cliente usado pelo usuário que originou o erro. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Nome da categoria do cliente usado pelo usuário que originou o erro.  <br/> |
|**Origem** <br/> |nvarchar(256)  <br/> |Nome do servidor que originou o erro (se o relatório foi enviado a partir de um componente de servidor).  <br/> |
|**Aplicativo** <br/> |nvarchar(256)  <br/> |Nome do aplicativo que originou o erro (se o relatório foi enviado a partir de um componente de servidor).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para a sessão da mensagem SIP que contém o relatório de erros.  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |Tipo de solicitação que falhou.  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |Tipo de conteúdo da solicitação que falhou.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Tipo de sessão. Consulte a [tabela CallType no Skype for Business Server 2015](calltype.md) para obter mais informações. <br/> |
|**Telemetria** <br/> |identificador  <br/> |Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.  <br/> |
|**Setuptime** <br/> |int  <br/> |Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indica se o relatório de erros foi capturado pelo agente CDR em execução no servidor front-end ou enviado pelo cliente.  <br/> |
|**Sinalizador** <br/> |smallint  <br/> |Reservado para uso futuro.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Informações adicionais sobre o erro.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nome de domínio totalmente qualificado do servidor front-end que enviou o relatório.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Nome de domínio totalmente qualificado do pool que contém o servidor front-end que enviou o relatório.  <br/> |
   

