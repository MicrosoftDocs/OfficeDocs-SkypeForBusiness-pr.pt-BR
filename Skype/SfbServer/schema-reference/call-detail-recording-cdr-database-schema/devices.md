---
title: Tabela Devices no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: A tabela Devices é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831811"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabela Devices no Skype for Business Server 2015
 
A tabela Devices é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esta versão de hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Externo  <br/> |Fabricante deste dispositivo. Consulte a [tabela Manufacturers no Skype for Business Server 2015](manufacturers.md) para obter mais informações. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Externo  <br/> |Versão de hardware deste dispositivo. Consulte a [tabela HardwareVersions no Skype for Business Server 2015](hardwareversions.md) para obter mais informações. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Endereço MAC  <br/> |
   

