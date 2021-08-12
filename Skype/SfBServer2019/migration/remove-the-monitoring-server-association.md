---
title: Remover a associação do Servidor de Monitoramento
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
description: Para remover o Servidor de Monitoramento, você precisa alterar ou limpar a dependência no pool de Front-End associado, Servidor Front-End, Aparelho de Filial E Servidor de Filial Desavivável. Edite as propriedades do pool front-end, servidor front-end, aparelho de filial e servidor de filial que sobrevive para remover a dependência. Depois de limpar a dependência e excluir o servidor no Construtor de Topologias, você será notificado de que o objeto de armazenamento de banco de dados associado no Construtor de Topologias também será excluído.
ms.openlocfilehash: 8e4c4b08c6126f6ac2c03d66e9ddcfe921b79850e704c54c65d6951c1449aa9f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280396"
---
# <a name="remove-the-monitoring-server-association"></a>Remover a associação do Servidor de Monitoramento

Para remover o Servidor de Monitoramento, você precisa alterar ou limpar a dependência no pool de Front-End associado, Servidor Front-End, Aparelho de Filial Desavivável e Servidor de Filial Desavivável. Edite as propriedades do pool front-end, servidor front-end, aparelho de filial e servidor de filial que sobrevive para remover a dependência. Depois de limpar a dependência e excluir o servidor no Construtor de Topologias, você será notificado de que o objeto de armazenamento de banco de dados associado no Construtor de Topologias também será excluído.
  
### <a name="to-remove-the-monitoring-server-association"></a>Para remover a associação do Servidor de Monitoramento

1. No servidor front-end Skype for Business Server 2019, abra o Construtor de Topologias.
    
2. Navegue até o nó de instalação herdou.
    
3. No Construtor de Topologias, expanda Edição Enterprise pools de **front-end,** Edição Standard **servidores front-end** ou sites de **filial,** dependendo de onde o Servidor de Monitoramento é definido.
    
4. Se você tiver o Servidor de Filial Suportável associado, expanda **sites** de filial, expanda o nome do site de filial e expanda **Aparelhos de** FilialVivíveis .
    
    > [!NOTE]
    > **Aparelhos de FilialVivíveis** na interface do usuário se aplica ao Servidor de Filial E Aparelho de Filial Desavivável. 
  
5. Clique com o botão direito do mouse no pool, servidor ou dispositivo associado ao Servidor de Monitoramento e clique em **Editar Propriedades.**
    
6. Em **Editar Propriedades,** em   >  **Associações Gerais, desempure** a caixa de seleção **Associar Servidor** de Monitoramento e clique em **OK**.
    
7. Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao Servidor de Monitoramento.
    
8. Clique com o botão direito do mouse no Servidor de Monitoramento e clique em **Excluir**. 
    
9. Em **Excluir Repositórios Dependentes**, clique em **OK**.
    
10. Publique a topologia, verifique o status da replicação e execute o Assistente Skype for Business Server implantação conforme necessário. 
    

