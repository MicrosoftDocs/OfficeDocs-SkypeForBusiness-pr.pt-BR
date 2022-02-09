---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processadas pelas etapas posteriores de Sincronização de Serviços de Domínio do Active Directory.
ms.openlocfilehash: c52f1290eb0da442ffed9f8d8b645423b6f6c59c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410664"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processadas pelas etapas posteriores de Sincronização de Serviços de Domínio do Active Directory.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, não nulo  <br/> |GUID principal do grupo que mudou.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Nome distinto do membro.  <br/> |
|memberRemoved  <br/> |bit, não nulo  <br/> |Falso se o membro tiver sido adicionado. Verdadeiro se o membro tiver sido removido.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Chave primária.  <br/> |
   

