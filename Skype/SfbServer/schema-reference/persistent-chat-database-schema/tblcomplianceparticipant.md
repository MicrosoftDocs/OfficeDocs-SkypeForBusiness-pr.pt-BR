---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contém os participantes atuais por canal e por servidor.
ms.openlocfilehash: a3d18c4a78af2892a837e1105a435a3ce46ea14b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212948"
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
   

