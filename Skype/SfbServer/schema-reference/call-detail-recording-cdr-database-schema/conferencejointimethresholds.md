---
title: Tabela ConferenceJoinTimeThresholds no Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'A tabela ConferenceJoinTimeThresholds contém os limites de classificação utilizados pelo relatório de resumo de tempo de ingresso de conferência. O relatório de resumo de tempo de ingresso de conferência resume o tempo necessário para os usuários ingressem em uma conferência; com êxito Esses valores de tempo são relatados como uma média e em uma das seguintes categorias:'
ms.openlocfilehash: 75df75e16d2a4ed34f667c94f2b2f0960f56e7ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901433"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Tabela ConferenceJoinTimeThresholds no Skype para Business Server 2015
 
A tabela ConferenceJoinTimeThresholds contém os limites de classificação utilizados pelo relatório de resumo de tempo de ingresso de conferência. O relatório de resumo de tempo de ingresso de conferência resume o tempo necessário para os usuários ingressem em uma conferência; com êxito Esses valores de tempo são relatados como uma média e em uma das seguintes categorias:
  
- Menos de 2 segundos.
    
- Entre 2 e 5 segundos.
    
- Entre 5 e 10 segundos.
    
- Mais de 10 segundos.
    
A tabela ConferenceJoinTimeThresholds contém os valores de classificação de 2 segundos, 5 segundos e 10 segundos.
  
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primária  <br/> |Identificador exclusivo para a classificação.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Limite superior para a classificação. Os valores permitidos são: <br/>  2 <br/>  5 <br/>  10 <br/> |
   

