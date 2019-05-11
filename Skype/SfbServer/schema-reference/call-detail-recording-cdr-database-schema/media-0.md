---
title: Modo de exibição de mídia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: O modo de exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia é usado. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 83caf609efae4e97961e7c62c3a1ed6c6004e8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930690"
---
# <a name="media-view"></a>Modo de exibição de mídia
 
O modo de exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia é usado. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
> [!NOTE]
> O modo de exibição de mídia não deve ser usado para calcular a duração de mídia para uma sessão. Este modo de exibição contém os detalhes de sinalização de troca de mídia em uma sessão. Troca de mídia é feita com a solicitação de convite e StartTime indica a hora em que o convite foi enviado. O tempo de convidar não necessariamente que a mídia Iniciar tempo, porque a mídia inicia somente depois que a sessão é aceito. 
  
O modo de exibição de mídia contém todas as colunas no [SessionDetails view](sessiondetails-0.md) além das listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Tipo de mídia. Consulte a [tabela MediaList](medialist.md) para obter mais informações. <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Hora em que a solicitação de mídia foi enviada.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
   

