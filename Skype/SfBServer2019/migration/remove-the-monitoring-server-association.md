---
title: Remover a associação do Servidor de Monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para remover o Monitoring Server, você precisará alterar ou desmarque a dependência no pool de Front-End associado, servidor Front-End, o aparelho de filial e o servidor de filial persistente. Você editar as propriedades do pool de Front-End, servidor Front-End, servidor de filial persistente e aparelho de filial persistente para remover a dependência. Depois que você desmarcar a dependência e excluir o servidor no construtor de topologia, você será notificado de que o objeto de armazenamento de banco de dados associado no construtor de topologia também será excluído.
ms.openlocfilehash: 854e95969d08d14d626bb374073091ae4ae39630
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892699"
---
# <a name="remove-the-monitoring-server-association"></a>Remover a associação do Servidor de Monitoramento

Para remover o Monitoring Server, você precisará alterar ou desmarque a dependência a associado Front End pool, servidor Front-End, aparelho de filial persistente e servidor de filial persistente. Você editar as propriedades do pool Front-End, servidor Front-End, aparelho de filial persistente e servidor de filial persistente para remover a dependência. Depois que você desmarcar a dependência e excluir o servidor no construtor de topologia, você será notificado de que o objeto de armazenamento de banco de dados associado no construtor de topologia também será excluído.
  
### <a name="to-remove-the-monitoring-server-association"></a>Para remover a associação do Monitoring Server

1. No Skype para Business Server 2019 servidor Front-End, abra o construtor de topologias.
    
2. Navegue até o nó de instalações herdadas.
    
3. No construtor de topologia, expanda **pools de Front End do Enterprise Edition**, **Servidores Standard Edition Front End**ou **sites de filiais**, dependendo de onde o Monitoring Server está definido.
    
4. Se você tiver um servidor de filial persistente associado, expanda **sites de filiais**, expanda o nome do site de filial e expanda **Aparelhos de filial persistente**.
    
    > [!NOTE]
    > **Aparelhos de filial persistente** na interface do usuário aplica-se ao servidor de filial persistente e aparelho de filial persistente. 
  
5. Com o botão direito do pool, servidor ou dispositivo que está associado com o Monitoring Server e, em seguida, clique em **Editar propriedades**.
    
6. Em **Editar propriedades**, em **Geral** > **associações**, desmarque a caixa de seleção **Associar Monitoring Server** e clique em **Okey**.
    
7. Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao Monitoring Server.
    
8. Com o botão direito no Monitoring Server e, em seguida, clique em **Excluir**. 
    
9. Em **Excluir armazenamentos dependentes**, clique em **Okey**.
    
10. Publique a topologia, verifique o status de replicação e execute o Skype para o Assistente de implantação de servidor de negócios, conforme necessário. 
    

