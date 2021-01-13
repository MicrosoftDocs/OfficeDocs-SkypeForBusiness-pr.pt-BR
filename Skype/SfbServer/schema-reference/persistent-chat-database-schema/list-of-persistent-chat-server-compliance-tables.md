---
title: Lista de tabelas de conformidade do Servidor de Chat Persistente no Skype for Business Server
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
description: O esquema de banco de dados de conformidade do Chat Persistente consiste nas tabelas a seguir.
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813051"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Lista de tabelas de conformidade do Servidor de Chat Persistente no Skype for Business Server
 
O esquema de banco de dados de conformidade do Chat Persistente consiste nas tabelas a seguir.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista das tabelas de conformidade do servidor de chat persistente

|**Table**|**Descrição**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contém eventos de conformidade que ainda não foram processados pelo adaptador configurado.  <br/> Esta tabela inclui eventos relacionados ao Chat Persistente, como mensagens de chat e downloads de arquivos. (Os eventos de participantes são acompanhados pela tabela tblComplianceParticipant.)  <br/> Os servidores que processaram os eventos dessa tabela estão listados na tabela tblComplianceFanout.  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contém os servidores que processaram um evento de conformidade. Esta tabela está diretamente relacionada à tabela tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contém os participantes atuais por serviço de chat e por servidor. Ele é mantido com base nos eventos de conformidade de participação e parte recebidos do serviço de Chat Persistente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contém informações sobre o estado de conformidade de todo o pool.  <br/> |
   

