---
title: Tabela UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido nas configurações de rede.
ms.openlocfilehash: 80286b04e408a8f80e63364e3c7a822ce8e63505
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851765"
---
# <a name="usersite-table"></a>Tabela UserSite
 
A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido nas configurações de rede.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primário  <br/> |Número único de identificação do site de usuário.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Unique  <br/> |Nome do site do usuário.  <br/> |
|**RegionKey** <br/> |int  <br/> |Foreign  <br/> |Referenciado na [tabela Região.](region.md)  <br/> |
   

