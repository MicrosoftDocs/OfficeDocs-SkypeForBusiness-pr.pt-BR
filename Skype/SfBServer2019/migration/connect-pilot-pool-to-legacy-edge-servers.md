---
title: Conectar pool piloto aos Servidores de Borda herdados
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
description: Depois de implantar o Skype for Business Server 2019, você precisa configurar uma rota de Federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota.
ms.openlocfilehash: 6cc49da3cb27679ef295c7bbeca122aea5a89d10
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813699"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conectar pool piloto aos Servidores de Borda herdados

Depois de implantar o Skype for Business Server 2019, você precisa configurar uma rota de Federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota. 
  
Para habilitar o site do Skype for Business Server 2019 para usar o diretor e o servidor de borda da implantação herdada, use o construtor de topologias para associar o pool de bordas herdado.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para associar o pool de bordas herdado usando o construtor de topologias

1. Abrir o construtor de topologias. 
    
2. Selecione seu site, que está diretamente abaixo do nó do **Skype for Business Server** . 
    
3. No menu **ações** , clique em **Editar propriedades**.
    
4. No painel esquerdo, selecione **roteiro de Federação**.
    
5. Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor herdado ou o servidor de borda herdado, se nenhum diretor estiver listado.
  
6. Clique em **OK** para fechar a página **Editar propriedades** . 
    
7. No construtor de topologias, no nó Skype for Business Server 2019, navegue até o **servidor Standard Edition** ou **pools front-end do Enterprise Edition**, clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.
    
8. Em **associações**, marque a caixa de seleção ao lado de **associar o pool de bordas (para componentes de mídia)**. 
    
9. Na lista, selecione o servidor de borda herdado. 
  
10. Clique em **OK** para fechar a página **Editar propriedades** . 
    
11. No **Construtor de topologias**, selecione o nó mais superior, **Skype for Business Server**.
    
12. No menu **ação** , clique em **publicar topologia**e, em seguida, clique em **Avançar**.
    
13. Quando o **Assistente de publicação** for concluído, clique em **concluir**.
    

