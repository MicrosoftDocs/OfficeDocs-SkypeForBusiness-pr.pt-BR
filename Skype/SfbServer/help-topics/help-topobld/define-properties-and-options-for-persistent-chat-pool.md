---
title: Definir Propriedades e Opções para Pool de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Você configura as opções do seu servidor de chat persistente ou pool de servidores de chat persistente definindo as seguintes propriedades:'
ms.openlocfilehash: 458e50ecc3ddd389a8e413e8f2dd368fc0f15369
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697546"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definir Propriedades e Opções para Pool de Chat Persistente
 
Você configura as opções do seu servidor de chat persistente ou pool de servidores de chat persistente definindo as seguintes propriedades:
  
 **Exibir o nome do pool de chat persistente**: uma propriedade necessária que define um nome de usuário amigável que será exibido para este servidor de chat persistente ou pool de servidores de chat persistente.
  
 **Porta de chat persistente**: uma propriedade necessária que definirá o número da porta que esse servidor de chat persistente ou o pool de servidores de chat persistente escutará.
  
 **Habilitar a conformidade**: marque a caixa de seleção se você planeja implantar e implementar o recurso de conformidade de chat persistente opcional e o banco de dados.
  
 **Use as lojas de backup do SQL Server para habilitar a recuperação de desastres**: Marque esta caixa de seleção se você planeja implantar e implementar a recuperação de desastres dos repositórios persistentes do SQL Server de um conjunto de backup configurado de armazenamentos em outro SQL Server. Para obter detalhes, consulte [Configurar alta disponibilidade e recuperação de desastre para servidor de chat persistente no Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Essa opção está disponível somente para pools com vários servidores. 
  
 **Use este pool como padrão para o site \<do site em\>que esse servidor ou pool está sendo configurado**: Marque esta caixa de seleção se este for o servidor de chat persistente ou o pool de servidores de chat persistentes padrão do site. Você deve ter um servidor de chat persistente ou uma pol padrão por site.
  
> [!NOTE]
> Se sua topologia incluir vários sites, uma caixa de seleção para **Usar este pool como o padrão para todos os sites** também será exibida.
  
Clique em  **Voltar** para voltar à caixa de diálogo de definição de pool anterior.
  
Clique em **Avançar** após terminar de inserir as opções desse pool para continuar com a definição do pool de servidores de chat persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda contextual, como esta página.
  
## <a name="see-also"></a>Confira também

[Planejar Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
