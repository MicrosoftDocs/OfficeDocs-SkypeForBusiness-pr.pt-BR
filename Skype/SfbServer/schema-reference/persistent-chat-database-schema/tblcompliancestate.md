---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações sobre o estado de conformidade de todo o pool.
ms.openlocfilehash: c9027068550b4320e1e7d170ee23b6cb6e060d6162583132f927c720c09d6ebe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315417"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contém informações sobre o estado de conformidade de todo o pool.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, não nulo  <br/> |ID do último evento de conformidade processado.  <br/> |
|activeServerID  <br/> |int, não nulo  <br/> |ID do servidor de conformidade que possui o bloqueio exclusivo no banco de dados, ou -1 se nenhum.  <br/> |
|lockExpirationTime  <br/> |datetime2, não nulo  <br/> |Hora de expiração do bloqueio (se activeServerID não for igual a -1).  <br/> |
   

