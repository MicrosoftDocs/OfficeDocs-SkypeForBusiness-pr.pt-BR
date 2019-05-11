---
title: Tabela Tenants
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: A tabela de Inquilinos é uma tabela de suporte que armazena uma lista dos vários locatários. Cada registro na tabela representa um inquilino.
ms.openlocfilehash: 68050ce76cc41d3fd66931fbdc0b0d3168786bc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930203"
---
# <a name="tenants-table"></a>Tabela Tenants
 
A tabela de Inquilinos é uma tabela de suporte que armazena uma lista dos vários locatários. Cada registro na tabela representa um inquilino.
  
> [!NOTE]
> Na implantação no local, o CDR usa a ID do inquilino integrado para indicar o tipo de autenticação diferente, como conectividade de IM pública, federada e anônima. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o ID desse inquilino.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-000000000000-Enterprise <br/>  00000000-0000-0000-0000-000000000001-federado <br/>  00000000-0000-0000-0000-000000000002 - anônima <br/>  00000000-0000-0000-0000-000000000003-conectividade de IM pública <br/> |
   

