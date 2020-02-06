---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: o tblADUpdates contém alterações dos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814679"
---
# <a name="tbladupdates"></a>tblADUpdates
 
o tblADUpdates contém alterações dos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, não nulo  <br/> |O principal GUID do objeto que foi alterado.  <br/> |
|prinADPath  <br/> |nvarchar (384), NOT NULL  <br/> |Nome diferenciado do objeto.  <br/> |
|prinAttributesChanged  <br/> |bit, e não nulo  <br/> |True se pelo menos um atributo do objeto foi alterado.  <br/> |
|prinMembersChanged  <br/> |bit, e não nulo  <br/> |Verdadeiro se a associação for alterada.  <br/> |
|prinAffiliationsChanged  <br/> |bit, e não nulo  <br/> |Não usado.  <br/> |
|prinDeleted  <br/> |bit, e não nulo  <br/> |Verdadeiro se o objeto foi excluído.  <br/> |
|lastUpdated  <br/> |DateTime, não nulo  <br/> |Carimbo de data/hora de quando a linha foi inserida.  <br/> |
   

