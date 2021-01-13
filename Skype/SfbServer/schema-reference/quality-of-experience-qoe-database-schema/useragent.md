---
title: Tabela UserAgent
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
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: A tabela UserAgent é uma tabela de suporte que armazena uma lista dos vários agentes do usuário que participaram de sessões gravadas no banco de dados. Cada registro na tabela representa um agente do usuário
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799926"
---
# <a name="useragent-table"></a>Tabela UserAgent
 
A tabela UserAgent é uma tabela de suporte que armazena uma lista dos vários agentes do usuário que participaram de sessões gravadas no banco de dados. Cada registro na tabela representa um agente do usuário
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse agente do usuário.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Exclusivo  <br/> |Cadeia de caracteres do Agente do Usuário.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 é o Servidor de Mediação.  <br/> 2 é Servidor de Conferência A/V.  <br/> 4 é o Skype for Business.  <br/> 8 é o Telefone IP.  <br/> 16 é o Live Meeting Console.  <br/> 32 é a Ferramenta de Validação de Implantação (DVT).  <br/> 64 é Skype for Business Server em computadores Macintosh.  <br/> 128 é o Skype for Business Server Attendant.  <br/> 256 é o serviço de Comunicado de Conferência.  <br/> 512 é o Atendente Automático de Conferência.  <br/> 1024 é o aplicativo grupo de resposta.  <br/> 2048 é Outside Voice Control.  <br/> |
   

