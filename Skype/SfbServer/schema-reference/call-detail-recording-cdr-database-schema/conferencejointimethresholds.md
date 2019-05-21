---
title: Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo relatório de Resumo de tempo de ingresso em conferência. O relatório de Resumo de tempo de ingresso em conferência resume o tempo necessário para que os usuários ingressem com êxito em uma conferência; esses valores de tempo são relatados como uma média e em uma das seguintes categorias:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296494"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015
 
A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo relatório de Resumo de tempo de ingresso em conferência. O relatório de Resumo de tempo de ingresso em conferência resume o tempo necessário para que os usuários ingressem com êxito em uma conferência; esses valores de tempo são relatados como uma média e em uma das seguintes categorias:
  
- Menos de 2 segundos.
    
- Entre 2 e 5 segundos.
    
- Entre 5 segundos e 10 segundos.
    
- Mais de 10 segundos.
    
A tabela ConferenceJoinTimeThresholds contém os valores de classificação 2 segundos, 5 segundos e 10 segundos.
  
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Thresholdid** <br/> |int  <br/> |Primária  <br/> |Identificador exclusivo da classificação.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Limite superior da classificação. Os valores permitidos são: <br/>  2 <br/>  5 <br/>  254 <br/> |
   

