---
title: Tabela AppliedBandwidthSource
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma origem.
ms.openlocfilehash: c886c5179d40063c1325bea3167e06ae7fe37666
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411504"
---
# <a name="appliedbandwidthsource-table"></a>Tabela AppliedBandwidthSource
 
A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma origem.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica a origem.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Unique  <br/> |Essa é a origem do cap de largura de banda que está sendo imposto. Ele descreve de onde vem o limite de largura de banda (por exemplo, "Servidor de Política", "SERVIDOR TURN" ou "Modalidade").  <br/> |
   

