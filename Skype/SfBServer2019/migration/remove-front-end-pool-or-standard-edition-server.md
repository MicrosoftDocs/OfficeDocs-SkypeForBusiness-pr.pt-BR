---
title: Remover um pool Front-End ou um servidor Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tópico fornece orientações sobre o processo de remoção de um pool de front-end ou um servidor front-end Standard Edition. Quando você remove um pool de front-end, Remove cada servidor front-end que pertence ao pool como parte do processo de remoção de pool. Quando você remove um servidor front-end padrão da edição, deve remover a definição do SQL Store do construtor de topologias.
ms.openlocfilehash: fd43682fca67b961ac93c01813ca6ea9e702b644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301129"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Remover um pool Front-End ou um servidor Standard Edition

Este artigo orienta você pelo processo de remoção de um pool de front-end ou um servidor front-end Standard Edition. Quando você remove um pool de front-end, Remove cada servidor front-end que pertence ao pool como parte do processo de remoção de pool. Quando você remove um servidor front-end padrão da edição, deve remover a definição do SQL Store do construtor de topologias.
  
## <a name="to-remove-a-front-end-server-pool"></a>Para remover um pool de servidores front-end

1. Abrir o construtor de topologias.
    
2. Navegue até o nó herdado.
    
3. Expanda Pools de **front-end do Enterprise Edition**, expanda o pool de front-ends, clique com o botão direito do mouse no pool de front-ends que você deseja remover e clique em **excluir**.
    
4. Publique a topologia, verifique o status da replicação e execute o assistente de implantação herdado conforme necessário. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Para remover um servidor front-end padrão da edição

1. Abrir o construtor de topologias.
    
2. Navegue até o nó instalações herdadas.
    
3. Expanda **servidores front-end padrão da edição**, clique com o botão direito do mouse no servidor front-end que você deseja remover e, em seguida, clique em **excluir**.
    
4. Expanda **repositórios SQL**, clique com o botão direito do mouse no banco de dados do SQL Server associado ao servidor front-end Standard Edition e clique em **excluir**.
    
    > [!IMPORTANT]
    > Você deve remover a definição dos bancos de dados do SQL Server posicionado do servidor front-end da Standard Edition. 
  
5. Publique a topologia, verifique o status da replicação e execute o assistente de implantação conforme necessário. 
    

