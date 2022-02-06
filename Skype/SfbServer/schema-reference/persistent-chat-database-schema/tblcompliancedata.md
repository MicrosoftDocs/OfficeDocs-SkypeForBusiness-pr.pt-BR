---
title: tblComplianceData
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: A tabela ComplianceData inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade
---

# <a name="tblcompliancedata"></a>tblComplianceData
 
A tabela ComplianceData inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, não nulo  <br/> |ID do evento.  <br/> |
|entryDate  <br/> |smalldatetime, não nulo  <br/> |Hora de inserção (pode está longe no futuro para cmplType=9, pois a entrada é apenas um espaço reservado neste caso).  <br/> |
|cmplType  <br/> |int, não nulo  <br/> | Tipo de evento de conformidade: <br/>  1: Chat <br/>  2: Backchat <br/>  3: Download de arquivo <br/>  4: Carregamento de arquivo <br/>  9: Transferência de arquivo provisional <br/>  10: Exclusão de chat (com substituição) <br/>  11: Limpeza de chat <br/> |
|cmplTime  <br/> |bigint, não nulo  <br/> |Carimbo de data/hora para o evento.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), não nulo  <br/> |Canal do Identificador de Recurso Uniforme (URI).  <br/> |
|cmplChatID  <br/> |bigint  <br/> |ID do chat (correspondendo à tabela do Chat.chatId).  <br/> |
|cmplUserID  <br/> |int, não nulo  <br/> |ID principal do pôster (correspondendo à tabela do Principal.prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), não nulo  <br/> |URI do usuário.  <br/> |
|cmplMessage  <br/> |nvarchar (máx)  <br/> |Mensagem (codificação depende de cmplType).  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|cmplEventID  <br/> |Chave primária.  <br/> |
   

