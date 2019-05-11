---
title: Tabela Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de configuração de rede.
ms.openlocfilehash: f659d73bbdd654365697a9f853fbb48162e1bba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907063"
---
# <a name="subnet-table"></a>Tabela Subnet
 
A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de configuração de rede.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primária, estrangeira  <br/> |Representação de inteiro para o IP da sub-rede.  <br/> |
|**Máscara de sub-rede** <br/> |int  <br/> ||Máscara de sub-rede.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Externa  <br/> |Referenciado de [UserSite table](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||A descrição para a sub-rede.  <br/> |
   

