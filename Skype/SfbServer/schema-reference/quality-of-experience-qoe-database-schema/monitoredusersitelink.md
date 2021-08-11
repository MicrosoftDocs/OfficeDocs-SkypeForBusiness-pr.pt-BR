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
ms.openlocfilehash: 7c7edea00fdd680ece091d06aa7528fb0dc7fe25d5b5b4fa126c37c48b3ee81d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321603"
---
# <a name="monitoredusersitelink-table"></a>Tabela MonitoredUserSiteLink
 
MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois locais de usuários.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primário, externo  <br/> |Referenciado na tabela [UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primário, externo  <br/> |Referência da tabela [UserSite](usersite.md).  <br/> |
   

