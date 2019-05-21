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
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que participaram de sessões registradas no banco de dados. Cada registro na tabela representa um agente do usuário
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294583"
---
# <a name="useragent-table"></a>Tabela UserAgent
 
A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que participaram de sessões registradas no banco de dados. Cada registro na tabela representa um agente do usuário
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse agente de usuário.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Exclusividade  <br/> |Cadeia de caracteres do agente do usuário.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 é o servidor de mediação.  <br/> 2 é um servidor de conferência A/V.  <br/> 4 é o Skype for Business.  <br/> 8 é o telefone IP.  <br/> 16 é o console do Live Meeting.  <br/> o 32 é uma ferramenta de validação de implantação (DVT).  <br/> o 64 é o Skype for Business Server em computadores Macintosh.  <br/> o 128 é o Skype for Business Server Attendant.  <br/> o 256 é o serviço de anúncio de conferências.  <br/> o 512 é o atendedor automático da conferência.  <br/> o 1024 é um aplicativo de grupo de resposta.  <br/> 2048 está fora do controle de voz.  <br/> |
   

