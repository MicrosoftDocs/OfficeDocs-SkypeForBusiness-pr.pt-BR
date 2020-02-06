---
title: Tabela UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela de usersite é uma tabela de suporte. Cada registro representa um site de usuário definido na configuração de rede.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804999"
---
# <a name="usersite-table"></a>Tabela UserSite
 
A tabela de usersite é uma tabela de suporte. Cada registro representa um site de usuário definido na configuração de rede.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o site do usuário.  <br/> |
|**Usersitename** <br/> |nvarchar(128  <br/> |Exclusividade  <br/> |Nome do site do usuário.  <br/> |
|**RegionKey** <br/> |int  <br/> |Exterior  <br/> |Referenciado da [tabela Region](region.md).  <br/> |
   

