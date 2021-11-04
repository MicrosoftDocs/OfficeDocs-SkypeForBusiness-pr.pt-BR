---
title: Tabela UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido nas configurações de rede.
ms.openlocfilehash: d8e7ccea49d00355a3e114833518cf5e6f762674
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737477"
---
# <a name="usersite-table"></a>Tabela UserSite
 
A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido nas configurações de rede.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primário  <br/> |Número único de identificação do site de usuário.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Unique  <br/> |Nome do site do usuário.  <br/> |
|**RegionKey** <br/> |int  <br/> |Foreign  <br/> |Referenciado na [tabela Região.](region.md)  <br/> |
   

