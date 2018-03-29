---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, não nulo  <br/> |Bloquear a expiração de data e hora. O proprietário pode estender esse valor periodicamente.  <br/> |
|lockServerID  <br/> |int, não nulo  <br/> |ID do servidor que possui o bloqueio.  <br/> |
|lockActorID  <br/> |int, não nulo  <br/> |ID da entidade que possui o bloqueio.  <br/> |
   

