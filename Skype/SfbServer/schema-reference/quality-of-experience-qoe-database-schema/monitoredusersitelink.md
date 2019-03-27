---
title: Tabela MonitoredUserSiteLink
ms.reviewer: ''
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
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874256"
---
# <a name="monitoredusersitelink-table"></a>Tabela MonitoredUserSiteLink
 
A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um vínculo entre dois sites do usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primária, estrangeira  <br/> |Referenciado de [UserSite table](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primária, estrangeira  <br/> |Referência de [UserSite table](usersite.md).  <br/> |
   

