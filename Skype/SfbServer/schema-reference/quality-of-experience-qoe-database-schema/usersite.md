---
title: Tabela UserSite
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido na definição de configuração de rede.
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a>Tabela UserSite
 
A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido na definição de configuração de rede.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o site de usuário.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Exclusivo  <br/> |Nome do site do usuário.  <br/> |
|**RegionKey** <br/> |int  <br/> |Externa  <br/> |Citada em [Region table](region.md).  <br/> |
   

