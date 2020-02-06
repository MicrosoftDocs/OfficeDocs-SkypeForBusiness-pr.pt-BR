---
title: Remover um pool Front-End ou um servidor Standard Edition
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
description: Este tópico fornece orientações sobre o processo de remoção de um pool de front-end ou um servidor front-end Standard Edition. Quando você remove um pool de front-end, Remove cada servidor front-end que pertence ao pool como parte do processo de remoção de pool. Quando você remove um servidor front-end padrão da edição, deve remover a definição do SQL Store do construtor de topologias.
ms.openlocfilehash: d3397b47f94a96cde3326b2479a9e5c6ffd365e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812999"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Remover um pool Front-End ou um servidor Standard Edition

Este artigo orienta você pelo processo de remoção de um pool de front-end ou um servidor front-end Standard Edition. Quando você remove um pool de front-end, Remove cada servidor front-end que pertence ao pool como parte do processo de remoção de pool. Quando você remove um servidor front-end padrão da edição, deve remover a definição do SQL Store do construtor de topologias.
  
## <a name="to-remove-a-front-end-server-pool"></a>Para remover um pool de servidores front-end

1. Abrir o construtor de topologias.
    
2. Navegue até o nó herdado.
    
3. Expanda **pools de front-end do Enterprise Edition**, expanda o pool de front-ends, clique com o botão direito do mouse no pool de front-ends que você deseja remover e clique em **excluir**.
    
4. Publique a topologia, verifique o status da replicação e execute o assistente de implantação herdado conforme necessário. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Para remover um servidor front-end padrão da edição

1. Abrir o construtor de topologias.
    
2. Navegue até o nó instalações herdadas.
    
3. Expanda **servidores front-end padrão da edição**, clique com o botão direito do mouse no servidor front-end que você deseja remover e, em seguida, clique em **excluir**.
    
4. Expanda **repositórios SQL**, clique com o botão direito do mouse no banco de dados do SQL Server associado ao servidor front-end Standard Edition e clique em **excluir**.
    
    > [!IMPORTANT]
    > Você deve remover a definição dos bancos de dados do SQL Server posicionado do servidor front-end da Standard Edition. 
  
5. Publique a topologia, verifique o status da replicação e execute o assistente de implantação conforme necessário. 
    

