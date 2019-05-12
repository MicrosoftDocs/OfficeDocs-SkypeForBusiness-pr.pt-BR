---
title: Lista das tabelas de conformidade do servidor de Chat persistente no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: O esquema de banco de dados de conformidade Chat persistente consiste as tabelas a seguir.
ms.openlocfilehash: e17b2e52bdeb65ff4c77377cb913da212f20ecf0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929886"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Lista das tabelas de conformidade do servidor de Chat persistente no Skype para Business Server
 
O esquema de banco de dados de conformidade Chat persistente consiste as tabelas a seguir.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista das tabelas de conformidade do servidor de bate-papo persistente

|**Tabela**|**Descrição**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contém eventos de conformidade que ainda não foram processados pelo adaptador configurado.  <br/> Esta tabela inclui eventos de bate-papo persistente relacionados, como mensagens de chat e downloads de arquivo. (Os eventos do participante são controlados pela tabela tblComplianceParticipant.)  <br/> (Os servidores que processaram os eventos nessa tabela são listados na tabela tblComplianceFanout.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contém os servidores que processaram um evento de conformidade. Esta tabela está estreitamente ligada a tabela tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contém os participantes atuais por serviço de bate-papo e por servidor. Ele é mantido com base nos eventos de conformidade de participação e parte recebidos do serviço do Chat persistente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contém informações de estado de conformidade de todo o pool.  <br/> |
   

