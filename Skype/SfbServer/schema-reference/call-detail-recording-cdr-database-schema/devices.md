---
title: Tabela de dispositivos no Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: A tabela de dispositivos é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabela de dispositivos no Skype para Business Server 2015
 
A tabela de dispositivos é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo identificando esta versão de hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Externa  <br/> |Fabricante do dispositivo. Consulte a [tabela de fabricantes no Skype para Business Server 2015](manufacturers.md) para obter mais informações. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Externa  <br/> |Versão de hardware do dispositivo. Consulte a [tabela HardwareVersions no Skype para Business Server 2015](hardwareversions.md) para obter mais informações. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Endereço MAC  <br/> |
   

