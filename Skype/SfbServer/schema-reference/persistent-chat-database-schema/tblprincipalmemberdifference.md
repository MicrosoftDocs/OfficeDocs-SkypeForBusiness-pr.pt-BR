---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: a tabela Principalmemberdifference inclui as alterações de associação do grupo (tanto adicionadas e removidas membros) que ainda não foram processadas pelas etapas posteriores de sincronização de serviços de domínio do Active Directory.
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212443"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
a tabela Principalmemberdifference inclui as alterações de associação do grupo (tanto adicionadas e removidas membros) que ainda não foram processadas pelas etapas posteriores de sincronização de serviços de domínio do Active Directory.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, não nulo  <br/> |GUID principal do grupo que mudou.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Nome distinto do membro.  <br/> |
|memberRemoved  <br/> |bit, não nulo  <br/> |False se o membro foi adicionado. True se o membro foi removido.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Chave primária.  <br/> |
   

