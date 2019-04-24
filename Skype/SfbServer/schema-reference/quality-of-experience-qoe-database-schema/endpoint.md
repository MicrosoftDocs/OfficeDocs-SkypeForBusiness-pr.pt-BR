---
title: Tabela Endpoint
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: A tabela de ponto de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212239"
---
# <a name="endpoint-table"></a>Tabela Endpoint
 
A tabela de ponto de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este ponto de extremidade.  <br/> |
|**Nome** <br/> |nvarchar(256)  <br/> |Exclusivo  <br/> |Nome do ponto de extremidade.  <br/> |
|**Sistema operacional** <br/> |nvarchar (128)  <br/> | <br/> |Sistema operacional (SO) do ponto de extremidade.  <br/> |
|**CPUName** <br/> |nvarchar (128)  <br/> ||Nome da CPU do ponto de extremidade.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Número de núcleos de CPU do ponto de extremidade.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Velocidade do processador da CPU do ponto de extremidade.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Sinalizador de bit que indica se o sistema está sendo executado em um ambiente virtualizado: <br/>  0x0000 - nenhum <br/>  0x0001 - Hyper-v <br/>  0x0002 - VMWare <br/>  0x0004 - virtual PC <br/>  0x0008 - Xen PC <br/> |
   

