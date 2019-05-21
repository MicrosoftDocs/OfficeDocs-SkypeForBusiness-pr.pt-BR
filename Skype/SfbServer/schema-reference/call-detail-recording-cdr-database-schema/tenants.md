---
title: Tabela Tenants
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: A tabela locatários é uma tabela de suporte que armazena uma lista de vários locatários. Cada registro na tabela representa um locatário.
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295766"
---
# <a name="tenants-table"></a>Tabela Tenants
 
A tabela locatários é uma tabela de suporte que armazena uma lista de vários locatários. Cada registro na tabela representa um locatário.
  
> [!NOTE]
> Na implantação local, o CDR usa a ID de locatário de compilação para indicar um tipo de autenticação diferente, como conectividade de mensagem de chat pública, federada e anônima. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Tenantid** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esta ID de locatário.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-000000000000-empresa <br/>  00000000-0000-0000-0000-000000000001-federado <br/>  00000000-0000-0000-0000-000000000002-anônimo <br/>  00000000-0000-0000-0000-000000000003-conectividade de IM pública <br/> |
   

