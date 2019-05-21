---
title: Tabela AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma fonte.
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295108"
---
# <a name="appliedbandwidthsource-table"></a>Tabela AppliedBandwidthSource
 
A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma fonte.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica a fonte.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)  <br/> |Exclusividade  <br/> |Essa é a origem do limite de largura de banda que está sendo imposto. Ele descreve para onde o limite de largura de banda é proveniente (por exemplo, "servidor de políticas", "Ativar servidor" ou "modalidade").  <br/> |
   

