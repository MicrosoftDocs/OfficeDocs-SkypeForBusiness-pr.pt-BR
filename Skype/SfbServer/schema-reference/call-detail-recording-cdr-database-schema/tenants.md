---
title: Tabela Tenants
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: A tabela de Inquilinos é uma tabela de suporte que armazena uma lista dos vários locatários. Cada registro na tabela representa um inquilino.
ms.openlocfilehash: 4dde1baaf553c1a0d8a0efe65d72e8326cbb3bad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tenants-table"></a>Tabela Tenants
 
A tabela de Inquilinos é uma tabela de suporte que armazena uma lista dos vários locatários. Cada registro na tabela representa um inquilino.
  
> [!NOTE]
> Na implantação no local, o CDR usa a ID do inquilino integrado para indicar o tipo de autenticação diferente, como conectividade de IM pública, federada e anônima. 
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o ID desse inquilino.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-000000000000-Enterprise <br/>  00000000-0000-0000-0000-000000000001-federado <br/>  00000000-0000-0000-0000-000000000002 - anônima <br/>  00000000-0000-0000-0000-000000000003-conectividade de IM pública <br/> |
   

