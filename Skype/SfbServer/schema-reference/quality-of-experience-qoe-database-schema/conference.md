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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: A tabela de conferências é uma tabela de suporte. Cada registro representa uma reunião ou sessão ponto a ponto.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810299"
---
# <a name="conference-table"></a>Tabela Conference
 
A tabela de conferências é uma tabela de suporte. Cada registro representa uma reunião ou sessão ponto a ponto.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse registro de conferência.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |exclusividade  <br/> |URL da conferência se for uma conferência ou caixa de diálogo se for uma sessão ponto a ponto.  <br/> |
|**Prova** <br/> |int  <br/> |dedo  <br/> |Checksum do URI da conferência. Isso é usado internamente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Somente para uso interno.  <br/> |
   

