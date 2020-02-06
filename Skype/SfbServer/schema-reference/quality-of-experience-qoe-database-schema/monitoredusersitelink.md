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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois sites de usuário.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807789"
---
# <a name="monitoredusersitelink-table"></a>Tabela MonitoredUserSiteLink
 
A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois sites de usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Referenciado da [tabela usersite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Referência a partir da [tabela do usersite](usersite.md).  <br/> |
   

