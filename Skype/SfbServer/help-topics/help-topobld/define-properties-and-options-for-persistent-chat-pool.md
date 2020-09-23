---
title: Definir Propriedades e Opções para Pool de Bate-papo Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Configure as opções para seu servidor de chat persistente ou pool de servidor de chat persistente, definindo as seguintes propriedades:'
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218542"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definir Propriedades e Opções para Pool de Bate-papo Persistente
 
Configure as opções para seu servidor de chat persistente ou pool de servidor de chat persistente, definindo as seguintes propriedades:
  
 **Nome para exibição do pool de chat persistente**: uma propriedade necessária que define um nome de usuário amigável que será exibido para este servidor de chat persistente ou pool de servidor de chat persistente.
  
 **Porta de chat persistente**: uma propriedade necessária que definirá o número de porta que este servidor de chat persistente ou pool de servidor de chat persistente escutará.
  
 **Habilitar conformidade**: marque a caixa de seleção se você planeja implantar e implementar o recurso de conformidade de chat persistente opcional e o banco de dados.
  
 **Usar repositórios de backup do SQL Server para habilitar a recuperação de desastres**: Marque essa caixa de seleção se você planeja implantar e implementar a recuperação de desastres dos repositórios do SQL Server do chat persistente de um conjunto de backup configurado de repositórios em outro SQL Server. Para obter detalhes, consulte [Configure High Availability and Disaster Recovery for persistent chat Server in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Essa opção está disponível somente para pools com múltiplos servidores. 
  
 **Use este pool como padrão para o site \<site that this server or pool is being configured in\> **: Marque essa caixa de seleção se este for o servidor de chat persistente padrão ou o pool do servidor de chat persistente para o site. Você deve ter um servidor de chat persistente padrão ou um pol por site.
  
> [!NOTE]
> Se sua topologia incluir múltiplos sites, uma caixa de seleção para **Usar este pool como padrão para todos os sites** também será exibida.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique em **Avançar** depois de inserir as opções desse pool para prosseguir com a definição do pool do servidor de chat persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Planejar o servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar servidor de chat persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
