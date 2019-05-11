---
title: Tabela UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido na definição de configuração de rede.
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906950"
---
# <a name="usersite-table"></a>Tabela UserSite
 
A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido na definição de configuração de rede.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o site de usuário.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Exclusivo  <br/> |Nome do site do usuário.  <br/> |
|**RegionKey** <br/> |int  <br/> |Externa  <br/> |Citada em [Region table](region.md).  <br/> |
   

