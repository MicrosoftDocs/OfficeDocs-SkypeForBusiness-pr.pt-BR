---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contém a árvore de objetos (com os nós de categoria ou de sala de chat) conforme gerenciado no painel de controle e nos cmdlets administrativos.
ms.openlocfilehash: 99300b6e26a0c173a13e6187680fd150ffa90e0a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814559"
---
# <a name="tblnode"></a>tblNode
 
tblNode contém a árvore de objetos (com os nós de categoria ou de sala de chat) conforme gerenciado no painel de controle e nos cmdlets administrativos.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|NodeId  <br/> |int, não nulo  <br/> |ID do nó (número exclusivo).  <br/> |
|nodeGuid  <br/> |GUID, não nulo  <br/> |GUID do nó.  <br/> |
|parentID  <br/> |int  <br/> |ID do nó do pai. O nó raiz (com ID 1) também inclui o próprio pai.  <br/> |
|nodeType  <br/> |bit, e não nulo  <br/> |Verdadeiro se o nó for uma categoria.  <br/> Falso se o nó for uma sala de chat.  <br/> |
|Node  <br/> |nvarchar (256), NOT NULL  <br/> |Nome do nó.  <br/> |
|nodeDesc  <br/> |nvarchar (256), NOT NULL  <br/> |Descrição do nó.  <br/> |
|Eles  <br/> |bit  <br/> | Para categorias: <br/>  Verdadeiro se os convites estiverem em. <br/>  Falso se os convites estiverem desativados. <br/>  Para salas: <br/>  Falso se os convites estiverem desativados (Substitui a categoria pai). <br/>  Nulo se a configuração convites for herdada da categoria pai. <br/> |
|realizou  <br/> |bit  <br/> | Para categorias: <br/>  Verdadeiro se o histórico de chats estiver ativado. <br/>  Falso se o histórico de chats estiver desativado. <br/>  Para salas: <br/>  Vazio. <br/> |
|Postagem de mensagem  <br/> |bit  <br/> | Para categorias: <br/>  Verdadeiro se os carregamentos de arquivo forem permitidos. <br/>  Falso se os carregamentos de arquivos não forem permitidos. <br/>  Para salas: <br/>  Vazio. <br/> |
|ativo  <br/> |bit, e não nulo  <br/> |Verdadeiro se a sala de chat estiver desabilitada. Aplica-se somente a salas de chat. (Falso para categorias.)  <br/> |
|funcionamento  <br/> |smallint, não nulo  <br/> | Comportamento (pesquisado na tabela EnumValue): <br/>  4: normal (salas de chat normal). <br/>  5: Auditorium (salas de chat Auditorium, somente os apresentadores podem contribuir). <br/>  Aplica-se somente a salas de chat. <br/> |
|visibilidade  <br/> |smallint, não nulo  <br/> | Visibilidade (pesquisada na tabela de EnumValue): <br/>  2: particular <br/>  3: com escopo <br/>  6: abrir <br/>  Aplica-se somente a salas de chat. <br/> |
|siopID  <br/> |GUID  <br/> |GUID do suplemento se um suplemento estiver associado a esta sala de chat. (As categorias não têm suplementos.)  <br/> As informações do suplemento são pesquisadas na tabela SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, não nulo  <br/> |ID da entidade de segurança que criou esse nó.  <br/> |
|nodeAddedOn  <br/> |bigint, e não nulo  <br/> |Carimbo de data/hora da criação de nós.  <br/> |
|nodeUpdatedBy  <br/> |int, não nulo  <br/> |ID da entidade de segurança que fez a atualização mais recente deste nó.  <br/> |
|nodeUpdatedOn  <br/> |bigint, e não nulo  <br/> |Carimbo de data/hora da atualização mais recente deste nó.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Hora da última operação de limpeza (remoção de escopos da tabela tblScopedPrincipal e funções da tabela tblPrincipalRole) que afetou esse nó. Isso é usado pelo mecanismo de atualização do cache interno do serviço de chat.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|NodeId  <br/> |Chave primária.  <br/> |
|funcionamento  <br/> |Chave estrangeira com Lookup na tabela tblEnumValue. valueid.  <br/> |
|visibilidade  <br/> |Chave estrangeira com Lookup na tabela tblEnumValue. valueid.  <br/> |
|parentID  <br/> |Chave estrangeira com Lookup na tabela tblNode. NodeId.  <br/> |
|siopID  <br/> |Chave estrangeira com Lookup na tabela tblSiopWhiteList. siopId.  <br/> |
   

