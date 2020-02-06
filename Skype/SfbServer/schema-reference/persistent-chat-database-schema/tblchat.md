---
title: tblChat
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
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contém todas as mensagens de chat.
ms.openlocfilehash: 7221136c435c1d4af836174ddfde5cbd02f4c5f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814669"
---
# <a name="tblchat"></a>tblChat
 
tblChat contém todas as mensagens de chat.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|channelId  <br/> |int, não nulo  <br/> |ID do nó.  <br/> |
|chats  <br/> |bigint, e não nulo  <br/> |Número seqüencial exclusivo (por ID do nó) que define o pedido de sala de chat, gerado pela tabela tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, e não nulo  <br/> |Carimbo de data/hora para a mensagem de chat.  <br/> |
|ID  <br/> |int, não nulo  <br/> |ID da entidade de segurança do pôster.  <br/> |
|isalert  <br/> |bit, e não nulo  <br/> |Verdadeiro se a mensagem for uma mensagem de alerta. Falso se não for.  <br/> |
|disputa  <br/> |nvarchar (max), NOT NULL  <br/> | Conteúdo de chat (a versão de texto sem formatação). O conteúdo geralmente está em texto sem formatação com as seguintes exceções: <br/>  Os arquivos são representados como links ma-filelink: links. <br/>  Os links são representados como um elemento HTML (embora o tipo de conteúdo não possa ser considerado HTML). <br/>  As matérias são codificadas como um formato "[história]..."-como. <br/> |
|me  <br/> |varchar (max)  <br/> |Conteúdo de chat (a versão RTF). Pode ser NULL se o cliente não fornecê-lo.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<channelId, em chat\>  <br/> |Chave primária.  <br/> |
   

