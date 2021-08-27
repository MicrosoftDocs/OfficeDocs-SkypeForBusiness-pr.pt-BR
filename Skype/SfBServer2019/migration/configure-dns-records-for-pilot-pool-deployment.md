---
title: Configurar os registros DNS para a implantação do pool piloto
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
description: Antes de implantar o pool piloto, você deve atualizar as entradas dns host A para o pool piloto. Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.
ms.openlocfilehash: e77a85d84debadc19e52cb2d195ac86f5b3e6055
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588053"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar os registros DNS para a implantação do pool piloto

Antes de implantar o pool piloto, você deve atualizar as entradas dns host A para o pool piloto. Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Para configurar os registros de DNS Host A

1. No servidor DNS (Sistema de Nomes de Domínio), clique em **Iniciar**, em **Ferramentas Administrativas** e em **DNS**.
    
2. Na árvore de console do seu domínio, expanda **Zonas** de Busca Encaminhar e clique com o botão direito do mouse no domínio no qual o Skype for Business Server 2019 será instalado.
    
3. Clique em **Novo Host (A ou AAAA)**.
    
4. Clique em Nome , digite o nome do host do pool Skype for Business Server 2019 (o nome de domínio é assumido da zona em que o registro é definido e não precisa ser inserido como parte do registro A).
    
5. Clique **em Endereço IP** e digite o endereço IP para o pool de Front-End.
    
6. Clique em **Adicionar Host** e depois clique em **OK**. 
    
7. Quando tiver terminado, clique em **Concluído**.
    

