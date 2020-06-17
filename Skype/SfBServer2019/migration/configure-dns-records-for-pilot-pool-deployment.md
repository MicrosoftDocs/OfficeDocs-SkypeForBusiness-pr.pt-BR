---
title: Configurar registros de DNS para implantação de pool piloto
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
description: Antes de implantar o pool piloto, você deve atualizar as entradas do host DNS a para o pool piloto. Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754051"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros de DNS para implantação de pool piloto

Antes de implantar o pool piloto, você deve atualizar as entradas do host DNS a para o pool piloto. Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Para configurar os registros de DNS Host A

1. No servidor DNS (Sistema de Nomes de Domínio), clique em **Iniciar**, em **Ferramentas Administrativas** e em **DNS**.
    
2. Na árvore de console do seu domínio, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Skype for Business Server 2019 será instalado.
    
3. Clique em **Novo Host (A ou AAAA)**.
    
4. Clique em **nome**, digite o nome do host para o pool do Skype for Business Server 2019 (o nome do domínio é considerado da zona em que o registro está definido e não precisa ser inserido como parte do registro a).
    
5. Clique em **endereço IP**e digite o endereço IP do pool de front-ends.
    
6. Clique em **Adicionar Host** e depois clique em **OK**. 
    
7. Quando tiver terminado, clique em **Concluído**.
    

