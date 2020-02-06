---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contém os eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814659"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData contém os eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, e não nulo  <br/> |ID do evento.  <br/> |
|entryDate  <br/> |smalldatetime, não nulo  <br/> |Tempo de inserção (pode estar muito no futuro para cmplType = 9 porque a entrada é apenas um espaço reservado nesse caso).  <br/> |
|cmplType  <br/> |int, não nulo  <br/> | Tipo de evento de conformidade: <br/>  1: chat <br/>  2: backchat <br/>  3: download de arquivo <br/>  4: carregamento de arquivo <br/>  9: transferência de arquivo provisório <br/>  10: exclusão de chat (com replace) <br/>  11: limpeza de chat <br/> |
|cmplTime  <br/> |bigint, e não nulo  <br/> |Carimbo de data/hora do evento.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), NOT NULL  <br/> |URI (Uniform Resource Identifier) do canal.  <br/> |
|cmplChatID  <br/> |bigint  <br/> |ID de chat (correspondente à tabela tblChat. chatid).  <br/> |
|cmplUserID  <br/> |int, não nulo  <br/> |ID da entidade de segurança do pôster (correspondente à tabela tblPrincipal. retoid).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), NOT NULL  <br/> |URI de usuário.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Mensagem (a codificação depende do cmplType).  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|cmplEventID  <br/> |Chave primária.  <br/> |
   

