---
title: Tabela PayloadDescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: A tabela PayloadDescription é uma tabela de suporte. Cada registro representa um codec, que é usado em uma sessão de áudio ou de vídeo.
ms.openlocfilehash: 41819c8329802b224bd3848334eddbc9de6935f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294807"
---
# <a name="payloaddescription-table"></a>Tabela PayloadDescription
 
A tabela PayloadDescription é uma tabela de suporte. Cada registro representa um codec, que é usado em uma sessão de áudio ou de vídeo.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Exclusividade  <br/> |Nome do codec.  <br/> |
   

