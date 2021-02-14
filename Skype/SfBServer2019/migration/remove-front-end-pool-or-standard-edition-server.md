---
title: Remover um pool Front-End ou um servidor Standard Edition
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
description: 'Este tópico orienta você durante o processo de remoção de um pool de front-end ou um servidor de front-end Standard Edition. Ao remover um pool de Front-End, você remove cada Servidor front-end que pertence ao pool como parte do processo de remoção do pool. Ao remover um Servidor #A0 Standard Edition, você deve remover a definição do SQL Store do Construtor de Topologias.'
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752273"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Remover um pool Front-End ou um servidor Standard Edition

Este artigo orienta você durante o processo de remoção de um pool de front-end ou um servidor de front-end Standard Edition. Ao remover um pool de Front-End, você remove cada Servidor front-end que pertence ao pool como parte do processo de remoção do pool. Ao remover um Servidor #A0 Standard Edition, você deve remover a definição do SQL Store do Construtor de Topologias.
  
## <a name="to-remove-a-front-end-server-pool"></a>Para remover um pool de Servidor Front-End

1. Abra o Construtor de Topologia.
    
2. Navegue até o nó herddo.
    
3. Expanda **pools de front-end** do Enterprise Edition, expanda o pool de Front-End, clique com o botão direito do mouse no pool de Front-End que você deseja remover e clique em **Excluir.**
    
4. Publique a topologia, verifique o status de replicação e execute o Assistente de Implantação herddo conforme necessário. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Para remover um Servidor Front-End Standard Edition

1. Abra o Construtor de Topologia.
    
2. Navegue até o nó de instalação herdam.
    
3. Expanda **os servidores front-end** do Standard Edition, clique com o botão direito do mouse no Servidor front-end que você deseja remover e clique em **Excluir.**
    
4. Expanda **os armazenamentos SQL,** clique com o botão direito do mouse no banco de dados do SQL Server associado ao Servidor #A0 Standard Edition e clique em **Excluir.**
    
    > [!IMPORTANT]
    > Você deve remover a definição dos bancos de dados do SQL Server alocados do Servidor #A0 Standard Edition. 
  
5. Publique a topologia, verifique o status da replicação e execute o Assistente de Implantação conforme necessário. 
    

