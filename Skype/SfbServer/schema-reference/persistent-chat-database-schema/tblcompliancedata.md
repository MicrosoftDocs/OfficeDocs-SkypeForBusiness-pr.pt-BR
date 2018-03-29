---
title: tblComplianceData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: a tabela Compliancedata inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.
ms.openlocfilehash: 6fcee20a96a83a69a3671fe9255f1336590b42de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
a tabela Compliancedata inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, não nulo  <br/> |ID do evento.  <br/> |
|entryDate  <br/> |smalldatetime, não nulo  <br/> |Hora de inserção (pode está longe no futuro para cmplType = 9, pois a entrada é apenas um espaço reservado neste caso).  <br/> |
|cmplType  <br/> |int, não nulo  <br/> | Tipo de evento de conformidade: <br/>  1: chat <br/>  2: Chat persistente <br/>  3: download de arquivo <br/>  4: carregamento de arquivo <br/>  9: transferência de arquivo provisional <br/>  10: exclusão (com substituição) de chat <br/>  11: limpeza de chat <br/> |
|cmplTime  <br/> |bigint, não nulo  <br/> |Carimbo de hora para o evento.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), não nulo  <br/> |Identificador de recurso uniforme do canal (URI).  <br/> |
|cmplChatID  <br/> |bigint  <br/> |Bate-papo ID (correspondendo à tabela de Chatid).  <br/> |
|cmplUserID  <br/> |int, não nulo  <br/> |ID principal do pôster (correspondendo à tabela Tblprincipal).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), não nulo  <br/> |URI do usuário.  <br/> |
|cmplMessage  <br/> |nvarchar (máx.)  <br/> |Mensagem (codificação depende de cmplType).  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|cmplEventID  <br/> |Chave primária.  <br/> |
   

