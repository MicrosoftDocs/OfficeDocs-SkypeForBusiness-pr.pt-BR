---
title: Tabela de conferências
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: A tabela de Conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.
ms.openlocfilehash: b5129fec73658d86fdb8d5cd7dd5c387cdadf4f9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763209"
---
# <a name="conference-table"></a>Tabela de conferências
 
A tabela de Conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o registro desta conferência.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |URI da conferência, se isso for uma conferência, ou DialogID se for uma sessão ponto a ponto.  <br/> |
|**Soma de verificação** <br/> |int  <br/> |index  <br/> |Soma de verificação do URI de conferência. Isso é usado internamente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Apenas para uso interno.  <br/> |
   

