---
title: Definir Propriedades e Opções para Pool de Chat Persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Você pode configurar opções para o servidor de Chat persistente ou o pool de servidor de Chat persistente definindo as seguintes propriedades:'
ms.openlocfilehash: f1276fa72f9a6c41ac4d5ec8e2a91232561eb79d
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2018
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definir Propriedades e Opções para Pool de Chat Persistente
 
Você pode configurar opções para o servidor de Chat persistente ou o pool de servidor de Chat persistente definindo as seguintes propriedades:
  
 **Nome para exibição do pool de Chat persistente**: uma propriedade necessária que define um nome amigável para o usuário que será exibido para esse servidor de Chat persistente ou o pool do servidor de Chat persistente.
  
 **Porta de Chat persistente**: uma propriedade necessária que definirá a porta de número em que este servidor de Chat persistente ou servidor de Chat persistente pool escutará.
  
 **Habilitar a conformidade**: marque a caixa de seleção se você planeja implantar e implementar o recurso de conformidade de Chat persistente opcional e um banco de dados.
  
 **Use o backup SQL Server armazena para habilitar a recuperação de desastres**: marque essa caixa de seleção se você planeja implantar e implementar a recuperação de desastre do SQL Server de Chat persistente armazena a partir de um conjunto de backup configurado dos repositórios em outro SQL Server. Para obter detalhes, consulte [Configure alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Essa opção está disponível somente para pools com vários servidores. 
  
 **Usar este pool como padrão para o site \<sites nesse servidor ou pool que está sendo configurado no\>**: marque essa caixa de seleção se esse será o padrão de servidor de Chat persistente ou o pool de servidor de Chat persistente para o site. Você deve ter um servidor de Chat persistente padrão ou pol por site.
  
> [!NOTE]
> Se sua topologia incluir vários sites, uma caixa de seleção para **Usar este pool como o padrão para todos os sites** também será exibida.
  
Clique em  **Voltar** para voltar à caixa de diálogo de definição de pool anterior.
  
Clique em **Avançar** depois de concluir a inserção das opções para essa pool a fim de continuar com a definição do pool de servidor de Chat persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda contextual, como esta página.
  
## <a name="see-also"></a>Consulte também

#### 

[Planejar o servidor de Chat persistente no Skype for Business Server 2015](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015](../../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

