---
title: Exibição do usuário
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: A exibição de Usuário armazena informações sobre usuários envolvidos em chamadas ou sessões com registros no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 59b7371336ec900d6474016bb366407d4ffb7c14
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616377"
---
# <a name="user-view"></a>Exibição do usuário
 
A exibição de Usuário armazena informações sobre usuários envolvidos em chamadas ou sessões com registros no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Número exclusivo que identifica este usuário.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |Uri do usuário.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Locatário do usuário. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
   

