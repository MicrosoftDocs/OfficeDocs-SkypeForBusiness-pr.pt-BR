---
title: a tabela tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: a tabela tblADUpdates contém alterações de serviços de domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de sincronização do Active Directory.
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a>a tabela tblADUpdates
 
a tabela tblADUpdates contém alterações de serviços de domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de sincronização do Active Directory.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, não nulo  <br/> |GUID principal do objeto que foi alterado.  <br/> |
|prinADPath  <br/> |nvarchar (384), não nulo  <br/> |Nome distinto do objeto.  <br/> |
|prinAttributesChanged  <br/> |bit, não nulo  <br/> |True se pelo menos um atributo do objeto é alterado.  <br/> |
|prinMembersChanged  <br/> |bit, não nulo  <br/> |True se a associação tiver sido alterada.  <br/> |
|prinAffiliationsChanged  <br/> |bit, não nulo  <br/> |Não usado.  <br/> |
|prinDeleted  <br/> |bit, não nulo  <br/> |True se o objeto foi excluído.  <br/> |
|lastUpdated  <br/> |DateTime, não nulo  <br/> |Carimbo de hora de quando a linha foi inserida.  <br/> |
   

