---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: TblADUpdates contém alterações dos Serviços de Domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de Sincronização do Active Directory.
ms.openlocfilehash: 992834e0086df6ecbc0b8b1cf13a2feaca53cd6ed3f80b6a076abef31e362a6b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329425"
---
# <a name="tbladupdates"></a>tblADUpdates
 
TblADUpdates contém alterações dos Serviços de Domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de Sincronização do Active Directory.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, não nulo  <br/> |GUID da entidade do objeto que mudou.  <br/> |
|prinADPath  <br/> |nvarchar (384), não nulo  <br/> |Nome distinto do objeto.  <br/> |
|prinAttributesChanged  <br/> |bit, não nulo  <br/> |True se pelo menos um atributo do objeto tiver mudado.  <br/> |
|prinMembersChanged  <br/> |bit, não nulo  <br/> |True se a associação tiver sido alterada.  <br/> |
|prinAffiliationsChanged  <br/> |bit, não nulo  <br/> |Não usado  <br/> |
|prinDeleted  <br/> |bit, não nulo  <br/> |True se o objeto tiver sido excluído.  <br/> |
|lastUpdated  <br/> |datetime, não nulo  <br/> |Carimbo de hora de quando a linha foi inserida.  <br/> |
   

