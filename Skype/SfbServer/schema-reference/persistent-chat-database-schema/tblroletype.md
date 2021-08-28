---
title: tblRoleType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType é uma tabela de pesquisa estática com tipos de funções e seus conjuntos de permissões associados.
ms.openlocfilehash: 341655ec26202bb1158d40ac8f6e36c4aad24542
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611860"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType é uma tabela de pesquisa estática com tipos de funções e seus conjuntos de permissões associados.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, not null  <br/> |ID do tipo de função.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), not null  <br/> | Descrição do tipo de função. Existem quatro funções disponíveis: <br/>  Membro: Membro da sala de chat <br/>  Gerente: Gerente da sala de chat <br/>  Com voz: Apresentador para uma sala de chat de auditório <br/>  Criador: Pode criar salas de bate-papo <br/> |
|rtypeAllowedPermSet  <br/> |bigint, not null  <br/> | Permissão configurada para a função. Os bits usados são: <br/>  2: True se a função puder gerenciar nós. <br/>  4: True se a função puder criar nós filhos. <br/>  7: True se a função puder entrar em uma sala de chat (ou nas salas filhos de uma categoria). <br/>  8: True se a função puder conversar em uma sala de chat (ou nas salas filhos de uma categoria). <br/>  10: True se a função puder ler o histórico do chat mesmo quando não tiver entrado na sala de chat. <br/>  11: True se a função puder ver a sala de chat (refinado por fatores como escopo e visibilidade). <br/>  12: True se a função puder conversar em uma sala de chat de auditório. <br/>  13: True se a função puder ignorar as regras de visibilidade ao exibir nós. <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|rtypeID  <br/> |Chave primária.  <br/> |
   

