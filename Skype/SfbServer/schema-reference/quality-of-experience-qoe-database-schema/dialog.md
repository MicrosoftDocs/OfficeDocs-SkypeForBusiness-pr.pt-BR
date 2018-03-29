---
title: Tabela Dialog
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: A tabela de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo de iniciação de sessão (SIP).
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a>Tabela Dialog
 
A tabela de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo de iniciação de sessão (SIP).
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Hora de quando o agente de qualidade de excelência (QoE) recebe o primeiro relatório do chamador ou o receptor. Usado em conjunto com SessionSeq para identificar exclusivamente uma sessão.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Número de sequência para diferenciar sessões quando tiverem o mesmo ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||ID de diálogo que é globalmente exclusiva.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |índice  <br/> |Soma de verificação da ID do diálogo.  <br/> |
   

