---
title: Tabela MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
ms.openlocfilehash: 308a9eee57089a02b8e3ff9924e0d9d34162f33e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295976"
---
# <a name="medialist-table"></a>Tabela MediaList
 
MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primária  <br/> |Valores: 1-7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Mapeamento estático dos valores de MediaID e Media: <br/>  1 – IM <br/>  Transferência de 2 arquivos <br/>  3-assistência remota <br/>  4-compartilhamento de aplicativos <br/>  5 – Áudio <br/>  6 – Vídeo <br/>  7-convite do aplicativo <br/> |
   
Se você está tentando determinar o tipo de modalidade dos valores em LcsCDR.SessionDetailsView.MediaTypes, use o seguinte snippet Join:  
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
