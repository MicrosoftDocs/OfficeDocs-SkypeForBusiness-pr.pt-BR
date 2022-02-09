---
title: Tabela MediaList
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
ms.openlocfilehash: da5d1c90f768e059ccb61b471d8f8e538c8c53aa
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418364"
---
# <a name="medialist-table"></a>Tabela MediaList
 
MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primário  <br/> |Valores: 1 a 7  <br/> |
|**Mídia** <br/> |nvarchar(256)  <br/> || Mapeamento estático dos valores MediaID e Media: <br/>  1 -- IM <br/>  2 - Transferência de Arquivos <br/>  3 - Assistência Remota <br/>  4 - Compartilhamento de Aplicativos <br/>  5 -- Áudio <br/>  6 -- Vídeo <br/>  7 - Convite do Aplicativo <br/> |
   
Se você estiver tentando determinar o tipo de modalidade para os valores em LcsCDR.SessionDetailsView.MediaTypes, será necessário usar o seguinte trecho de Junção: 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
