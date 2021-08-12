---
title: Tabela PayloadDescription
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: A tabela PayloadDescription é uma tabela de suporte. Cada registro representa um Codec, que é usado em uma sessão de áudio ou de vídeo.
ms.openlocfilehash: aa2d2048b61523ed0fab9b8b8796f7b3a29a83dbd1ebb5b5ec800e00520a387e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312979"
---
# <a name="payloaddescription-table"></a>Tabela PayloadDescription
 
A tabela PayloadDescription é uma tabela de suporte. Cada registro representa um Codec, que é usado em uma sessão de áudio ou de vídeo.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o Codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Unique  <br/> |Nome do codec.  <br/> |
   

