---
title: Remover um servidor Front-End de um pool
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Servidor Front-End não pode existir como um computador autônomo. Ele deve ser definido como um pool de Front-End, mesmo se houver apenas um único computador no pool.
ms.openlocfilehash: a9f0adc991355b6f79b20365795ffaf92fa230e2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028940"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Remover um servidor Front-End de um pool

Servidor Front-End não pode existir como um computador autônomo. Ele deve ser definido como um pool de Front-End, mesmo se houver apenas um único computador no pool.
  
Este tópico o orienta no processo de remover um servidor Front-End individuais de um pool de Front-End existente. Se o servidor Front-End for o último servidor no pool ou se você estiver removendo completamente o pool, consulte [Remover Front End pool ou servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Não há nenhuma necessidade para remover os servidores Front-End individuais antes de remover o pool de Front-End. Quando você remove o pool, você pode remover cada servidor Front-End.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Para remover um servidor Front-End de um pool

1. No Skype para Business Server 2019 servidor Front-End, abra o construtor de topologias.
    
2. Navegue até o nó install herdado.
    
3. Expanda **pools de Front End do Enterprise Edition**, expanda o pool de Front-End com o servidor Front-End que você deseja remover, clique com o botão servidor Front-End que você deseja remover e clique em **Excluir**.
    

