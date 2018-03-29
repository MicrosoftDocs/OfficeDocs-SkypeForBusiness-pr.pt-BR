---
title: tblComplianceState
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
ms.openlocfilehash: e46db9c73f4489ade9bbed90f0061567fd14af1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contém informações de estado de conformidade de todo o pool.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, não nulo  <br/> |ID do evento mais recente de conformidade processado.  <br/> |
|activeServerID  <br/> |int, não nulo  <br/> |ID do servidor de conformidade, mantendo o bloqueio exclusivo no banco de dados, ou -1 se nenhum.  <br/> |
|lockExpirationTime  <br/> |datetime2, não nulo  <br/> |Tempo de expiração de bloqueio (se activeServerID não for -1).  <br/> |
   

