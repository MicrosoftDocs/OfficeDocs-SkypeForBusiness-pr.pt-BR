---
title: Tabela MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois locais de usuários.
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806351"
---
# <a name="monitoredusersitelink-table"></a>Tabela MonitoredUserSiteLink
 
MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois locais de usuários.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primário, externo  <br/> |Referenciado na tabela [UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primário, externo  <br/> |Referência da [tabela UserSite](usersite.md).  <br/> |
   

