---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contém os participantes atuais por canal e por servidor.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814639"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contém os participantes atuais por canal e por servidor.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), NOT NULL  <br/> |URI (Uniform Resource Identifier) do canal.  <br/> |
|ID  <br/> |int, não nulo  <br/> |ID da entidade de segurança do participante (correspondente à tabela tblPrincipal. retoid).  <br/> |
|joinedAt  <br/> |bigint, e não nulo  <br/> |Carimbo de data/hora do evento de associação.  <br/> |
|partedAt  <br/> |bigint  <br/> |NULL se o participante ainda estiver associado. O carimbo de data/hora do evento de persaiar de canal, se não for nulo.  <br/> Essas entradas são eventualmente removidas quando todos os tradutores processam o evento.  <br/> |
|userUri  <br/> |nvarchar (255), NOT NULL  <br/> |URI de usuário.  <br/> |
|serverID  <br/> |int  <br/> |Identidade do servidor (como na tabela tblServerIdentity. ServerId).  <br/> |
|Identificação  <br/> |bigint  <br/> |Sessão do servidor. Esse é um número aleatório gerado cada vez que um serviço de chat é iniciado. Ele é usado para diferenciar sessões para fins de identificação de participantes órfãos.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Chave primária.  <br/> |
   

