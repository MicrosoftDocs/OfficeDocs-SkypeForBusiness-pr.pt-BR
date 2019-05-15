---
title: Tabela Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: A tabela de ponto de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
ms.openlocfilehash: 4917b0817d8fcedbc3a20b2c41d3ed62ce468c5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920107"
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
   

