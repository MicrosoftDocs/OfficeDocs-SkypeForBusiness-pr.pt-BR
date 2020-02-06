---
title: Tabela Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: A tabela de pontos de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram em sessões registradas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809549"
---
# <a name="endpoint-table"></a>Tabela Endpoint
 
A tabela de pontos de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram em sessões registradas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse ponto de extremidade.  <br/> |
|**Nome** <br/> |nvarchar(256)  <br/> |Exclusividade  <br/> |Nome do ponto de extremidade.  <br/> |
|**Sistema operacional** <br/> |nvarchar(128  <br/> | <br/> |Sistema operacional (SO) da empresa.  <br/> |
|**CPUName** <br/> |nvarchar(128  <br/> ||Nome da CPU do ponto de extremidade.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Número de núcleos da CPU da empresa.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Velocidade do processador da CPU do ponto de extremidade.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Sinalizador de bit que indica se o sistema está em execução em um ambiente virtualizado: <br/>  0x0000-nenhum <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-Virtual PC <br/>  PC 0x0008-Xen <br/> |
   

