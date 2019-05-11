---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações de estado de conformidade de todo o pool.
ms.openlocfilehash: 6f6b3891638fc3d769c0b0f4f4a42ca5f94a5a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929844"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contém informações de estado de conformidade de todo o pool.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, não nulo  <br/> |ID do evento mais recente de conformidade processado.  <br/> |
|activeServerID  <br/> |int, não nulo  <br/> |ID do servidor de conformidade, mantendo o bloqueio exclusivo no banco de dados, ou -1 se nenhum.  <br/> |
|lockExpirationTime  <br/> |datetime2, não nulo  <br/> |Tempo de expiração de bloqueio (se activeServerID não for -1).  <br/> |
   

