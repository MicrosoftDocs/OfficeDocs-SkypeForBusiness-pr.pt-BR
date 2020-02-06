---
title: Tabela UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: A tabela UriTypes contém os diferentes tipos de URI (Uniform Resource Identifier) monitorados no Skype for Business Server 2015.
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814839"
---
# <a name="uritypes-table"></a>Tabela UriTypes
 
A tabela UriTypes contém os diferentes tipos de URI (Uniform Resource Identifier) monitorados no Skype for Business Server 2015.

Quando o banco de banco de CDR é criado, dois registros para representar PhoneUri e UserUri são criados, e os registros criados após esse UriTypeId são atribuídos dinamicamente. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primária  <br/> |Identificador exclusivo atribuído a um tipo de URI.  <br/> Valores possíveis de 0 a 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descrições dos diferentes tipos de URI. Os seguintes valores são predefinidos: <br/>  1-URI do telefone <br/>  0-URI do usuário <br/> <br/>  Outros tipos possíveis incluem: <br/>conf: applicationsharing <br/> conf: áudio-vídeo<br/> conf: chat<br/>    conf: foco<br/>   mras<br/>
