---
title: Lista de tabelas de conformidade do Servidor de Chat Persistente Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: O esquema de banco de dados de conformidade de Chat Persistente consiste nas tabelas a seguir.
ms.openlocfilehash: cc4a40d5c2fa80559ddb2ba2cb713c078b4af357
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833245"
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
   

