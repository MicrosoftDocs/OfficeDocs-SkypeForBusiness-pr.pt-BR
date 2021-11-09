---
title: Tabela sub-rede
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: A tabela Subnet é uma tabela de suporte. Cada registro representa uma subrede definida em uma configuração de rede.
ms.openlocfilehash: abbc1317c6a0db1da0b52e5b0eef56abbfad06f5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834839"
---
# <a name="subnet-table"></a>Tabela sub-rede
 
A tabela Subnet é uma tabela de suporte. Cada registro representa uma subrede definida em uma configuração de rede.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primária, estrangeira  <br/> |Representação de inteiro para o IP da sub-rede.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Máscara de sub-rede.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |Referenciado na tabela [UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||A descrição para a sub-rede.  <br/> |
   

