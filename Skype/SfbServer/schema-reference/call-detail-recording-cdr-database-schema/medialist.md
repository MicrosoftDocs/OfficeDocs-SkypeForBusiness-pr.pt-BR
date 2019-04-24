---
title: Tabela MediaList
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
ms.openlocfilehash: 72ae6dbb145c3bb284f1090b01585591e4e773bf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212905"
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
