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
description: Para remover o Monitoring Server, você precisa alterar ou limpar a dependência do pool de front-ends associado, servidor front-end, aparelho de filial persistente e servidor de filial persistente. Edite as propriedades do pool de front-ends, servidor front-end, aparelho de filial persistente e servidor de filial persistente para remover a dependência. Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto repositório de banco de dados associado no construtor de topologias também será excluído.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753413"
---
# <a name="remove-the-monitoring-server-association"></a>Remover a associação do Servidor de Monitoramento

Para remover o Monitoring Server, você precisa alterar ou limpar a dependência no pool de front-ends associado, servidor front-end, aparelho de filial persistente e servidor de filial persistente. Edite as propriedades do pool de front-ends, servidor front-end, aparelho de filial persistente e servidor de filial persistente para remover a dependência. Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto repositório de banco de dados associado no construtor de topologias também será excluído.
  
### <a name="to-remove-the-monitoring-server-association"></a>Para remover a associação do Servidor de Monitoramento

1. No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.
    
2. Navegue até o nó instalações herdadas.
    
3. No construtor de topologias, expanda **pools de front-ends Enterprise Edition**, **servidores front-end Standard Edition**ou **sites de filiais**, dependendo de onde o servidor de monitoramento está definido.
    
4. Se você tiver um servidor de filial persistente associado, expanda **sites de filial**, expanda o nome do site de filial e expanda **aparelhos de filial persistente**.
    
    > [!NOTE]
    > **Aparelhos de filial persistentes** na interface do usuário aplicam-se ao servidor de filial persistente e ao aparelho de filial persistente. 
  
5. Clique com o botão direito do mouse no pool, servidor ou dispositivo associado ao servidor de monitoramento e clique em **Editar propriedades**.
    
6. Em **Editar propriedades**, em **General**  >  **associações**gerais, desmarque a caixa de seleção **associar servidor de monitoramento** e clique em **OK**.
    
7. Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao servidor de monitoramento.
    
8. Clique com o botão direito do mouse no servidor de monitoramento e clique em **excluir**. 
    
9. Em **Excluir Repositórios Dependentes**, clique em **OK**.
    
10. Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Skype for Business Server, conforme necessário. 
    

