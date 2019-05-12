---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contém os participantes atuais por canal e por servidor.
ms.openlocfilehash: 6644796d88f303c6614cbd73d98224fe0e41eabb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929935"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contém os participantes atuais por canal e por servidor.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), não nulo  <br/> |Identificador de recurso uniforme do canal (URI).  <br/> |
|userId  <br/> |int, não nulo  <br/> |ID da entidade do participante (correspondente à tabela Tblprincipal).  <br/> |
|joinedAt  <br/> |bigint, não nulo  <br/> |Carimbo de hora de ingresso no evento.  <br/> |
|partedAt  <br/> |bigint  <br/> |Nulo se participante ainda está vinculada. O carimbo de hora do canal deixando evento se não nulo.  <br/> Essas entradas são eventualmente removidas quando todos os conversores processam o evento.  <br/> |
|userUri  <br/> |nvarchar (255), não nulo  <br/> |URI do usuário.  <br/> |
|serverID  <br/> |int  <br/> |Identidade do servidor (como em Tblserveridentity tabela).  <br/> |
|sessionId  <br/> |bigint  <br/> |Sessão de servidor. Este é um número aleatório gerado sempre que um serviço de bate-papo é iniciado. Ele é usado para diferenciar sessões com o objetivo de identificar participantes órfãos.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Chave primária.  <br/> |
   

