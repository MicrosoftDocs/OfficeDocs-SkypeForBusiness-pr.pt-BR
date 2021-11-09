---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contém funções explícitas atribuídas aos nós.
ms.openlocfilehash: 6c9960c4eafc2d28a4710a8e4dded6bea19c841a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828524"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole contém funções explícitas atribuídas aos nós.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, not null  <br/> |ID do nó à que a função se aplica.  <br/> |
|prinRolePrinID  <br/> |int, not null  <br/> |ID principal.  <br/> |
|prinRoleTypeID  <br/> |int, not null  <br/> |ID do tipo de função (de tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, not null  <br/> |ID da entidade de segurança da última atualização dessa entrada.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Chave primária.  <br/> |
|prinRoleNodeID  <br/> |Chave estrangeira com pesquisa na tabela tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Chave estrangeira com lookup na tabela tblRoleType.rtypeID.  <br/> |
   

