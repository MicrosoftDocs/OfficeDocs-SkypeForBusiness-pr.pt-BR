---
title: Tabela de dispositivos
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: A tabela Device é uma tabela de suporte que armazena informações sobre os vários dispositivos de captura ou renderização. Cada registro na tabela representa um dispositivo.
ms.openlocfilehash: 71a92ab0f73e844b4b58110dbb8c59650a26873a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763129"
---
# <a name="device-table"></a>Tabela de dispositivos
 
A tabela Device é uma tabela de suporte que armazena informações sobre os vários dispositivos de captura ou renderização. Cada registro na tabela representa um dispositivo.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica este dispositivo.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType é exclusivo  <br/> |Nome do dispositivo.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType é exclusivo  <br/> |Tipo de dispositivo. 1 é um dispositivo de captura, 0 é um dispositivo de processamento.  <br/> |
   

