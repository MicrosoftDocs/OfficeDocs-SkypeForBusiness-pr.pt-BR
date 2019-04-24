---
title: tblNode
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contém a árvore de objeto (conosco de categoria ou sala de bate-papo), como gerenciado no painel de controle e cmdlets administrativos.
ms.openlocfilehash: c5028b138711b6f57c0e947ea41572fd9984b3fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212548"
---
# <a name="tblnode"></a>tblNode
 
tblNode contém a árvore de objeto (conosco de categoria ou sala de bate-papo), como gerenciado no painel de controle e cmdlets administrativos.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, não nulo  <br/> |ID do nó (número único).  <br/> |
|nodeGuid  <br/> |GUID, não nulo  <br/> |GUIDO do nó.  <br/> |
|parentID  <br/> |int  <br/> |ID do nó do pai. O nó raiz (com ID 1) inclui próprio como pai também.  <br/> |
|nodeType  <br/> |bit, não nulo  <br/> |True se o nó for uma categoria.  <br/> False se o nó for uma sala de bate-papo.  <br/> |
|nodeName  <br/> |nvarchar (256), não nulo  <br/> |Nome do nó.  <br/> |
|nodeDesc  <br/> |nvarchar (256), não nulo  <br/> |Descrição do nó.  <br/> |
|Convidar  <br/> |bit  <br/> | Para categorias: <br/>  True se convites estiverem ativados. <br/>  FALSO se convites estiverem desativados. <br/>  Para salas: <br/>  FALSO se convites estiverem desativados (substitui a categoria pai). <br/>  Nulo se a configuração de convites for herdada da categoria pai. <br/> |
|conectado  <br/> |bit  <br/> | Para categorias: <br/>  True se o histórico de chat estiver ligado. <br/>  False se o histórico de chat estiver desativado. <br/>  Para salas: <br/>  Nulo. <br/> |
|filePost  <br/> |bit  <br/> | Para categorias: <br/>  True se carregamentos de arquivos são permitidos. <br/>  FALSO se carregamentos de arquivo não são permitidos. <br/>  Para salas: <br/>  Nulo. <br/> |
|desabilitado  <br/> |bit, não nulo  <br/> |True se a sala de bate-papo está desabilitada. Aplica-se somente a salas de chat. (False para categorias).  <br/> |
|comportamento  <br/> |smallint, não nulo  <br/> | Comportamento (consultado na tabela EnumValue): <br/>  4: Normal (salas de chat normais). <br/>  5: auditório (salas de bate-papo de auditório, somente apresentadores podem de contribuir). <br/>  Aplica-se somente a salas de chat. <br/> |
|visibilidade  <br/> |smallint, não nulo  <br/> | Visibilidade (consultada na tabela EnumValue): <br/>  2: privada <br/>  3: com escopo <br/>  6: open <br/>  Aplica-se somente a salas de chat. <br/> |
|siopID  <br/> |GUID  <br/> |Suplemento GUID se um suplemento estiver associado esta sala de bate-papo. (As categorias não têm complementos.)  <br/> As informações do suplemento são consultadas na tabela SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, não nulo  <br/> |ID da entidade de segurança que criou este nó.  <br/> |
|nodeAddedOn  <br/> |bigint, não nulo  <br/> |Carimbo de hora da criação do nó.  <br/> |
|nodeUpdatedBy  <br/> |int, não nulo  <br/> |ID da entidade de segurança que efetuou a atualização mais recente deste nó.  <br/> |
|nodeUpdatedOn  <br/> |bigint, não nulo  <br/> |Carimbo de hora da última atualização deste nó.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Hora da operação purge (remoção de escopos da tabela tblScopedPrincipal e funções da tabela tblPrincipalRole) mais recente que afetaram deste nó. Isso é usado pelo mecanismo de atualização de cache interno do serviço de bate-papo.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|nodeID  <br/> |Chave primária.  <br/> |
|comportamento  <br/> |Chave estrangeira com pesquisa na tabela Tblenumvalue.  <br/> |
|visibilidade  <br/> |Chave estrangeira com pesquisa na tabela Tblenumvalue.  <br/> |
|parentID  <br/> |Chave estrangeira com pesquisa na tabela Tblnode.  <br/> |
|siopID  <br/> |Chave estrangeira com pesquisa na tabela Tblsiopwhitelist.  <br/> |
   

