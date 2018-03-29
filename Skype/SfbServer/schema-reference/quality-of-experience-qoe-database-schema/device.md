---
title: Tabela Device
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: A tabela de dispositivo é uma tabela de suporte que armazena informações sobre a captura de vários ou dispositivos de renderização. Cada registro na tabela representa um dispositivo.
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a>Tabela Device
 
A tabela de dispositivo é uma tabela de suporte que armazena informações sobre a captura de vários ou dispositivos de renderização. Cada registro na tabela representa um dispositivo.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este dispositivo.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType é exclusivo  <br/> |Nome do dispositivo.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType é exclusivo  <br/> |Tipo de dispositivo. 1 é um dispositivo de captura, 0 é um dispositivo de renderização.  <br/> |
   

