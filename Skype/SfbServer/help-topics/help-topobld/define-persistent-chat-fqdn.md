---
title: Definir FQDN de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Você cria um novo servidor de chat persistente ou pool de servidor de chat persistente usando o assistente definir novo pool de chat persistente. Selecione um pool de vários computadores ou um pool de computador único. Se você selecionar um pool de computador único e mais tarde precisar de um pool de vários computadores, será necessário remover o pool de computador único e, em seguida, definir um pool de vários computadores.
ms.openlocfilehash: 61851656b70b85db47fdad01dff0101217262dda
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217543"
---
# <a name="define-persistent-chat-fqdn"></a>Definir FQDN de Chat Persistente
 
Você cria um novo servidor de chat persistente ou pool de servidor de chat persistente usando o assistente **definir novo pool de chat persistente** . Selecione um **pool de vários computadores** ou um **pool de computador único**. Se você selecionar um pool de computador único e mais tarde precisar de um pool de vários computadores, será necessário remover o pool de computador único e, em seguida, definir um pool de vários computadores.
  
Você também deve definir um **FQDN de pool** para o servidor de chat persistente ou o pool de servidor de chat persistente. O nome de domínio totalmente qualificado (FQDN) do pool para um único pool de computador deve ser o mesmo que o FQDN do computador que compõe o pool de servidor único. Para um pool de vários computadores, o FQDN deve ser o nome que você escolhe para representar esse pool de vários computadores e é definido no DNS por um registro A (e AAAA se IPv6 estiver sendo usado).
  
## <a name="see-also"></a>Confira também

[Planejar o servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar servidor de chat persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
