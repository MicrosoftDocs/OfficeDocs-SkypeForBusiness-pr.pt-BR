---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contém a última ID de convite gerada (e usada na tabela tblPrincipalInvites) para cada usuário.
ms.openlocfilehash: f7a7fdf9038de9a8bf4dcb22bce79f294ea231e5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768439"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId contém a última ID de convite gerada (e usada na tabela tblPrincipalInvites) para cada usuário.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|lastInviteID  <br/> |int, não nulo  <br/> |ID do último convite usado.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|prinID  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.  <br/> |
   
## <a name="see-also"></a>Confira também

[tblPrincipalInvites](tblprincipalinvites.md)
