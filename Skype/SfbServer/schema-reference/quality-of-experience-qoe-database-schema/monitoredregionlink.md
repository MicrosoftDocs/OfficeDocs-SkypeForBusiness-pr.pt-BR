---
title: Tabela MonitoredRegionLink
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: A tabela MonitoredRegionLink é uma tabela de suporte. Cada registro representa um vínculo entre dois países/regiões.
ms.openlocfilehash: 0efac1d496889645ffb52db5c419397337ebf9f2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858098"
---
# <a name="monitoredregionlink-table"></a>Tabela MonitoredRegionLink
 
A tabela MonitoredRegionLink é uma tabela de suporte. Cada registro representa um vínculo entre dois países/regiões.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primário, externo  <br/> |Referenciado na tabela [Região](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primário, externo  <br/> |Referenciado na tabela [Região](region.md).  <br/> |
   

