---
title: Tabela CodecDescription
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: A tabela CodecDescription associa identificadores exclusivos de codec a seus codecs correspondentes. Os codecs são usados para codificar sinais digitais para transmissão e divulgação e, depois, para decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
ms.openlocfilehash: 9facaa9ddf29024a731f9e199b5cf749d91bc6671c320ded510d693755640f38
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309170"
---
# <a name="codecdescription-table"></a>Tabela CodecDescription
 
A tabela CodecDescription associa identificadores exclusivos de codec a seus codecs correspondentes. Os codecs são usados para codificar sinais digitais para transmissão e divulgação e, depois, para decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primário  <br/> |Identificador exclusivo atribuído ao codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Unique  <br/> |Descrição exclusiva do codec correspondendo à chave de descrição do codec.  <br/> |
   

