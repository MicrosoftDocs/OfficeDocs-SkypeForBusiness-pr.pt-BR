---
title: Lista das tabelas de conformidade do servidor de Chat persistente no Skype para Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: O esquema de banco de dados de conformidade Chat persistente consiste as tabelas a seguir.
ms.openlocfilehash: 18c35cc71da43dcf25bb477e81a2471b483ee86d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874312"
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
   

