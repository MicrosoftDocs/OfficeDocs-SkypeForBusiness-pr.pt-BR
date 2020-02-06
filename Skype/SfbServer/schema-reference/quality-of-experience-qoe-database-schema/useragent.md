---
title: Tabela UserAgent
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
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que participaram de sessões registradas no banco de dados. Cada registro na tabela representa um agente do usuário
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805049"
---
# <a name="useragent-table"></a>Tabela UserAgent
 
A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que participaram de sessões registradas no banco de dados. Cada registro na tabela representa um agente do usuário
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse agente de usuário.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Exclusividade  <br/> |Cadeia de caracteres do agente do usuário.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 é o servidor de mediação.  <br/> 2 é um servidor de conferência A/V.  <br/> 4 é o Skype for Business.  <br/> 8 é o telefone IP.  <br/> 16 é o console do Live Meeting.  <br/> o 32 é uma ferramenta de validação de implantação (DVT).  <br/> o 64 é o Skype for Business Server em computadores Macintosh.  <br/> o 128 é o Skype for Business Server Attendant.  <br/> o 256 é o serviço de anúncio de conferências.  <br/> o 512 é o atendedor automático da conferência.  <br/> o 1024 é um aplicativo de grupo de resposta.  <br/> 2048 está fora do controle de voz.  <br/> |
   

