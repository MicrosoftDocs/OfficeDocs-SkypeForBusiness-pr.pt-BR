---
title: tblChat
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
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: A tabela tblChat contém todas as mensagens de chat.
ms.openlocfilehash: e8a07c0c8ff8b3b473855ee86f6fc0c276e959f6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839813"
---
# <a name="tblchat"></a>tblChat
 
A tabela tblChat contém todas as mensagens de chat.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|channelId  <br/> |int, não nulo  <br/> |ID do nó.  <br/> |
|chatId  <br/> |bigint, não nulo  <br/> |Número sequencial exclusivo (por ID do nó) que define a ordem da sala de chat, gerado pela tabela tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, não nulo  <br/> |Carimbo de hora para a mensagem de chat.  <br/> |
|userId  <br/> |int, não nulo  <br/> |ID principal do pôster.  <br/> |
|isAlert  <br/> |bit, não nulo  <br/> |True se a mensagem for uma mensagem de alerta.False se não for.  <br/> |
|conteúdo  <br/> |nvarchar (max), não nulo  <br/> | Conteúdo de chat (a versão de texto). O conteúdo está normalmente em texto sem formatação com as seguintes exceções: <br/>  Os arquivos são representados como links ma-filelink:. <br/>  Links são representados como um elemento HTML (embora o tipo de conteúdo não possa ser considerado HTML). <br/>  As histórias são codificadas como um formato "[STORY]...."".like. <br/> |
|rtf  <br/> |varchar(max)  <br/> |Conteúdo do chat (a versão RTF). Pode ser Null se o cliente não o fornecer.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |Chave primária.  <br/> |
   

