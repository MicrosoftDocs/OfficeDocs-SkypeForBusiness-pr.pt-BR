---
title: Tabela Subnet
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de configuração de rede.
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a>Tabela Subnet
 
A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de configuração de rede.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primária, estrangeira  <br/> |Representação de inteiro para o IP da sub-rede.  <br/> |
|**Máscara de sub-rede** <br/> |int  <br/> ||Máscara de sub-rede.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Externa  <br/> |Referenciado de [UserSite table](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||A descrição para a sub-rede.  <br/> |
   

