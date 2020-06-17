---
title: Remover um Servidor Front-End de um pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: O servidor front-end não pode existir como um computador autônomo. Ele deve ser definido como um pool de front-ends, mesmo se houver apenas um único computador no pool.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752313"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Remover um Servidor Front-End de um pool

O servidor front-end não pode existir como um computador autônomo. Ele deve ser definido como um pool de front-ends, mesmo se houver apenas um único computador no pool.
  
Este tópico orienta você durante o processo de remoção de um servidor front-end individual de um pool de front-ends existente. Se o servidor front-end for o último servidor do pool ou se você estiver removendo o pool completamente, consulte [Remove front end pool ou Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md). Não é necessário remover os servidores front-end individuais antes de remover o pool de front-ends. Ao remover o pool, você remove cada servidor de front-end.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Para remover um servidor Front-End de um pool

1. No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.
    
2. Navegue até o nó de instalação herdado.
    
3. Expanda **pools de front-ends Enterprise Edition**, expanda o pool de front-ends com o servidor front-end que você deseja remover, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.
    

