---
title: Exibição de mídia
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: A exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela caso mais de um tipo de mídia seja usado. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 2ed8d66bf55594e3524a43b35df3bfa6d859055a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828554"
---
# <a name="media-view"></a>Exibição de mídia
 
A exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela caso mais de um tipo de mídia seja usado. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
> [!NOTE]
> A exibição de mídia não deve ser usada para calcular a duração de mídia para uma sessão. Essa exibição contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é feita pela solicitação INVITE, e o StartTime indica o horário em que o INVITE foi enviado. O horário de convite não significa, necessariamente, o horário de início da mídia, pois a mídia só começa depois que a sessão tenha sido aceita. 
  
O exibição Mídia contém todas as colunas no [exibição SessionDetails,](sessiondetails-0.md) além das listadas abaixo.
  
|**Column**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**Mídia** <br/> |nvarchar(256)  <br/> |Tipo de mídia. Consulte a [tabela MediaList para](medialist.md) obter mais informações. <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Horário em que a solicitação de mídia foi enviada.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Horário de término da sessão.  <br/> |
   

