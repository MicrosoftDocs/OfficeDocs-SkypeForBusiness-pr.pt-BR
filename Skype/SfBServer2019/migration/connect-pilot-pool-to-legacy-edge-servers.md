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
ms.localizationpriority: medium
description: Depois de implantar Skype for Business Server 2019, você precisa configurar uma rota de federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota.
ms.openlocfilehash: a5f5da34300d993f59d4de5e2eb0b47cc58eff0e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607458"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conectar pool piloto aos Servidores de Borda herdados

Depois de implantar Skype for Business Server 2019, você precisa configurar uma rota de federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota. 
  
Para habilitar o site Skype for Business Server 2019 para usar o Diretor e o Servidor de Borda da implantação herdado, use o Construtor de Topologias para associar o pool de Borda herdado.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para associar o pool de Borda herdado usando o Construtor de Topologia

1. Abra o Construtor de Topologia. 
    
2. Selecione seu site, que está diretamente abaixo do **nó Skype for Business Server** usuário. 
    
3. No menu **Ações**, clique em **Editar Propriedades**.
    
4. No painel esquerdo, selecione **Rota de federação**.
    
5. Em **Atribuição de** rota de federação de site, selecione Habilitar federação **SIP** e selecione o Diretor herdado ou o Servidor de Borda herdado se nenhum Diretor estiver listado.
  
6. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
7. No Construtor de Topologias, no nó Skype for Business Server 2019, navegue até o servidor **Edição Standard** ou **pools de front-end** do Edição Enterprise , clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.
    
8. Em **Associações**, marque a caixa de seleção próxima ao **Associar pool de Borda (para componentes de mídia)**. 
    
9. Na lista, selecione o Servidor de Borda herdado. 
  
10. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
11. No **Construtor de Topologias,** selecione o nó mais alto, **Skype for Business Server**.
    
12. No painel **Ações**, no menu **Publicar topologia** e em **Avançar**.
    
13. Quando o **Assistente de publicação** for concluído, clique em **Finalizar**.
    

