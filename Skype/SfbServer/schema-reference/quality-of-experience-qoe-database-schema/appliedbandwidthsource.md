---
title: Tabela AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma fonte.
ms.openlocfilehash: 49e4fd4b2c2543399d073d5d03e8cccad8b0038e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924847"
---
# <a name="appliedbandwidthsource-table"></a>Tabela AppliedBandwidthSource
 
A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma fonte.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica a origem.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Exclusivo  <br/> |Isso representa a origem do limite de largura de banda que está sendo imposta. Ele descreve onde o limite de largura de banda é proveniente (por exemplo, "Política de servidor", "Ativar o servidor" ou "Modalidade").  <br/> |
   

