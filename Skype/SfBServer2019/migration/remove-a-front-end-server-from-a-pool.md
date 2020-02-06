---
title: Remover um Servidor Front-End de um pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: O servidor front-end não pode existir como um computador autônomo. Ele deve ser definido como um pool de front-end, mesmo se houver apenas um único computador no pool.
ms.openlocfilehash: 93df9e293f7a1876d4a8b1f172472f708556f67f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813029"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Remover um Servidor Front-End de um pool

O servidor front-end não pode existir como um computador autônomo. Ele deve ser definido como um pool de front-end, mesmo se houver apenas um único computador no pool.
  
Este tópico orienta você pelo processo de remoção de um servidor front-end individual de um pool de front-end existente. Se o servidor front-end for o último servidor do pool ou se você estiver removendo o pool completamente, consulte [remover o pool de front-end ou o servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Não é necessário remover os servidores front-end individuais antes de remover o pool de front-ends. Ao remover o pool, você remove cada servidor front-end.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Para remover um servidor front-end de um pool

1. No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.
    
2. Navegue até o nó instalação herdada.
    
3. Expanda **pools de front-end do Enterprise Edition**, expanda o pool de front-ends com o servidor front-end que você deseja remover, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.
    

