---
title: Lista de tabelas de conformidade do servidor de chat persistente no Skype for Business Server
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
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: O esquema de banco de dados de conformidade de chat persistente consiste nas tabelas a seguir.
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814759"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Lista de tabelas de conformidade do servidor de chat persistente no Skype for Business Server
 
O esquema de banco de dados de conformidade de chat persistente consiste nas tabelas a seguir.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista de tabelas de conformidade do servidor de chat persistente

|**Tabela**|**Descrição**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contém os eventos de conformidade que ainda não foram processados pelo adaptador configurado.  <br/> Esta tabela inclui eventos persistentes relacionados a chats, como mensagens de chat e downloads de arquivos. (Os eventos do participante são rastreados pela tabela tblComplianceParticipant.)  <br/> (Os servidores que processaram os eventos nessa tabela estão listados na tabela tblComplianceFanout.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contém os servidores que processaram um evento de conformidade. Esta tabela está rigidamente acoplada à tabela tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contém os participantes atuais por serviço de chat e por servidor. Ele é mantido com base nos eventos de conformidade do ingresso e na parte recebidos do serviço de chat persistente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contém informações de estado de conformidade em todo o pool.  <br/> |
   

