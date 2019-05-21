---
title: Remover um Servidor Front-End de um pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: O servidor front-end não pode existir como um computador autônomo. Ele deve ser definido como um pool de front-end, mesmo se houver apenas um único computador no pool.
ms.openlocfilehash: 5c1cd06e4cbe5cd6cecd8484e9c7874fb5ba590e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301136"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Remover um Servidor Front-End de um pool

O servidor front-end não pode existir como um computador autônomo. Ele deve ser definido como um pool de front-end, mesmo se houver apenas um único computador no pool.
  
Este tópico orienta você pelo processo de remoção de um servidor front-end individual de um pool de front-end existente. Se o servidor front-end for o último servidor do pool ou se você estiver removendo o pool completamente, consulte [remover o pool de front-end ou o servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Não é necessário remover os servidores front-end individuais antes de remover o pool de front-ends. Ao remover o pool, você remove cada servidor front-end.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Para remover um servidor front-end de um pool

1. No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.
    
2. Navegue até o nó instalação herdada.
    
3. Expanda Pools de **front-end do Enterprise Edition**, expanda o pool de front-ends com o servidor front-end que você deseja remover, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.
    

