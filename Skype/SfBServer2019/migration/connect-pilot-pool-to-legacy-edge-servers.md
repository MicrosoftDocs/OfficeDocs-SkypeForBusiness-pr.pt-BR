---
title: Conectar pool piloto aos Servidores de Borda herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após a implantação do Skype para Business Server 2019, você precisará configurar uma rota de federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, Skype para Business Server 2019 deve ser configurado para usar essa rota.
ms.openlocfilehash: 5a3498041b4af762d184cd56e3883a90612b13e0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238665"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conectar pool piloto aos Servidores de Borda herdados

Após a implantação do Skype para Business Server 2019, você precisará configurar uma rota de federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, Skype para Business Server 2019 deve ser configurado para usar essa rota. 
  
Para habilitar o Skype para Business Server 2019 site usar o diretor e servidor de borda da implantação herdada, use o construtor de topologias para associar o pool de borda herdado.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para associar o pool de borda herdado usando o construtor de topologia

1. Abra o construtor de topologia. 
    
2. Marque seu site, que é diretamente abaixo do nó do **Skype para Business Server** . 
    
3. No menu **ações** , clique em **Editar propriedades**.
    
4. No painel esquerdo, selecione **rota de Federação**.
    
5. Em **atribuição de rota de Federação do Site**, selecione **Habilitar federação SIP**e selecione o Diretor herdado ou servidor de borda herdado se nenhum diretor esteja listado.
  
6. Clique em **Okey** para fechar a página **Editar propriedades** . 
    
7. No construtor de topologias, sob o Skype para Business Server 2019 nó, navegue até o **servidor Standard Edition** ou **pools de Front End do Enterprise Edition**, com o botão direito do pool e, em seguida, clique em **Editar propriedades**.
    
8. Em **associações**, marque a caixa de seleção ao lado de **associar pool de borda (para componentes de mídia)**. 
    
9. Na lista, selecione o servidor de borda herdado. 
  
10. Clique em **Okey** para fechar a página **Editar propriedades** . 
    
11. No **Construtor de topologias**, selecione o nó superior, **Skype para Business Server**.
    
12. No menu **ação** , clique em **Publicar topologia**e clique em **Avançar**.
    
13. Quando o **Assistente para publicação** for concluído, clique em **Concluir**.
    

