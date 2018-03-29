---
title: Principalmemberdifference
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
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a>Principalmemberdifference
 
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
   

