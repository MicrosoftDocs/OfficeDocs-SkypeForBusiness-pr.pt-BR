---
title: Tabela Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: A tabela de conferências é uma tabela de suporte. Cada registro representa uma reunião ou sessão ponto a ponto.
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295010"
---
# <a name="conference-table"></a>Tabela Conference
 
A tabela de conferências é uma tabela de suporte. Cada registro representa uma reunião ou sessão ponto a ponto.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse registro de conferência.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |exclusividade  <br/> |URL da conferência se for uma conferência ou caixa de diálogo se for uma sessão ponto a ponto.  <br/> |
|**Prova** <br/> |int  <br/> |dedo  <br/> |Checksum do URI da conferência. Isso é usado internamente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Somente para uso interno.  <br/> |
   

