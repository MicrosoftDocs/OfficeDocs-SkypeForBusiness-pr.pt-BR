---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 884f1450b74300ad2915c27b524dc0419c97062d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743157"
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
   

