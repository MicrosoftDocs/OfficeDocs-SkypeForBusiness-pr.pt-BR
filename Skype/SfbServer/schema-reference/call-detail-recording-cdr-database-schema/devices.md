---
title: Tabela de dispositivos no Skype para Business Server 2015
ms.reviewer: ''
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
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881699"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabela de dispositivos no Skype para Business Server 2015
 
A tabela de dispositivos é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo identificando esta versão de hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Externa  <br/> |Fabricante do dispositivo. Consulte a [tabela de fabricantes no Skype para Business Server 2015](manufacturers.md) para obter mais informações. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Externa  <br/> |Versão de hardware do dispositivo. Consulte a [tabela HardwareVersions no Skype para Business Server 2015](hardwareversions.md) para obter mais informações. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Endereço MAC  <br/> |
   

