---
title: Tabela tenants
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: A tabela Tenants é uma tabela de suporte que armazena uma lista de vários locatários. Cada registro na tabela representa um locatário.
---

# <a name="tenants-table"></a>Tabela tenants
 
A tabela Tenants é uma tabela de suporte que armazena uma lista de vários locatários. Cada registro na tabela representa um locatário.
  
> [!NOTE]
> Na implantação no local, o CDR usa o ID de Inquilino integrado para indicar um tipo de autenticação diferente, como conectividade de IM pública, Federada e Anônima. 
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o ID desse inquilino.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-0000000000000000 - Enterprise <br/>  00000000-0000-0000-0000-00000000000001 - Federado <br/>  00000000-0000-0000-0000-0000000000002 - Anônimo <br/>  00000000-0000-0000-0000-0000000000000 - Conectividade de IM Pública <br/> |
   

