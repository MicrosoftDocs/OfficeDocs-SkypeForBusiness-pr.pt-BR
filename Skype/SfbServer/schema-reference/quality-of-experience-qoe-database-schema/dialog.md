---
title: Tabela Dialog
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
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: A tabela da Caixa de Diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo SIP.
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815841"
---
# <a name="dialog-table"></a>Tabela Dialog
 
A tabela da Caixa de Diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo SIP.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Horário em que o agente de QoE (Qualidade de Excelência) recebe o primeiro relatório do chamador ou receptor. Usado em conjunto com SessionSeq para identificar exclusivamente uma sessão.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |Número de sequência para diferenciar sessões quando tiverem o mesmo ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||ID da caixa de diálogo que é globalmente exclusiva.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Soma de verificação da ID da Caixa de Diálogo.  <br/> |
   

