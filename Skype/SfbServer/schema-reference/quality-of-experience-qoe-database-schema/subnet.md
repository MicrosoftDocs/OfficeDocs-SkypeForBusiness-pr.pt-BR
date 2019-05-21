---
title: Tabela Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de rede.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294632"
---
# <a name="subnet-table"></a>Tabela Subnet
 
A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de rede.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Representação do inteiro para o IP da sub-rede.  <br/> |
|**Máscara_de_Sub-rede** <br/> |int  <br/> ||Máscara de sub-rede.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Exterior  <br/> |Referenciado da [tabela usersite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||A descrição da sub-rede.  <br/> |
   

