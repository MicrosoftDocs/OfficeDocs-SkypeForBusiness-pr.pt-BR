---
title: Tabela MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: A tabela MonitoredRegionLink é uma tabela de suporte. Cada registro representa um vínculo entre dois países/regiões.
ms.openlocfilehash: 991cc3b6ce2f442ad13c350d2e37cc7c9d592d40d16da51932975a4907040569
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321623"
---
# <a name="monitoredregionlink-table"></a>Tabela MonitoredRegionLink
 
A tabela MonitoredRegionLink é uma tabela de suporte. Cada registro representa um vínculo entre dois países/regiões.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primário, externo  <br/> |Referenciado na tabela [Região](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primário, externo  <br/> |Referenciado na tabela [Região](region.md).  <br/> |
   

