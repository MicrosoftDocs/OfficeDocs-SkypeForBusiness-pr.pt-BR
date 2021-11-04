---
title: Tabela Dispositivos no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: A tabela Devices é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
ms.openlocfilehash: c7662663625937a0ad0c7cc023620798f0398e49
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743967"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabela Dispositivos no Skype for Business Server 2015
 
A tabela Devices é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica essa versão de hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Foreign  <br/> |Fabricante deste dispositivo. Consulte a [tabela Fabricantes no Skype for Business Server 2015](manufacturers.md) para obter mais informações. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Foreign  <br/> |Versão de hardware deste dispositivo. Consulte a [tabela HardwareVersions no Skype for Business Server 2015](hardwareversions.md) para obter mais informações. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Endereço MAC  <br/> |
   

