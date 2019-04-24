---
title: tblLastInviteId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contém a última ID de convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.
ms.openlocfilehash: 977911150992b2e90b7dc344af0550a25ad77221
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212555"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId contém a última ID de convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|lastInviteID  <br/> |int, não nulo  <br/> |ID do último convite usado.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|prinID  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa na tabela Tblprincipal.  <br/> |
   
## <a name="see-also"></a>Confira também

[tblPrincipalInvites](tblprincipalinvites.md)
