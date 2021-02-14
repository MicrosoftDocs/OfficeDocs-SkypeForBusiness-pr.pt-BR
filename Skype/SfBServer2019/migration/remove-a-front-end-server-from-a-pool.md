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
description: O Servidor Front End não pode existir como um computador autônomo. Ele deve ser definido como um pool de Front-End, mesmo se houver apenas um único computador no pool.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752313"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Remover um Servidor Front-End de um pool

O Servidor Front End não pode existir como um computador autônomo. Ele deve ser definido como um pool de Front-End, mesmo se houver apenas um único computador no pool.
  
Este tópico orienta você durante o processo de remoção de um Servidor front-end individual de um pool de front-end existente. Se o Servidor front-end for o último servidor no pool ou se você estiver removendo o pool completamente, consulte Remover pool de [front-end](remove-front-end-pool-or-standard-edition-server.md)ou servidor Standard Edition . Não é necessário remover os Servidores front-end individuais antes de remover o pool de Front-End. Ao remover o pool, você remove cada Servidor front-end.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Para remover um servidor Front-End de um pool

1. No Servidor front-end do Skype for Business Server 2019, abra o Construtor de Topologias.
    
2. Navegue até o nó de instalação herddo.
    
3. Expanda os pools de **front-end** do Enterprise Edition, expanda o pool de front-end com o servidor front-end que você deseja remover, clique com o botão direito do mouse no Servidor front-end que você deseja remover e clique em **Excluir.**
    

