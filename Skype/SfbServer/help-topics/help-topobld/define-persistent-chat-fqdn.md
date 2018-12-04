---
title: Definir FQDN de Chat Persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Você cria um novo servidor de Chat persistente ou o pool de servidor de Chat persistente usando o assistente Definir Novo Pool de Chat persistente. Selecione um  Pool de vários computadores ou um Pool com um único computador. Se você selecionar um pool com um único computador e precisar mais tarde de um pool com vários computadores, será necessário remover o pool com um único computador e definir um pool com vários computadores.
ms.openlocfilehash: 5dc548f791abe6aa0b697d69bc30ecf3af54d701
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503932"
---
# <a name="define-persistent-chat-fqdn"></a>Definir FQDN de Chat Persistente
 
Você cria um novo servidor de Chat persistente ou o pool de servidor de Chat persistente usando o assistente **Definir Novo Pool de Chat persistente** . Selecione um  **Pool de vários computadores** ou um **Pool com um único computador**. Se você selecionar um pool com um único computador e precisar mais tarde de um pool com vários computadores, será necessário remover o pool com um único computador e definir um pool com vários computadores.
  
Você também deve definir um **FQDN do Pool** para o servidor de Chat persistente ou o pool de servidor de Chat persistente. O nome de domínio totalmente qualificado (FQDN) de um pool com um único computador precisa ser o mesmo que o FQDN do computador que compõe o pool com um único computador. Para um pool com vários computadores, o FQDN precisa ser o nome que você escolher para representar esse pool e precisa ser definido em DNS por um registro de host A (e AAAA se IPv6 estiver sendo usado).
  
## <a name="see-also"></a>Consulte também

[Planejar Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)