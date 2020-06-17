---
title: Conectar pool piloto aos Servidores de Borda herdados
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
description: Após implantar o Skype for Business Server 2019, você precisará configurar uma rota de Federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753921"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conectar pool piloto aos Servidores de Borda herdados

Após implantar o Skype for Business Server 2019, você precisará configurar uma rota de Federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota. 
  
Para habilitar o site do Skype for Business Server 2019 para usar o diretor e o servidor de borda da implantação herdada, use o construtor de topologia para associar o pool de borda herdado.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para associar o pool de Borda herdado usando o Construtor de Topologia

1. Abra o Construtor de Topologia. 
    
2. Selecione seu site, que está diretamente abaixo do nó do **Skype for Business Server** . 
    
3. No menu **Ações**, clique em **Editar Propriedades**.
    
4. No painel esquerdo, selecione **Rota de federação**.
    
5. Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor herdado ou o servidor de borda herdado se nenhum diretor estiver listado.
  
6. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
7. No construtor de topologias, sob o nó do Skype for Business Server 2019, navegue até o **servidor Standard Edition** ou **pools de front-ends Enterprise Edition**, clique com o botão direito do mouse no pool e clique em **Editar propriedades**.
    
8. Em **Associações**, marque a caixa de seleção próxima ao **Associar pool de Borda (para componentes de mídia)**. 
    
9. Na lista, selecione o Servidor de Borda herdado. 
  
10. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
11. No **Construtor de topologias**, selecione o nó superior, **Skype for Business Server**.
    
12. No painel **Ações**, no menu **Publicar topologia** e em **Avançar**.
    
13. Quando o **Assistente de publicação** for concluído, clique em **Finalizar**.
    

