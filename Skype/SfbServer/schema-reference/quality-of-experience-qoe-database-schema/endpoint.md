---
title: Tabela de ponto de extremidade
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: A tabela Ponto de Extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram de sessões gravadas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
ms.openlocfilehash: 40c5ee0962059644db998fe7706fe53e212564c2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741837"
---
# <a name="endpoint-table"></a>Tabela de ponto de extremidade
 
A tabela Ponto de Extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram de sessões gravadas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse ponto de extremidade.  <br/> |
|**Nome** <br/> |nvarchar(256)  <br/> |Unique  <br/> |Nome do ponto de extremidade.  <br/> |
|**SISTEMA OPERACIONAL** <br/> |nvarchar(128)  <br/> | <br/> |Sistema operacional (OS) do ponto de extremidade.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Nome da CPU do ponto de extremidade.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Número de núcleos de CPU do ponto de extremidade.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Velocidade do processador da CPU do ponto de extremidade.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Sinalizador de bits que indica se o sistema está em execução em um ambiente virtualizado: <br/>  0x0000 - Nenhum <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - Computador Virtual <br/>  0x0008 - Xen PC <br/> |
   

