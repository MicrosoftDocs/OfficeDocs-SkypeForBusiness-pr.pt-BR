---
title: Tabela FileTransfers no Skype for Business Server 2015
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
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Cada registro representa uma sessão de transferência de arquivos.
ms.openlocfilehash: 2cd28adc21fd5ea5b19b03c0e527ea4097463943
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754358"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Tabela FileTransfers no Skype for Business Server 2015
 
Cada registro representa uma sessão de transferência de arquivos.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário, Estrangeiro  <br/> |Tempo da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, Estrangeiro  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**Nome do arquivo** <br/> |nvarchar(256)  <br/> ||Nome do arquivo.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Identificador exclusivo para distinguir entre as transferências de arquivo envolvendo o mesmo nome do arquivo.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Primário  <br/> |Usado para identificar cada mensagem de acompanhamento como sendo associado a este.  <br/> |
|**Accept** <br/> |bit  <br/> ||Pode ser TRUE ou NULL. Se for TRUE, Rejeitar e Cancelar serão NULL.  <br/> |
|**Reject** <br/> |bit  <br/> ||Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Cancelar serão NULL.  <br/> |
|**Cancel** <br/> |bit  <br/> ||Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Rejeitar serão NULL.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Skype for Business Server 2015.  <br/> |
   

