---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.
ms.openlocfilehash: ad3b2543e2715462b953c611c8b5f24ea7885a6cb910931aa5b832b8196856eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351940"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, não nulo  <br/> |Data de expiração de bloqueio. O proprietário pode estender esse valor periodicamente.  <br/> |
|lockServerID  <br/> |int, não nulo  <br/> |Identificação do servidor que possui o bloqueio.  <br/> |
|lockActorID  <br/> |int, não nulo  <br/> |Identificação da entidade que possui o bloqueio.  <br/> |
   

