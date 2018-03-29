---
title: Tabela MonitoredUserSiteLink
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um vínculo entre dois sites do usuário.
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a>Tabela MonitoredUserSiteLink
 
A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um vínculo entre dois sites do usuário.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primária, estrangeira  <br/> |Referenciado de [UserSite table](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primária, estrangeira  <br/> |Referência de [UserSite table](usersite.md).  <br/> |
   

