---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações sobre o estado de conformidade de todo o pool.
ms.openlocfilehash: 627632625e5898557d650009974fe709ff00e35d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398635"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contém informações sobre o estado de conformidade de todo o pool.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, não nulo  <br/> |ID do último evento de conformidade processado.  <br/> |
|activeServerID  <br/> |int, não nulo  <br/> |ID do servidor de conformidade que possui o bloqueio exclusivo no banco de dados, ou -1 se nenhum.  <br/> |
|lockExpirationTime  <br/> |datetime2, não nulo  <br/> |Hora de expiração do bloqueio (se activeServerID não for igual a -1).  <br/> |
   

