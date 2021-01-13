---
title: tblComplianceParticipant
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
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contém os participantes atuais por canal e por servidor.
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809741"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contém os participantes atuais por canal e por servidor.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), não nulo  <br/> |Identificador de Recurso Uniforme do Canal (URI).  <br/> |
|userId  <br/> |int, não nulo  <br/> |ID da entidade do participante (correspondente à tabela tblPrincipal.prinID).  <br/> |
|joinedAt  <br/> |bigint, não nulo  <br/> |Carimbo de data e hora de ingresso no evento.  <br/> |
|partedAt  <br/> |bigint  <br/> |Nulo se o participante ainda estiver ingressado. O carimbo de data e hora de quando o canal deixa o evento se não for nulo.  <br/> Essas entradas são eventualmente removidas quando todos os conversores processam o evento.  <br/> |
|userUri  <br/> |nvarchar (255), não nulo  <br/> |URI do Usuário.  <br/> |
|serverID  <br/> |int  <br/> |Identidade do servidor (como na tabela tblServerIdentity.serverID).  <br/> |
|sessionId  <br/> |bigint  <br/> |Sessão do servidor. Este é um número aleatório gerado sempre que um serviço de chat é iniciado. Ele é usado para diferenciar as sessões a fim de identificar os participantes órfãos.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Chave primária.  <br/> |
   

