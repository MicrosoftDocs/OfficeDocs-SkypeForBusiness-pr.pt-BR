---
title: Tabela UriTypes
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
ms.openlocfilehash: e21fe7d88c64acf57ad8d318a755b7fa6c73c1c2
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570055"
---
# <a name="uritypes-table"></a>Tabela UriTypes
 
A tabela UriTypes Table contém os diferentes tipos URI (Uniform resource identifier) monitorados no Skype para Business Server 2015.

Quando o CDR DB é criado, dois registros para representar PhoneUri e UserUri são criados e outros 
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primária  <br/> |Identificador exclusivo atribuído a um tipo de URI.  <br/> Valores possíveis - 0 a 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descrições dos diferentes tipos de URI. Os seguintes valores são atribuídos previamente: <br/>  1 - Uri do telefone <br/>  0 - Uri do usuário <br/> <br/>  Outros tipos possíveis incluem: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:Chat<br/>    conf:focus<br/>   mras<br/>