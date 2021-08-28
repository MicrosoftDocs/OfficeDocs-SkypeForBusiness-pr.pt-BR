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
ms.localizationpriority: medium
description: Para remover um Servidor de Arquivamento, você precisa alterar ou limpar a dependência no pool de Front-End associado, Servidor Front-End, Aparelho de Filial E Servidor de Filial Desavivável. Edite as propriedades do pool front-end, servidor front-end, aparelho de filial e servidor de filial que sobrevive para remover a dependência. Depois de limpar a dependência e excluir o servidor no Construtor de Topologias, você será notificado de que o objeto de armazenamento de banco de dados associado no Construtor de Topologias também será excluído.
ms.openlocfilehash: 489eeb276b495598ec2f11fc9b4502935beedf30
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617067"
---
# <a name="remove-the-archiving-server-association"></a>Remover a associação de Servidor de Arquivamento

Para remover um Servidor de Arquivamento, você precisa alterar ou limpar a dependência no pool de Front-End associado, Servidor Front-End, Aparelho de Filial E Servidor de Filial Suportável. Edite as propriedades do pool front-end, servidor front-end, aparelho de filial e servidor de filial que sobrevive para remover a dependência. Depois de limpar a dependência e excluir o servidor no Construtor de Topologias, você será notificado de que o objeto de armazenamento de banco de dados associado no Construtor de Topologias também será excluído.
  
### <a name="to-remove-the-archiving-server-association"></a>Para remover a associação de Servidor de Arquivamento

1. No servidor front-end Skype for Business Server 2019, abra o Construtor de Topologias.
    
2. Navegue até o nó de instalação herddo.
    
3. No Construtor de Topologias, expanda Edição Enterprise pools de **front-end,** Edição Standard **servidores front-end** ou sites de **filial,** dependendo de onde o Servidor de Arquivamento é definido.
    
4. Se você tiver o Servidor de Filial Suportável associado, expanda **sites** de filial, expanda o nome do site de filial e expanda **Aparelhos de** FilialVivíveis .
    
    > [!NOTE]
    > **Aparelhos de FilialVivíveis** na interface do usuário se aplica ao Servidor de Filial E Aparelho de Filial Desavivável. 
  
5. Clique com o botão direito do mouse no pool, servidor ou dispositivo associado ao Servidor de Arquivamento e clique em **Editar Propriedades**.
    
6. Em **Editar Propriedades,** em   >  **Associações Gerais, desempure** a caixa de seleção **Associar** Servidor de Arquivamento e clique em **OK**.
    
7. Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao Servidor de Arquivamento que você deseja remover.
    
8. Clique com o botão direito do mouse no Servidor de Arquivamento e clique em **Excluir**.
    
9. Em **Excluir Repositórios Dependentes**, clique em **OK**.
    
10. Publique a topologia, verifique o status da replicação e execute o Assistente Skype for Business Server implantação, conforme necessário. 
    

