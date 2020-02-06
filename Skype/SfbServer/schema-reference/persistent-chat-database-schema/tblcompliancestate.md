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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações de estado de conformidade em todo o pool.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814629"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contém informações de estado de conformidade em todo o pool.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, e não nulo  <br/> |ID do evento de conformidade processado mais recente.  <br/> |
|activeServerID  <br/> |int, não nulo  <br/> |ID do servidor de conformidade que mantém o bloqueio exclusivo no banco de dados ou-1 se nenhum.  <br/> |
|lockExpirationTime  <br/> |datetime2, não nulo  <br/> |Bloquear o tempo de expiração (se activeServerID não for-1).  <br/> |
   

