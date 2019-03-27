---
title: tblADUpdates
ms.reviewer: ''
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
ms.openlocfilehash: 0e7bde110ad3d0495cb7ddea55e405eac21d96b4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899600"
---
# <a name="tbladupdates"></a>tblADUpdates
 
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
   

