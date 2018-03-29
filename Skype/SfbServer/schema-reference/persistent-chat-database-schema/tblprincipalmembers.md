---
title: tblPrincipalMembers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contém associações de entidade.
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers contém associações de entidade.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|memberADPath  <br/> |nvarchar (384), não nulo  <br/> |Nome distinto do membro. Membro não precisam ser uma entidade de segurança (na tabela tblPrincipal).  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa em Tblprincipal.  <br/> |
   

