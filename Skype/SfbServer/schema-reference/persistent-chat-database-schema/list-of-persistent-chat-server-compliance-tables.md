---
title: Lista de tabelas de conformidade do Servidor de Chat Persistente Skype for Business Server
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
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: O esquema de banco de dados de conformidade de Chat Persistente consiste nas tabelas a seguir.
ms.openlocfilehash: b41d8a3f3c5e42f9e4c29eeb6cb81774b5b177aee18c67dc52bc4c9009f67c8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303664"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Lista de tabelas de conformidade do Servidor de Chat Persistente Skype for Business Server
 
O esquema de banco de dados de conformidade de Chat Persistente consiste nas tabelas a seguir.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista das tabelas de conformidade do servidor de chat persistente

|**Table**|**Descrição**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contém eventos de conformidade que ainda não foram processados pelo adaptador configurado.  <br/> Esta tabela inclui eventos relacionados ao Chat Persistente, como mensagens de chat e downloads de arquivos. (Os eventos dos participantes são acompanhados pela tabela tblComplianceParticipant.)  <br/> Os servidores que processaram os eventos dessa tabela estão listados na tabela tblComplianceFanout.  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contém os servidores que processaram um evento de conformidade. Esta tabela está diretamente relacionada à tabela tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contém os participantes atuais por serviço de chat e por servidor. Ele é mantido com base nos eventos de conformidade de participação e parte recebidos do serviço de Chat Persistente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contém informações sobre o estado de conformidade de todo o pool.  <br/> |
   

