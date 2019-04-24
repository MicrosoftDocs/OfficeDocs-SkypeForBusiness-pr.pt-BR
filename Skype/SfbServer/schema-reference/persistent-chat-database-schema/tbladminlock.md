---
title: tblAdminLock
ms.reviewer: ''
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
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212660"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, não nulo  <br/> |Bloquear a expiração de data e hora. O proprietário pode estender esse valor periodicamente.  <br/> |
|lockServerID  <br/> |int, não nulo  <br/> |ID do servidor que possui o bloqueio.  <br/> |
|lockActorID  <br/> |int, não nulo  <br/> |ID da entidade que possui o bloqueio.  <br/> |
   

