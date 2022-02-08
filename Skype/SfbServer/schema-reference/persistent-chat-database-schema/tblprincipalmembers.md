---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contém associações principais.
ms.openlocfilehash: 77377a98e7dcf336eb05deb68c170de0c58a1223
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389049"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers contém associações principais.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|memberADPath  <br/> |nvarchar (384), não nulo  <br/> |Nome diferenciado de um membro. Um membro não precisa ser uma entidade principal (na tabela tblPrincipal).  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com lookup em tblPrincipal.prinID.  <br/> |
   

