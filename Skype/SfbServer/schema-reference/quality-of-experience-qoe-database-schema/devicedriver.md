---
title: Tabela DeviceDriver
ms.reviewer: null
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: A tabela DeviceDriver é uma tabela de suporte. Cada registro representa um driver usado por um dispositivo de captura ou dispositivo de renderização.
---

# <a name="devicedriver-table"></a>Tabela DeviceDriver
 
A tabela DeviceDriver é uma tabela de suporte. Cada registro representa um driver usado por um dispositivo de captura ou dispositivo de renderização.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse registro de driver de dispositivo.  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |Nome do driver do dispositivo.  <br/> |
   

