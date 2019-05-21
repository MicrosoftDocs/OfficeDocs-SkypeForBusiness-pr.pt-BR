---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contém o bloqueio do administrador necessário para executar alguns comandos de administrador.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295521"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contém o bloqueio do administrador necessário para executar alguns comandos de administrador.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, não nulo  <br/> |Bloquear data e hora de expiração. O proprietário pode estender esse valor periodicamente.  <br/> |
|lockServerID  <br/> |int, não nulo  <br/> |ID do servidor que é proprietário do bloqueio.  <br/> |
|lockActorID  <br/> |int, não nulo  <br/> |ID da entidade de segurança que é proprietária do bloqueio.  <br/> |
   

