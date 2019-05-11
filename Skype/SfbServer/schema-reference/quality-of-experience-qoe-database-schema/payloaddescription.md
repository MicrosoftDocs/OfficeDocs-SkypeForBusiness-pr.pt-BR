---
title: Tabela PayloadDescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: A tabela PayloadDescription é uma tabela de suporte. Cada registro representa um Codec, que é usado em uma sessão de áudio ou vídeo.
ms.openlocfilehash: 2854d3b1dd5338b9d150bb1a9c36a0409d0f8099
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920059"
---
# <a name="payloaddescription-table"></a>Tabela PayloadDescription
 
A tabela PayloadDescription é uma tabela de suporte. Cada registro representa um Codec, que é usado em uma sessão de áudio ou vídeo.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o Codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Exclusivo  <br/> |Nome do codec.  <br/> |
   

