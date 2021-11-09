---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 130ca3cc7f57435f95add202f6af13660bf71610
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842603"
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
   

