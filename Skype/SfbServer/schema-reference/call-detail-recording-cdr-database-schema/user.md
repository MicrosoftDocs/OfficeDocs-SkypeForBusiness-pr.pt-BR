---
title: Exibição do usuário
ms.reviewer: ''
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: A exibição de Usuário armazena informações sobre usuários envolvidos em chamadas ou sessões com registros no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 448577f4379bc4db690569333c6d912f777e408e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404503"
---
# <a name="user-view"></a>Exibição do usuário
 
A exibição de Usuário armazena informações sobre usuários envolvidos em chamadas ou sessões com registros no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Número exclusivo que identifica este usuário.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |Uri do usuário.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Locatário do usuário. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
   

