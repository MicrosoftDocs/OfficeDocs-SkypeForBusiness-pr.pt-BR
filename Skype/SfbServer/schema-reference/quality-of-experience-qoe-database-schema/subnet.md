---
title: Tabela Subnet
ms.reviewer: ''
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
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880473"
---
# <a name="subnet-table"></a>Tabela Subnet
 
A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de configuração de rede.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primária, estrangeira  <br/> |Representação de inteiro para o IP da sub-rede.  <br/> |
|**Máscara de sub-rede** <br/> |int  <br/> ||Máscara de sub-rede.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Externa  <br/> |Referenciado de [UserSite table](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||A descrição para a sub-rede.  <br/> |
   

