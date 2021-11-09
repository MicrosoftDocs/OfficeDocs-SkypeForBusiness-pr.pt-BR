---
title: Tabela de diálogo
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: A tabela da Caixa de Diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo SIP.
ms.openlocfilehash: ab466a158ca059ff3110012a03e5c9c1e39b3d2d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851785"
---
# <a name="dialog-table"></a>Tabela de diálogo
 
A tabela da Caixa de Diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo SIP.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Horário em que o agente de QoE (Qualidade de Excelência) recebe o primeiro relatório do chamador ou receptor. Usado em conjunto com SessionSeq para identificar exclusivamente uma sessão.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |Número de sequência para diferenciar sessões quando tiverem o mesmo ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||ID da caixa de diálogo que é globalmente exclusiva.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Soma de verificação da ID da Caixa de Diálogo.  <br/> |
   

