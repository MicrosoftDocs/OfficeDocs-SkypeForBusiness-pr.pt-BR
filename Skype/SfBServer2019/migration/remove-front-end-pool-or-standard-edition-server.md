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
description: Este tópico orienta você pelo processo de remover um pool de Front-End ou um Edição Standard Servidor Front-End. Quando você remove um pool de Front-End, remove cada Servidor Front-End que pertence ao pool como parte do processo de remoção do pool. Ao remover um servidor Edição Standard front-end, você deve remover a definição SQL Store do Construtor de Topologias.
ms.openlocfilehash: 97407c05afc6055c02b7b54343bbd551c88e6a04236528a74da91f326bf9e25c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304723"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Remover um pool Front-End ou um servidor Standard Edition

Este artigo orienta você pelo processo de remover um pool de Front-End ou um Edição Standard Servidor Front-End. Quando você remove um pool de Front-End, remove cada Servidor Front-End que pertence ao pool como parte do processo de remoção do pool. Ao remover um servidor Edição Standard front-end, você deve remover a definição SQL Store do Construtor de Topologias.
  
## <a name="to-remove-a-front-end-server-pool"></a>Para remover um pool de Servidor Front-End

1. Abra o Construtor de Topologia.
    
2. Navegue até o nó herddo.
    
3. Expanda **Edição Enterprise pools front-end,** expanda o pool de Front-End, clique com o botão direito do mouse no pool de Front-End que você deseja remover e clique em **Excluir**.
    
4. Publique a topologia, verifique o status da replicação e execute o Assistente de Implantação herddo, conforme necessário. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Para remover um Servidor Front-End Standard Edition

1. Abra o Construtor de Topologia.
    
2. Navegue até o nó de instalação herdou.
    
3. Expanda **Edição Standard servidores Front-End,** clique com o botão direito do mouse no Servidor front-end que você deseja remover e clique em **Excluir**.
    
4. Expanda **SQL,** clique com o botão direito do mouse no banco de dados SQL Server que está associado ao servidor Edição Standard front-end e clique em **Excluir**.
    
    > [!IMPORTANT]
    > Você deve remover a definição dos bancos de dados de SQL Server do servidor Edição Standard front-end. 
  
5. Publique a topologia, verifique o status da replicação e execute o Assistente de Implantação conforme necessário. 
    

