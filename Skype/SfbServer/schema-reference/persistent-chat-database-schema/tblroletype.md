---
title: tblRoleType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.
ms.openlocfilehash: 6b5e545306c402fbfb89094a19799fe3ff6d2e34
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883142"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, não nulo  <br/> |ID do tipo de função.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), não nulo  <br/> | Descrição do tipo de função. Há quatro funções disponíveis: <br/>  Membro: membro da sala de bate-papo <br/>  Gerente: gerente da sala de Chat <br/>  Com voz: Apresentador para uma sala de bate-papo de auditório <br/>  Criador: Pode criar salas de chat <br/> |
|rtypeAllowedPermSet  <br/> |bigint, não nulo  <br/> | Permissão definido para a função. Os bits usados são: <br/>  2: true se a função puder gerenciar nós. <br/>  4: true se a função puder criar nós filhos. <br/>  7: true se a função pode ingressar em uma sala de chat (ou salas de bate-papo filhos de uma categoria). <br/>  8: true se a função puder conversar em uma sala de chat (ou nas salas filhos de uma categoria). <br/>  10: true se a função puder ler o histórico do chat mesmo quando não está vinculada a uma sala de bate-papo. <br/>  11: true se a função pode ver a sala de bate-papo. (Isso é ainda mais refinado por fatores como escopo e visibilidade.) <br/>  12: true se a função puder conversar em uma sala de bate-papo de auditório. <br/>  13: true se a função puder ignorar as regras de visibilidade ao exibir nós. <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|rtypeID  <br/> |Chave primária.  <br/> |
   

