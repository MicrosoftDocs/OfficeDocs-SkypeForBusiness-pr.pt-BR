---
title: Tabela MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
ms.openlocfilehash: 3eaa40cb5ae03129edaa36effa7b40012fc38429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930648"
---
# <a name="medialist-table"></a>Tabela MediaList
 
MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primária  <br/> |Valores: 1-7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Mapeamento estático dos valores de MediaID e Media: <br/>  1 – IM <br/>  2 - arquivo transferência <br/>  3 - assistência remota <br/>  4 - compartilhamento de aplicativos de <br/>  5 – Áudio <br/>  6 – Vídeo <br/>  7 - convidar app <br/> |
   
Se você está tentando determinar o tipo de modalidade dos valores em LcsCDR.SessionDetailsView.MediaTypes, use o seguinte snippet Join:  
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
