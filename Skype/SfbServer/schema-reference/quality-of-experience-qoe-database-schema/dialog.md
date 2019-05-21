---
title: Tabela Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: A tabela de caixa de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo SIP (protocolo de início de sessão).
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294954"
---
# <a name="dialog-table"></a>Tabela Dialog
 
A tabela de caixa de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo SIP (protocolo de início de sessão).
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Tempo quando o agente de Quality of Excellence (QoE) recebe o primeiro relatório do chamador ou do receptor. Usado em conjunto com o SessionSeq para identificar exclusivamente uma sessão.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Número de sequência para diferenciar sessões quando elas tiverem o mesmo ConferenceDateTime.  <br/> |
|**Caixa de diálogo** <br/> |varchar (256)  <br/> ||IDENTIFICAÇÃO da caixa de diálogo que é globalmente exclusiva.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |dedo  <br/> |Checksum da ID da caixa de diálogo.  <br/> |
   

