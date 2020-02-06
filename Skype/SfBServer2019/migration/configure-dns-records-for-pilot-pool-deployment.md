---
title: Configurar registros de DNS para implantação de pool piloto
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
description: Antes de implantar o pool piloto, você deve atualizar as entradas do host DNS a para o pool piloto. Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou ao domínio como membro do grupo Domain admins ou de um membro do grupo DnsAdmins.
ms.openlocfilehash: 94e5047dc82b0ddb55b03ad5c466011878c05ae7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813849"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros de DNS para implantação de pool piloto

Antes de implantar o pool piloto, você deve atualizar as entradas do host DNS a para o pool piloto. Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou ao domínio como membro do grupo Domain admins ou de um membro do grupo DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Para configurar registros do host DNS A

1. No servidor DNS (sistema de nomes de domínio), clique em **Iniciar**, clique em **Ferramentas administrativas**e clique em **DNS**.
    
2. Na árvore de console do seu domínio, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Skype for Business Server 2019 será instalado.
    
3. Clique em **novo host (A ou aaaa)**.
    
4. Clique em **nome**, digite o nome do host do pool do Skype for Business Server 2019 (o nome do domínio é presumido na zona em que o registro é definido e não precisa ser inserido como parte do registro a).
    
5. Clique em **endereço IP**e digite o endereço IP do pool de front-ends.
    
6. Clique em **Adicionar host**e, em seguida, clique em **OK**. 
    
7. Quando terminar, clique em **concluído**.
    

