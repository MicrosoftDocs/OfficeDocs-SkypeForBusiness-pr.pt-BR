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
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: o tblADUpdates contém alterações dos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295556"
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
   

