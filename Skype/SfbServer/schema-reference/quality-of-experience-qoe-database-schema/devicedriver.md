---
title: Tabela DeviceDriver
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: A tabela DeviceDriver é uma tabela de suporte. Cada registro representa um driver usado por um dispositivo de captura ou dispositivo de renderização.
ms.openlocfilehash: 49bf941de3c0639552bd01e5066c9b823953ca7d4c01acc1b77a973045d89985
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276566"
---
# <a name="devicedriver-table"></a>Tabela DeviceDriver
 
A tabela DeviceDriver é uma tabela de suporte. Cada registro representa um driver usado por um dispositivo de captura ou dispositivo de renderização.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse registro de driver de dispositivo.  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |Nome do driver do dispositivo.  <br/> |
   

