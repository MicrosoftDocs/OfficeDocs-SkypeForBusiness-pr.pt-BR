---
title: tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: a tabela tblChat contém todas as mensagens de chat.
ms.openlocfilehash: 77aa6ec803803a0f38e02c01167d0bbc5f090080
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929907"
---
# <a name="tblchat"></a>tblChat
 
a tabela tblChat contém todas as mensagens de chat.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|channelId  <br/> |int, não nulo  <br/> |ID do nó.  <br/> |
|chatId  <br/> |bigint, não nulo  <br/> |Número sequencial exclusivo (por ID do nó) que define a ordem da sala de chat, gerada pela tabela tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, não nulo  <br/> |Carimbo de hora para a mensagem de bate-papo.  <br/> |
|userId  <br/> |int, não nulo  <br/> |ID principal do pôster.  <br/> |
|isAlert  <br/> |bit, não nulo  <br/> |True se a mensagem é uma mensagem de alerta. False se não for.  <br/> |
|conteúdo  <br/> |nvarchar (max), não nulo  <br/> | Conteúdo do Chat (a versão de texto não criptografado). O conteúdo é geralmente em texto sem formatação com as seguintes exceções: <br/>  Arquivos são representados como ma-filelink: links. <br/>  Links são representados como um elemento HTML (embora o tipo de conteúdo não pode ser considerado HTML). <br/>  Histórias são codificadas como um "[STORY]..."-formato parecido com. <br/> |
|RTF  <br/> |varchar (max)  <br/> |Conteúdo do Chat (a versão RTF). Pode ser Null se o cliente não fornecer a ele.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |Chave primária.  <br/> |
   

