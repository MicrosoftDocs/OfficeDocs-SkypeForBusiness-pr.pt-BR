---
title: Remover a associação de Servidor de Arquivamento
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
description: Para remover um Servidor de Arquivamento, você precisa alterar ou limpar a dependência no pool de Front-End associado, servidor front-end, Aparelho de Filial E Servidor de Filial Survivível. Edite as propriedades do pool de Front-End, servidor front-end, Aparelho de Filial Survivável e Servidor de Filial Survivable para remover a dependência. Depois de limpar a dependência e excluir o servidor no Construtor de Topologias, você será notificado de que o objeto de armazenamento de banco de dados associado no Construtor de Topologias também será excluído.
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752133"
---
# <a name="remove-the-archiving-server-association"></a>Remover a associação de Servidor de Arquivamento

Para remover um Servidor de Arquivamento, você precisa alterar ou limpar a dependência no pool de Front-End associado, servidor front-end, Aparelho de Filial Survivável e Servidor de Filial Survivable. Edite as propriedades do pool de Front-End, servidor front-end, Aparelho de Filial Survivável e Servidor de Filial Survivable para remover a dependência. Depois de limpar a dependência e excluir o servidor no Construtor de Topologias, você será notificado de que o objeto de armazenamento de banco de dados associado no Construtor de Topologias também será excluído.
  
### <a name="to-remove-the-archiving-server-association"></a>Para remover a associação de Servidor de Arquivamento

1. No Servidor front-end do Skype for Business Server 2019, abra o Construtor de Topologias.
    
2. Navegue até o nó de instalação herddo.
    
3. No Construtor de Topologias, **expanda pools de front-end** enterprise edition , **servidores de front-end Standard Edition** ou sites de **filial**, dependendo de onde o Servidor de Arquivamento está definido.
    
4. Se você tiver um Servidor de Filial Survivable associado, expanda **os sites** de filial, expanda o nome do site de filial e expanda Aparelhos de Filial **Survivable.**
    
    > [!NOTE]
    > **Os Aparelhos** de FilialVivíveis na interface do usuário se aplica ao Servidor de Filial Survivable e ao Aparelho de Filial Survivable. 
  
5. Clique com o botão direito do mouse no pool, servidor ou dispositivo associado ao Servidor de Arquivamento e clique em **Editar Propriedades.**
    
6. Em **Editar Propriedades**, em **Associações** Gerais ,  >  **des des** clear the Associate **Archiving Server** check box, and then click **OK**.
    
7. Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao Servidor de Arquivamento que você deseja remover.
    
8. Clique com o botão direito do mouse no Servidor de Arquivamento e clique em **Excluir.**
    
9. Em **Excluir Repositórios Dependentes**, clique em **OK**.
    
10. Publique a topologia, verifique o status de replicação e execute o Assistente de Implantação do Skype for Business Server conforme necessário. 
    

