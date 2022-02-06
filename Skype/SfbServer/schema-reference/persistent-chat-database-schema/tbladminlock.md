---
title: tblAdminLock
ms.reviewer: null
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.
---

# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, não nulo  <br/> |Data de expiração de bloqueio. O proprietário pode estender esse valor periodicamente.  <br/> |
|lockServerID  <br/> |int, não nulo  <br/> |Identificação do servidor que possui o bloqueio.  <br/> |
|lockActorID  <br/> |int, não nulo  <br/> |Identificação da entidade que possui o bloqueio.  <br/> |
   

