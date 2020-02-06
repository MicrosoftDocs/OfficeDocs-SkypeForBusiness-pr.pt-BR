---
title: Remover a associação do Servidor de Monitoramento
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
description: Para remover o Monitoring Server, você precisa alterar ou limpar a dependência do pool de front-ends associado, servidor front-end, aparelho para ramificação sobreviventes e servidor de ramificação sobreviventes. Edite as propriedades do pool de front-end, servidor front-end, appliances para ramificação sobreviventes e servidor de ramificação sobreviventes para remover a dependência. Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto de repositório de banco de dados associado também será excluído.
ms.openlocfilehash: aed16d60fbdae2413cb7890e38895bf6930cd4fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812859"
---
# <a name="remove-the-monitoring-server-association"></a>Remover a associação do Servidor de Monitoramento

Para remover o Monitoring Server, você precisa alterar ou limpar a dependência do pool de front-ends associado, servidor front-end, aparelho para ramificação sobreviventes e servidor de ramificação sobreviventes. Edite as propriedades do pool de front-end, do servidor front-end, do Appliance para ramificação sobreviventes e do servidor de ramificação sobreviventes para remover a dependência. Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto de repositório de banco de dados associado também será excluído.
  
### <a name="to-remove-the-monitoring-server-association"></a>Para remover a associação do Monitoring Server

1. No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.
    
2. Navegue até o nó instalações herdadas.
    
3. No construtor de topologia, expanda **pools de front-end do Enterprise Edition**, **servidores front-end da edição padrão**ou **sites de filiais**, dependendo de onde o servidor de monitoração está definido.
    
4. Se você tiver um servidor de ramificação sobreviventes associado, expanda **sites de ramificação**, expanda o nome do site da filial e expanda **aparelhos de ramificação sobreviventes**.
    
    > [!NOTE]
    > **Aparelhos de ramificação sobreviventes** na interface do usuário se aplicam ao servidor de ramificação sobreviventes e ao aparelho de ramificação sobreviventes. 
  
5. Clique com o botão direito do mouse no pool, no servidor ou no dispositivo associado ao Monitoring Server e clique em **Editar propriedades**.
    
6. Em **Editar propriedades**, em **** > **associações**gerais, desmarque a caixa de seleção **associar o servidor de monitoramento** e clique em **OK**.
    
7. Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao servidor de monitoramento.
    
8. Clique com o botão direito do mouse no servidor de monitoramento e clique em **excluir**. 
    
9. Em **excluir repositórios dependentes**, clique em **OK**.
    
10. Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Skype for Business Server conforme necessário. 
    

