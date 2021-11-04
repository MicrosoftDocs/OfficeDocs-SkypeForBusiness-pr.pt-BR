---
title: Tabela CodecDescription
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: A tabela CodecDescription associa identificadores exclusivos de codec a seus codecs correspondentes. Os codecs são usados para codificar sinais digitais para transmissão e divulgação e, depois, para decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
ms.openlocfilehash: 0f5601847458f7ce59e0cd691b573ec77605b667
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763239"
---
# <a name="codecdescription-table"></a>Tabela CodecDescription
 
A tabela CodecDescription associa identificadores exclusivos de codec a seus codecs correspondentes. Os codecs são usados para codificar sinais digitais para transmissão e divulgação e, depois, para decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primário  <br/> |Identificador exclusivo atribuído ao codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Unique  <br/> |Descrição exclusiva do codec correspondendo à chave de descrição do codec.  <br/> |
   

