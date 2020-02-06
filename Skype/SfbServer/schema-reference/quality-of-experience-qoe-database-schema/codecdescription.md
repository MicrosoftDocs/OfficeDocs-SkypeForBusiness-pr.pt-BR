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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: A tabela CodecDescription mapeia identificadores de codec exclusivos para o codec correspondente. Codecs são usados para codificar sinais digitais para transmissão e transmissão e, em seguida, decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810359"
---
# <a name="codecdescription-table"></a>Tabela CodecDescription
 
A tabela CodecDescription mapeia identificadores de codec exclusivos para o codec correspondente. Codecs são usados para codificar sinais digitais para transmissão e transmissão e, em seguida, decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primária  <br/> |Identificador exclusivo atribuído ao codec.  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |Exclusividade  <br/> |Descrição exclusiva do codec correspondente ao CodecDescriptionKey.  <br/> |
   

