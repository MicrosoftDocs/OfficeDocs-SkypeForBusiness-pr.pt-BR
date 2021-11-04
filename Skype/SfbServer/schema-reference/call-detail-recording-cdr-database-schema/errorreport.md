---
title: Tabela ErrorReport no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: A tabela ErrorReport armazena informações sobre erros que ocorreram. Cada registro é uma ocorrência de erro. Os erros são capturados pelo agente CDR em execução no servidor front-end ou enviados do cliente.
ms.openlocfilehash: fd74743ed0b9dcd2fb9bb4cfa651f840528cb58c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745767"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabela ErrorReport no Skype for Business Server 2015
 
A tabela ErrorReport armazena informações sobre erros que ocorreram. Cada registro é uma ocorrência de erro. Os erros são capturados pelo agente CDR em execução no servidor front-end ou enviados do cliente.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primário  <br/> |Data e hora em que o erro ocorreu.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primário  <br/> |Número da ID para identificar o relatório de erro. Usado em conjunto com **ErrorTime** para identificar exclusivamente um relatório de erro. <br/> |
|**ErrorId** <br/> |int  <br/> |Foreign  <br/> |ID exclusiva do tipo de erro. Consulte a [tabela ErrorDef no Skype for Business Server 2015](errordef.md) para obter mais informações. <br/> |
|**FromUserId** <br/> |int  <br/> |Foreign  <br/> |Usuário que originou a solicitação que causou o erro. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**ToUserId** <br/> |int  <br/> |Foreign  <br/> |Usuário de destino para a solicitação que causou o erro. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |URI de conferência relacionado ao erro. Consulte a [tabela ConferenceUris no Skype for Business Server 2015](conferenceuris.md) para obter mais informações. Normalmente, se ConferenceUriId não for nulo, FromUserId ou ToUserId será nulo. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Foreign  <br/> |Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Foreign  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SourceId** <br/> |int  <br/> |Foreign  <br/> |Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente de servidor). Consulte a [tabela Servidores para](servers.md) obter mais informações. <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Foreign  <br/> |Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente de servidor). Consulte a [tabela Aplicativo no Skype for Business Server 2015](application.md) para obter mais informações. <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |imagem  <br/> | <br/> |Mais informações sobre o erro.  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Foreign  <br/> |A versão do cliente do ponto de extremidade que envia o relatório de erro. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||É o relatório de erro capturado pelo agente CDR em execução no servidor front-end ou enviado pelo cliente.  <br/> |
|**Flag** <br/> |smallint  <br/> ||Reserved for future use.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |Representa o nome de domínio totalmente qualificado do servidor que gerou o relatório de erro.  <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |Representa o nome de domínio totalmente qualificado do pool onde o relatório de erro foi gerado.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Skype for Business Server 2015.  <br/> |
   

