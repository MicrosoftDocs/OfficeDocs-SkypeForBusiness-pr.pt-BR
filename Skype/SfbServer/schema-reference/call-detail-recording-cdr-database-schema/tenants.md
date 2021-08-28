---
title: Tabela tenants
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 2705b44830efef4a8f921bf9ccc9c7b8e49f72ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583785"
---
# <a name="tenants-table"></a>Tabela tenants
 
A tabela Tenants é uma tabela de suporte que armazena uma lista de vários locatários. Cada registro na tabela representa um locatário.
  
> [!NOTE]
> Na implantação no local, o CDR usa o ID de Inquilino integrado para indicar um tipo de autenticação diferente, como conectividade de IM pública, Federada e Anônima. 
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o ID desse inquilino.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-0000000000000000 - Enterprise <br/>  00000000-0000-0000-0000-00000000000001 - Federado <br/>  00000000-0000-0000-0000-0000000000002 - Anônimo <br/>  00000000-0000-0000-0000-0000000000000 - Conectividade de IM Pública <br/> |
   

