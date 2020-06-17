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
description: Este tópico orienta você durante o processo de remoção de um pool de front-ends ou de um servidor front-end Standard Edition. Ao remover um pool de front-ends, você remove cada servidor de front-end que pertence ao pool como parte do processo de remoção do pool. Ao remover um servidor front-end Standard Edition, você deve remover a definição do repositório SQL do construtor de topologias.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752273"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Remover um pool Front-End ou um servidor Standard Edition

Este artigo orienta você durante o processo de remoção de um pool de front-ends ou um servidor front-end Standard Edition. Ao remover um pool de front-ends, você remove cada servidor de front-end que pertence ao pool como parte do processo de remoção do pool. Ao remover um servidor front-end Standard Edition, você deve remover a definição do repositório SQL do construtor de topologias.
  
## <a name="to-remove-a-front-end-server-pool"></a>Para remover um pool de Servidor Front-End

1. Abra o Construtor de Topologia.
    
2. Navegue até o nó herdado.
    
3. Expanda **pools de front-ends Enterprise Edition**, expanda o pool de front-ends, clique com o botão direito do mouse no pool de front-ends que você deseja remover e clique em **excluir**.
    
4. Publique a topologia, verifique o status da replicação e execute o assistente de implantação herdado conforme necessário. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Para remover um Servidor Front-End Standard Edition

1. Abra o Construtor de Topologia.
    
2. Navegue até o nó instalações herdadas.
    
3. Expanda **servidores front-end Standard Edition**, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.
    
4. Expanda **repositórios SQL**, clique com o botão direito do mouse no banco de dados do SQL Server que está associado ao servidor front-end Standard Edition e clique em **excluir**.
    
    > [!IMPORTANT]
    > Você deve remover a definição dos bancos de dados do SQL Server posicionados do servidor front-end Standard Edition. 
  
5. Publique a topologia, verifique o status da replicação e execute o assistente de implantação conforme necessário. 
    

