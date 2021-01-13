---
title: Tabela UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido nas configurações de rede.
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799911"
---
# <a name="usersite-table"></a>Tabela UserSite
 
A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido nas configurações de rede.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primário  <br/> |Número único de identificação do site de usuário.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Exclusivo  <br/> |Nome do site do usuário.  <br/> |
|**RegionKey** <br/> |int  <br/> |Externo  <br/> |Referenciado da [tabela Região](region.md).  <br/> |
   

