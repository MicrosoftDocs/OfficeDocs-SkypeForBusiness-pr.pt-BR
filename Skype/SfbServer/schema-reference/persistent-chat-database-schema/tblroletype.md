---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812899"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, não nulo  <br/> |ID do tipo de função.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), NOT NULL  <br/> | Descrição do tipo de função. Há quatro funções disponíveis: <br/>  Membro: membro da sala de chat <br/>  Manager: gerente da sala de chat <br/>  Encaixado: apresentador para uma sala de chat do Auditorium <br/>  Creator: pode criar salas de chat <br/> |
|rtypeAllowedPermSet  <br/> |bigint, e não nulo  <br/> | Conjunto de permissões para a função. Os bits usados são: <br/>  2: verdadeiro se a função puder gerenciar nós. <br/>  4: verdadeiro se a função puder criar nós filhos. <br/>  7: verdadeiro se a função puder ingressar em uma sala de chat (ou salas de chat dos filhos de uma categoria). <br/>  8: verdadeiro se a função puder conversar em uma sala de chat (ou nas salas de chat dos filhos de uma categoria). <br/>  10: verdadeiro se a função puder ler o histórico de chats mesmo quando não estiver associado a uma sala de chat. <br/>  11: verdadeiro se a função puder ver a sala de chat. (Isso é ainda mais refinado por fatores como escopo e visibilidade.) <br/>  12: verdadeiro se a função puder conversar em uma sala de chat do Auditorium. <br/>  13: verdadeiro se a função puder ignorar as regras de visibilidade ao exibir nós. <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|rtypeID  <br/> |Chave primária.  <br/> |
   

