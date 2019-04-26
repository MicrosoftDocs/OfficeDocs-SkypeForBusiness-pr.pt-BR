---
title: Configurar registros de DNS para implantação de pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implantar o pool piloto, você deve atualizar as entradas de DNS Host A para o pool piloto. Para concluir este procedimento, você deve estar conectado ao servidor ou domínio como membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.
ms.openlocfilehash: 23ac5e4f85dc0da560b4d288bbfad426298bf82e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238727"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros de DNS para implantação de pool piloto

Antes de implantar o pool piloto, você deve atualizar as entradas de DNS Host A para o pool piloto. Para concluir este procedimento, você deve estar conectado ao servidor ou domínio como membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Para configurar os registros do Host DNS

1. No servidor de sistema de nome de domínio (DNS), clique em **Iniciar**, clique em **Ferramentas administrativas**e clique em **DNS**.
    
2. Na árvore de console para seu domínio, expanda **Zonas de pesquisa direta**e, em seguida, clique com botão direito do domínio no qual Skype para Business Server 2019 será instalado.
    
3. Clique em **Novo Host (A ou AAAA)**.
    
4. Clique em **nome**, digite o nome de host para o Skype para pool Business Server 2019 (o nome de domínio é suposto a partir da zona que o registro é definido no e não precisa ser inserido como parte do registro).
    
5. Clique em **Endereço IP**e digite o endereço IP para o pool de Front-End.
    
6. Clique em **Adicionar Host**e, em seguida, clique em **Okey**. 
    
7. Quando terminar, clique em **concluído**.
    

