---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: TblADUpdates contém alterações dos Serviços de Domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de Sincronização do Active Directory.
ms.openlocfilehash: 00c3cce25b3e69372813721192677956ec8a15d4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839823"
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
   

