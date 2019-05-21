---
title: Tabela CodecDescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: A tabela CodecDescription mapeia identificadores de codec exclusivos para o codec correspondente. Codecs são usados para codificar sinais digitais para transmissão e transmissão e, em seguida, decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
ms.openlocfilehash: 678b458757c54385b608d89efd6b2c621c6cd42f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295038"
---
# <a name="codecdescription-table"></a>Tabela CodecDescription
 
A tabela CodecDescription mapeia identificadores de codec exclusivos para o codec correspondente. Codecs são usados para codificar sinais digitais para transmissão e transmissão e, em seguida, decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primária  <br/> |Identificador exclusivo atribuído ao codec.  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |Exclusividade  <br/> |Descrição exclusiva do codec correspondente ao CodecDescriptionKey.  <br/> |
   

