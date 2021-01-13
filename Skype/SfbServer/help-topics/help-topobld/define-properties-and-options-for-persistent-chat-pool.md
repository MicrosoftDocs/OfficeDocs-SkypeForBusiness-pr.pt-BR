---
title: Definir Propriedades e Opções para Pool de Bate-papo Persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Configure as opções para seu Servidor de Chat Persistente ou pool de Servidor de Chat Persistente definindo as seguintes propriedades:'
ms.openlocfilehash: acc80c76e79364be730ec56a2b64e5dcd001f661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818421"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definir Propriedades e Opções para Pool de Chat Persistente
 
Configure as opções para seu Servidor de Chat Persistente ou pool de Servidor de Chat Persistente definindo as seguintes propriedades:
  
 **Nome de exibição** do pool de Chat Persistente: uma propriedade necessária que define um nome amigável que será exibido para este Servidor de Chat Persistente ou pool de Servidor de Chat Persistente.
  
 **Porta de Chat** Persistente : uma propriedade necessária que definirá o número da porta que este Servidor de Chat Persistente ou pool de Servidor de Chat Persistente escutará.
  
 **Habilitar conformidade:** marque a caixa de seleção se você planeja implantar e implementar o recurso e o banco de dados de conformidade opcional de Chat Persistente.
  
 **Use os armazenamentos** de backup do SQL Server para habilitar a recuperação de desastre: marque essa caixa de seleção se planeja implantar e implementar a recuperação de desastre dos armazenamentos do SQL Server de Chat Persistente de um conjunto de backup configurado de armazenamentos em outro SQL Server. Para obter detalhes, [consulte Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
  
> [!NOTE]
> Essa opção está disponível somente para pools com múltiplos servidores. 
  
 **Use este pool como \<site that this server or pool is being configured in\> padrão para** o site: marque essa caixa de seleção se for o Servidor de Chat Persistente ou o pool de Servidor de Chat Persistente padrão para o site. Você deve ter um servidor de Chat Persistente padrão ou pol por site.
  
> [!NOTE]
> Se sua topologia incluir múltiplos sites, uma caixa de seleção para **Usar este pool como padrão para todos os sites** também será exibida.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique **em Avançar** depois de terminar de inserir as opções desse pool para prosseguir com a definição do pool do Servidor de Chat Persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Plano para Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar Servidor de Chat Persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
