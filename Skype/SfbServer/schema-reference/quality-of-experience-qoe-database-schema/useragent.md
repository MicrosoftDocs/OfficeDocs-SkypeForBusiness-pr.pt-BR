---
title: Tabela UserAgent
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
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: A tabela UserAgent é uma tabela de suporte que armazena uma lista dos vários agentes de usuário que participaram de sessões gravadas no banco de dados. Cada registro na tabela representa um agente de usuário
ms.openlocfilehash: 7e870e9d63f3d1c9e199df36c5225af704388746
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771817"
---
# <a name="useragent-table"></a>Tabela UserAgent
 
A tabela UserAgent é uma tabela de suporte que armazena uma lista dos vários agentes de usuário que participaram de sessões gravadas no banco de dados. Cada registro na tabela representa um agente de usuário
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse agente do usuário.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Unique  <br/> |Cadeia de caracteres do Agente do Usuário.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 é o Servidor de Mediação.  <br/> 2 é Servidor de Conferência A/V.  <br/> 4 é Skype for Business.  <br/> 8 é ip Telefone.  <br/> 16 é Live Meeting Console.  <br/> 32 é a Ferramenta de Validação de Implantação (DVT).  <br/> 64 é Skype for Business Server computadores Macintosh.  <br/> 128 é Skype for Business Server Attendant.  <br/> 256 é Comunicado de Conferência serviço.  <br/> 512 é Conferência Atendedor Automático.  <br/> 1024 é o aplicativo grupo de resposta.  <br/> 2048 é Outside Voice Control.  <br/> |
   

