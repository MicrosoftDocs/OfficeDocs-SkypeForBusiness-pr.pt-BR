---
title: tblPrincipalMemberDifference
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
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: TblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processadas pelas etapas posteriores de Sincronização dos Serviços de Domínio Active Directory.
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809701"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
TblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processadas pelas etapas posteriores de Sincronização dos Serviços de Domínio Active Directory.
  
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
   

