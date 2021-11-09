---
title: Tabela UriTypes
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: A Tabela UriTypes contém os diferentes tipos de URI (Uniform resource identifier) monitorados no Skype for Business Server 2015.
ms.openlocfilehash: ed0cc7e62aba47af6622f821af785d8daf571649
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859758"
---
# <a name="uritypes-table"></a>Tabela UriTypes
 
A Tabela UriTypes contém os diferentes tipos de URI (Uniform resource identifier) monitorados no Skype for Business Server 2015.

Quando o CDR DB é criado, dois registros para representar PhoneUri e UserUri são criados e os registros criados depois disso são atribuídos dinamicamente a UriTypeId. 
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primário  <br/> |Identificador exclusivo atribuído a um tipo de URI.  <br/> Valores possíveis - 0 a 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descrições de tipos de URI diferentes. Os seguintes valores são pré-atribuídos: <br/>  1 - Telefone Uri <br/>  0 - Uri do usuário <br/> <br/>  Outros tipos possíveis incluem: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
