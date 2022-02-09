---
title: Tabela MonitoredUserSiteLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 7c9e924092b687abe6fefe579109e943fd7c71ca
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399525"
---
# <a name="monitoredusersitelink-table"></a>Tabela MonitoredUserSiteLink
 
MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois locais de usuários.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primário, externo  <br/> |Referenciado na tabela [UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primário, externo  <br/> |Referência da [tabela UserSite](usersite.md).  <br/> |
   

