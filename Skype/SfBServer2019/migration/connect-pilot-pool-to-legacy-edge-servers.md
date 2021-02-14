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
description: Depois de implantar o Skype for Business Server 2019, você precisará configurar uma rota de federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753921"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conectar pool piloto aos Servidores de Borda herdados

Depois de implantar o Skype for Business Server 2019, você precisará configurar uma rota de federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota. 
  
Para habilitar o site do Skype for Business Server 2019 a usar o Diretor e o Servidor de Borda da implantação herdada, use o Construtor de Topologias para associar o pool de Borda herdado.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para associar o pool de Borda herdado usando o Construtor de Topologia

1. Abra o Construtor de Topologia. 
    
2. Selecione seu site, que está diretamente abaixo do **nó do Skype for Business Server.** 
    
3. No menu **Ações**, clique em **Editar Propriedades**.
    
4. No painel esquerdo, selecione **Rota de federação**.
    
5. Em **Atribuição da** rota de federação do site, selecione Habilitar federação **SIP** e selecione o Diretor herdado ou o Servidor de Borda herdado se nenhum Diretor estiver listado.
  
6. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
7. No Construtor de Topologias, no nó Skype for Business Server 2019, navegue até o servidor **Standard Edition** ou pools de **front-end enterprise edition**, clique com o botão direito do mouse no pool e clique em **Editar** propriedades .
    
8. Em **Associações**, marque a caixa de seleção próxima ao **Associar pool de Borda (para componentes de mídia)**. 
    
9. Na lista, selecione o Servidor de Borda herdado. 
  
10. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
11. No **Construtor de Topologias,** selecione o nó superior, **Skype for Business Server**.
    
12. No painel **Ações**, no menu **Publicar topologia** e em **Avançar**.
    
13. Quando o **Assistente de publicação** for concluído, clique em **Finalizar**.
    

