---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta inclui as entidades que precisam ser atualizadas dos serviços de domínio Active Directory.
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212429"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta inclui as entidades que precisam ser atualizadas dos serviços de domínio Active Directory.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|prinAffiliationsDirty  <br/> |bit, não nulo  <br/> |True se a entidade afiliações precisam ser atualizadas.  <br/> |
|prinAttributesDirty  <br/> |bit, não nulo  <br/> |True se a entidade atributos precisam ser atualizadas.  <br/> |
|prinDeleted  <br/> |bit, não nulo  <br/> |True se a entidade foi excluída.  <br/> |
|tryCount  <br/> |int  <br/> |Número de tentativas para atualizar a entidade do AD DS que ocorreram até o momento.  <br/> |
|lastTry  <br/> |datetime  <br/> |Carimbo de hora da última tentativa para atualizar a entidade. Pode ser null se nenhuma atualização foi tentada ainda.  <br/> |
|nextTry  <br/> |datetime  <br/> |Carimbo de hora para a próxima atualização agendada. Pode ser null se nenhuma outra atualização foi agendada.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|prinID  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa na tabela Tblprincipal.  <br/> |
   

