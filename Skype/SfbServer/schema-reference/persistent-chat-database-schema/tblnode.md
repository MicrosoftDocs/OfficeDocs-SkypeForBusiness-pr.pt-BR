---
title: tblNode
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contém a árvore de objetos (com nós de categoria ou sala de chat) como gerenciada no painel de controle e cmdlets administrativos.
ms.openlocfilehash: 0935e5cdec8db7f7ce33b07dcf287c1a8bd5d749
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776141"
---
# <a name="tblnode"></a>tblNode
 
tblNode contém a árvore de objetos (com nós de categoria ou sala de chat) como gerenciada no painel de controle e cmdlets administrativos.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, não nulo  <br/> |ID do Nó (número único).  <br/> |
|nodeGuid  <br/> |GUID, não nulo  <br/> |GUIDO do Nó.  <br/> |
|parentID  <br/> |int  <br/> |ID do nó do pai. O nó raiz (com ID 1) inclui si mesmo como pai também.  <br/> |
|nodeType  <br/> |bit, não nulo  <br/> |Verdadeiro se o nó for uma categoria.  <br/> Falso se o nó for uma sala de chat.  <br/> |
|nodeName  <br/> |nvarchar (256), não nulo  <br/> |Nome do nó.  <br/> |
|nodeDesc  <br/> |nvarchar (256), não nulo  <br/> |Descrição do nó.  <br/> |
|invite  <br/> |bit  <br/> | Para categorias: <br/>  Verdadeiro se convites estiverem ativados. <br/>  Falso se convites estiverem desativados. <br/>  Para salas: <br/>  Falso se convites estiverem desativados (substitui a categoria pai). <br/>  Nulo se a configuração de convites for herdada da categoria pai. <br/> |
|logged  <br/> |bit  <br/> | Para categorias: <br/>  Verdadeiro se o histórico de chat estiver ativado. <br/>  Falso se o histórico de chat estiver desativado. <br/>  Para salas: <br/>  Null. <br/> |
|filePost  <br/> |bit  <br/> | Para categorias: <br/>  Verdadeiro se o carregamento de arquivos for permitido. <br/>  Falso se o carregamento de arquivos não for permitido. <br/>  Para salas: <br/>  Null. <br/> |
|desabilitadas  <br/> |bit, não nulo  <br/> |Verdadeiros se a sala de chat estiver desabilitada. Aplica-se somente a salas de chat (falso para categorias).  <br/> |
|behavior  <br/> |smallint, not null  <br/> | Comportamento (consultado na tabela EnumValue): <br/>  4: Normal (salas de chat normais). <br/>  5: Auditório (salas de chat de auditório, somente apresentadores podem contribuir). <br/>  Aplica-se somente a salas de chat <br/> |
|visibility  <br/> |smallint, não nulo  <br/> | Visibilidade (consultado na tabela EnumValue): <br/>  2: Particular <br/>  3: Com escopo <br/>  6: Abrir <br/>  Aplica-se somente a salas de chat <br/> |
|siopID  <br/> |GUID  <br/> |O GUID de um suplemento é associado a esta sala de chat (categorias não possuem suplementos).  <br/> As informações do suplemento são consultadas na tabela SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, não nulo  <br/> |ID da entidade de segurança que criou este nó.  <br/> |
|nodeAddedOn  <br/> |bigint, não nulo  <br/> |Carimbo de data/hora da criação do nó.  <br/> |
|nodeUpdatedBy  <br/> |int, não nulo  <br/> |ID da entidade de segurança que efetuou a atualização mais recente deste nó.  <br/> |
|nodeUpdatedOn  <br/> |bigint, não nulo  <br/> |Carimbo de data/hora da última atualização deste nó.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Horário da última operação de limpeza (remoção de escopos da tabela tblScopedPrincipal e funções da tabela tblPrincipalRole) que afetou este nó. Isso é usado pelo mecanismo de atualização de cache interno do serviço de Chat.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|nodeID  <br/> |Chave primária.  <br/> |
|behavior  <br/> |Chave estrangeira com consulta na tabela tblEnumValue.valueID.  <br/> |
|visibility  <br/> |Chave estrangeira com consulta na tabela tblEnumValue.valueID.  <br/> |
|parentID  <br/> |Chave estrangeira com pesquisa na tabela tblNode.nodeID.  <br/> |
|siopID  <br/> |Chave estrangeira com consulta na tabela tblSiopWhiteList.siopId.  <br/> |
   

