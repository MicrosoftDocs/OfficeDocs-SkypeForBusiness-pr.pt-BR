---
title: Tabela PayloadDescription
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: A tabela PayloadDescription é uma tabela de suporte. Cada registro representa um Codec, que é usado em uma sessão de áudio ou vídeo.
ms.openlocfilehash: 320542593479e3051992e8079abfdf9f54b0efc0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874197"
---
# <a name="payloaddescription-table"></a>Tabela PayloadDescription
 
A tabela PayloadDescription é uma tabela de suporte. Cada registro representa um Codec, que é usado em uma sessão de áudio ou vídeo.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o Codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Exclusivo  <br/> |Nome do codec.  <br/> |
   

