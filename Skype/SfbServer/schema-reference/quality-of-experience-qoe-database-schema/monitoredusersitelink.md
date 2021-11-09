---
title: Tabela MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois locais de usuários.
ms.openlocfilehash: 83278162f5e2a499bd68b874ca9eb961c09cf3d3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829755"
---
# <a name="monitoredusersitelink-table"></a>Tabela MonitoredUserSiteLink
 
MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois locais de usuários.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primário, externo  <br/> |Referenciado na tabela [UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primário, externo  <br/> |Referência da tabela [UserSite](usersite.md).  <br/> |
   

