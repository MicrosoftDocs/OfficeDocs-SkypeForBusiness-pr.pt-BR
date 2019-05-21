---
title: Tabela MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois sites de usuário.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294849"
---
# <a name="monitoredusersitelink-table"></a>Tabela MonitoredUserSiteLink
 
A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois sites de usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Referenciado da [tabela usersite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Referência a partir da [tabela](usersite.md)do usersite.  <br/> |
   

