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
ms.localizationpriority: medium
description: O Servidor Front-End não pode existir como um computador autônomo. Ele deve ser definido como um pool de Front-End, mesmo que haja apenas um único computador no pool.
ms.openlocfilehash: b52954421034d83191e479e59d1efeeda8972868
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594995"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Remover um Servidor Front-End de um pool

O Servidor Front-End não pode existir como um computador autônomo. Ele deve ser definido como um pool de Front-End, mesmo que haja apenas um único computador no pool.
  
Este tópico orienta você pelo processo de remover um Servidor Front-End individual de um pool de Front-End existente. Se o Servidor front-end for o último servidor no pool ou se você estiver removendo completamente o pool, consulte [Remove Front End pool or Edição Standard server](remove-front-end-pool-or-standard-edition-server.md). Não é necessário remover os Servidores Front-End individuais antes de remover o pool de Front-End. Ao remover o pool, remova cada Servidor Front-End.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Para remover um servidor Front-End de um pool

1. No servidor front-end Skype for Business Server 2019, abra o Construtor de Topologias.
    
2. Navegue até o nó de instalação herddo.
    
3. Expanda Edição Enterprise pools de **Front-End,** expanda o pool de Front-End com o Servidor front-end que você deseja remover, clique com o botão direito do mouse no Servidor Front-End que você deseja remover e clique em **Excluir**.
    

