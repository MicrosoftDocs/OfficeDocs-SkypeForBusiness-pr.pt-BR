---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações de estado de conformidade de todo o pool.
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899289"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contém informações de estado de conformidade de todo o pool.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, não nulo  <br/> |ID do evento mais recente de conformidade processado.  <br/> |
|activeServerID  <br/> |int, não nulo  <br/> |ID do servidor de conformidade, mantendo o bloqueio exclusivo no banco de dados, ou -1 se nenhum.  <br/> |
|lockExpirationTime  <br/> |datetime2, não nulo  <br/> |Tempo de expiração de bloqueio (se activeServerID não for -1).  <br/> |
   

