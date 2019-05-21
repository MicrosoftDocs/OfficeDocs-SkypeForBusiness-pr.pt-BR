---
title: Tabela ErrorReport no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: A tabela ErrorReport armazena informações sobre erros ocorridos. Cada registro é uma ocorrência de um erro. Os erros são capturados pelo agente CDR executado no servidor front-end ou enviados do cliente.
ms.openlocfilehash: 80a6106bd7c6b87a7519bca6ce5cc72f45147ad6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296263"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabela ErrorReport no Skype for Business Server 2015
 
A tabela ErrorReport armazena informações sobre erros ocorridos. Cada registro é uma ocorrência de um erro. Os erros são capturados pelo agente CDR executado no servidor front-end ou enviados do cliente.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primária  <br/> |Data e hora em que o erro ocorreu.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primária  <br/> |Número de identificação para identificar o relatório de erros. Usado em conjunto com **ErrorTime** para identificar com exclusividade um relatório de erro. <br/> |
|**ErrorID** <br/> |int  <br/> |Exterior  <br/> |ID exclusiva do tipo de erro. Consulte a [tabela ErrorDef no Skype for Business Server 2015](errordef.md) para obter mais informações. <br/> |
|**FromUserId** <br/> |int  <br/> |Exterior  <br/> |Usuário que originou a solicitação que causou o erro. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**Parauserid** <br/> |int  <br/> |Exterior  <br/> |Usuário de destino para a solicitação que causou o erro. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Exterior  <br/> |URL de conferência relacionada ao erro. Consulte a [tabela ConferenceUris no Skype for Business Server 2015](conferenceuris.md) para obter mais informações. Geralmente, se ConferenceUriId não for nulo, o FromUserId ou o parauserid será nulo. <br/> |
|**Id_da_sessãotime** <br/> |datetime  <br/> |Exterior  <br/> |Usado em conjunto com o **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Exterior  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **** a identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SourceID** <br/> |int  <br/> |Exterior  <br/> |Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente de servidor). Consulte a [tabela servidores](servers.md) para obter mais informações. <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Exterior  <br/> |Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente de servidor). Consulte a [tabela de aplicativos no Skype for Business Server 2015](application.md) para obter mais informações. <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |imagem  <br/> | <br/> |Mais informações sobre o erro.  <br/> Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Exterior  <br/> |A versão do cliente do ponto de extremidade que envia o relatório de erros. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||É o relatório de erros capturado pelo agente CDR em execução no servidor front-end ou enviado pelo cliente.  <br/> |
|**Sinalizador** <br/> |smallint  <br/> ||Reservado para uso futuro.  <br/> |
|**Telemetria** <br/> |Identificador  <br/> ||Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**ServerID** <br/> |int  <br/> |Exterior  <br/> |Representa o nome de domínio totalmente qualificado do servidor que gerou o relatório de erros.  <br/> |
|**Poolid** <br/> |int  <br/> |Exterior  <br/> |Representa o nome de domínio totalmente qualificado do pool onde o relatório de erro foi gerado.  <br/> |
|**LastModifiedtime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Skype for Business Server 2015.  <br/> |
   

