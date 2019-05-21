---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações de estado de conformidade em todo o pool.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295472"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contém informações de estado de conformidade em todo o pool.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, e não nulo  <br/> |ID do evento de conformidade processado mais recente.  <br/> |
|activeServerID  <br/> |int, não nulo  <br/> |ID do servidor de conformidade que mantém o bloqueio exclusivo no banco de dados ou-1 se nenhum.  <br/> |
|lockExpirationTime  <br/> |datetime2, não nulo  <br/> |Bloquear o tempo de expiração (se activeServerID não for-1).  <br/> |
   

