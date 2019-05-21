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
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela de usersite é uma tabela de suporte. Cada registro representa um site de usuário definido na configuração de rede.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294569"
---
# <a name="usersite-table"></a>Tabela UserSite
 
A tabela de usersite é uma tabela de suporte. Cada registro representa um site de usuário definido na configuração de rede.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o site do usuário.  <br/> |
|**Usersitename** <br/> |nvarchar(128  <br/> |Exclusividade  <br/> |Nome do site do usuário.  <br/> |
|**RegionKey** <br/> |int  <br/> |Exterior  <br/> |Referenciado da [tabela Region](region.md).  <br/> |
   

