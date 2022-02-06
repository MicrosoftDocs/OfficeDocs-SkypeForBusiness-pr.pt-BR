---
title: Definir Propriedades e Opções para Pool de Bate-papo Persistente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Você configura opções para seu Servidor de Chat Persistente ou pool de Servidor de Chat Persistente definindo as seguintes propriedades:'
---

# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definir Propriedades e Opções para Pool de Chat Persistente
 
Você configura opções para seu Servidor de Chat Persistente ou pool de Servidor de Chat Persistente definindo as seguintes propriedades:
  
 **Nome de exibição do pool de Chat** Persistente: uma propriedade necessária que define um nome amigável que será exibido para esse Servidor de Chat Persistente ou pool de Servidor de Chat Persistente.
  
 **Porta de Chat Persistente**: uma propriedade necessária que definirá o número de porta que esse Servidor de Chat Persistente ou Pool de Servidor de Chat Persistente escutará.
  
 **Habilitar** a conformidade: marque a caixa de seleção se você planeja implantar e implementar o recurso opcional de conformidade do Chat Persistente e o banco de dados.
  
 Use **os SQL Server** de backup para habilitar a recuperação de desastres: marque essa caixa de seleção se você planeja implantar e implementar a recuperação de desastres dos armazenamentos de chat persistente SQL Server de um conjunto de backup configurado de armazenamentos em outro SQL Server. Para obter detalhes, consulte [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Essa opção está disponível somente para pools com múltiplos servidores. 
  
 **Use esse pool como padrão para o site \<site that this server or pool is being configured in\>**: Marque essa caixa de seleção se esse será o servidor de chat persistente padrão ou o pool de Servidor de Chat Persistente para o site. Você deve ter um servidor de Chat Persistente padrão ou pol por site.
  
> [!NOTE]
> Se sua topologia incluir múltiplos sites, uma caixa de seleção para **Usar este pool como padrão para todos os sites** também será exibida.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique **em Avançar** depois de terminar de inserir as opções desse pool para prosseguir com a definição do pool do Servidor de Chat Persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Planejar o Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar Servidor de Chat Persistente à topologia Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
