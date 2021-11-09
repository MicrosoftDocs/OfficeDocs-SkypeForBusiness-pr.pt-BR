---
title: Tabela MediaList
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 643c373eb7e6a73cf8755f14ea0f5497efee6fed
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849624"
---
# <a name="medialist-table"></a>Tabela MediaList
 
MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primário  <br/> |Valores: 1 a 7  <br/> |
|**Mídia** <br/> |nvarchar(256)  <br/> || Mapeamento estático dos valores MediaID e Media: <br/>  1 -- IM <br/>  2 - Transferência de Arquivos <br/>  3 - Assistência Remota <br/>  4 - Compartilhamento de Aplicativos <br/>  5 -- Áudio <br/>  6 -- Vídeo <br/>  7 - Convite do Aplicativo <br/> |
   
Se você estiver tentando determinar o tipo de modalidade para os valores em LcsCDR.SessionDetailsView.MediaTypes, será necessário usar o seguinte trecho de Junção: 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
