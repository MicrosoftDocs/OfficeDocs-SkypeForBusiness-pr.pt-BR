---
title: Tabela UserAgent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um agente do usuário
ms.openlocfilehash: 5b9bcc35fbad3d20a006410aeb3538b6f5daa77e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-table"></a>Tabela UserAgent
 
A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um agente do usuário
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse agente de usuário.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Exclusivo  <br/> |Cadeia de caracteres de agente do usuário.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 é o servidor de mediação.  <br/> 2 é A / V Conferencing Server.  <br/> 4 é Skype para negócios.  <br/> 8 é telefone IP.  <br/> 16 é o Console do Live Meeting.  <br/> 32 é a Deployment Validation Tool (DVT).  <br/> 64 é Skype para Business Server em computadores Macintosh.  <br/> 128 é Skype para Business Server Attendant.  <br/> 256 é o serviço de anúncio de conferência.  <br/> 512 é atendedor automático de conferência.  <br/> 1024 é o aplicativo grupo de resposta.  <br/> 2048 é o controle de voz externo.  <br/> |
   

