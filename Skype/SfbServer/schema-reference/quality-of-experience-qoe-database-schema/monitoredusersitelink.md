---
title: Tabela MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 3cc8c11f049e98223c80756eb2dc83f1b9354ec7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768359"
---
# <a name="monitoredusersitelink-table"></a>Tabela MonitoredUserSiteLink
 
MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois locais de usuários.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primário, externo  <br/> |Referenciado na tabela [UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primário, externo  <br/> |Referência da tabela [UserSite](usersite.md).  <br/> |
   

