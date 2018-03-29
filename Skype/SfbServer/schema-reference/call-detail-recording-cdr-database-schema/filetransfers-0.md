---
title: Tabela FileTransfers Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Cada registro representa uma sessão de transferência de arquivo.
ms.openlocfilehash: 07ab898246efbac623910886000e97037f43ead2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Tabela FileTransfers Skype para Business Server 2015
 
Cada registro representa uma sessão de transferência de arquivo.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Hora da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**Nome do arquivo** <br/> |nvarchar(256)  <br/> ||Nome do arquivo.  <br/> |
|**FileIdentity** <br/> |Identificador exclusivo  <br/> ||Identificador exclusivo para distinguir entre transferências de arquivo envolvendo o mesmo nome de arquivo.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Primária  <br/> |Usado para identificar cada mensagem de acompanhamento como sendo associado a este.  <br/> |
|**Aceitar** <br/> |bit  <br/> ||Pode ser TRUE ou nulo. Se for TRUE, em seguida, rejeitar e Cancelar será NULL.  <br/> |
|**Rejeitar** <br/> |bit  <br/> ||Pode ser TRUE ou nulo. Se for TRUE, em seguida, aceitar e Cancelar será NULL.  <br/> |
|**Cancelar** <br/> |bit  <br/> ||Pode ser TRUE ou nulo. Se for TRUE, em seguida, aceitar e rejeitar será NULL.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Skype para Business Server 2015.  <br/> |
   

