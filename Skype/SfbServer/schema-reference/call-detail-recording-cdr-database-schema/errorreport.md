---
title: Tabela ErrorReport Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: A tabela ErrorReport armazena informações sobre os erros que ocorreram. Cada registro é uma ocorrência de erro. Os erros são capturado pelo agente CDR executado no servidor front-end ou enviado pelo cliente.
ms.openlocfilehash: 4cb3cebba59201daa6f2a601ec969ed976ec3167
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930245"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabela ErrorReport Skype para Business Server 2015
 
A tabela ErrorReport armazena informações sobre os erros que ocorreram. Cada registro é uma ocorrência de erro. Os erros são capturado pelo agente CDR executado no servidor front-end ou enviado pelo cliente.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primária  <br/> |Data e hora em que o erro ocorreu.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primária  <br/> |Número de identificação para identificar o relatório de erros. Usado em conjunto com **ErrorTime** para identificar exclusivamente um relatório de erros. <br/> |
|**Identificação de erro** <br/> |int  <br/> |Externa  <br/> |ID exclusiva do tipo de erro. Consulte a [tabela ErrorDef no Skype para Business Server 2015](errordef.md) para obter mais informações. <br/> |
|**FromUserId** <br/> |int  <br/> |Externa  <br/> |Usuário que originou a solicitação que causou o erro. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**ToUserId** <br/> |int  <br/> |Externa  <br/> |Usuário de destino para a solicitação que causou o erro. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externa  <br/> |URI de conferência relacionadas ao erro. Consulte a [tabela ConferenceUris do Skype para Business Server 2015](conferenceuris.md) para obter mais informações. Geralmente, se ConferenceUriId não for nula, em seguida, FromUserId ou ToUserId será nulo. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Externa  <br/> |Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SourceId** <br/> |int  <br/> |Externa  <br/> |Servidor que enviou o relatório de erro (se o relatório está sendo enviado de um componente do servidor). Consulte a [tabela de servidores](servers.md) para obter mais informações. <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Externa  <br/> |Servidor que enviou o relatório de erro (se o relatório está sendo enviado de um componente do servidor). Consulte a [tabela de aplicativo no Skype para Business Server 2015](application.md) para obter mais informações. <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |imagem  <br/> | <br/> |Obter mais informações sobre o erro.  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Externa  <br/> |A versão do cliente do ponto de extremidade que envia o relatório de erros. Consulte a [tabela ClientVersions Skype para Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||É o relatório de erros capturado pelo agente de CDR em execução no servidor front-end ou enviado pelo cliente.  <br/> |
|**Sinalizador** <br/> |smallint  <br/> ||Reservado para uso futuro.  <br/> |
|**TelemetryId** <br/> |Identificador exclusivo  <br/> ||Identificador exclusivo correlacionando as informações de tempo de ingresso para os diferentes componentes envolvidos em uma conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tempo (em milissegundos) necessário para um componente específico ingresse em uma conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Externa  <br/> |Representa o nome de domínio totalmente qualificado do servidor que gerou o relatório de erros.  <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Representa o nome de domínio totalmente qualificado do pool onde o relatório de erro foi gerado.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Skype para Business Server 2015.  <br/> |
   

