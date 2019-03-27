---
title: Tabela UriTypes
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: A tabela UriTypes Table contém os diferentes tipos URI (Uniform resource identifier) monitorados no Skype para Business Server 2015.
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899642"
---
# <a name="uritypes-table"></a>Tabela UriTypes
 
A tabela UriTypes Table contém os diferentes tipos URI (Uniform resource identifier) monitorados no Skype para Business Server 2015.

Quando o CDR DB é criado, dois registros para representar PhoneUri e UserUri são criados e registros criados depois que são atribuídas dinamicamente UriTypeId. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primária  <br/> |Identificador exclusivo atribuído a um tipo de URI.  <br/> Valores possíveis - 0 a 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descrições dos diferentes tipos de URI. Os seguintes valores são atribuídos previamente: <br/>  1 - Uri do telefone <br/>  0 - Uri do usuário <br/> <br/>  Outros tipos possíveis incluem: <br/>conf:applicationsharing <br/> conf:Audio-vídeo<br/> conf:Chat<br/>    conf:Focus<br/>   mras<br/>
