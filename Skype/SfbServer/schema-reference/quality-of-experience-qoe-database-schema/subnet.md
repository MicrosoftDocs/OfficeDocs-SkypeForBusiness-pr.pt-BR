---
title: Tabela sub-rede
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
ms.localizationpriority: medium
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: A tabela Subnet é uma tabela de suporte. Cada registro representa uma subrede definida em uma configuração de rede.
ms.openlocfilehash: e7fd43963414b24ed684d8f1efa59c7e634839bd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613791"
---
# <a name="subnet-table"></a>Tabela sub-rede
 
A tabela Subnet é uma tabela de suporte. Cada registro representa uma subrede definida em uma configuração de rede.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primária, estrangeira  <br/> |Representação de inteiro para o IP da sub-rede.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Máscara de sub-rede.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |Referenciado na tabela [UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||A descrição para a sub-rede.  <br/> |
   

