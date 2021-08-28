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
ms.localizationpriority: medium
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: A tabela PayloadDescription é uma tabela de suporte. Cada registro representa um Codec, que é usado em uma sessão de áudio ou de vídeo.
ms.openlocfilehash: dedbf806c6cda1ce174e1a3282b81a409b63bced
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610558"
---
# <a name="payloaddescription-table"></a>Tabela PayloadDescription
 
A tabela PayloadDescription é uma tabela de suporte. Cada registro representa um Codec, que é usado em uma sessão de áudio ou de vídeo.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o Codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Unique  <br/> |Nome do codec.  <br/> |
   

