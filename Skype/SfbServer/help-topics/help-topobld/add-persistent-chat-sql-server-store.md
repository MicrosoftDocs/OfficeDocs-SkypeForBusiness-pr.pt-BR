---
title: Adicionar Repositório de Servidor SQL de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Você configura as lojas do SQL Server que fornecerão bancos de dados para o servidor de chat persistente ou o pool de servidor de chat persistente.
ms.openlocfilehash: 794ad4a1b5427fab7a8409fbbbd76448c33e918e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685054"
---
# <a name="add-persistent-chat-sql-server-store"></a>Adicionar Repositório de Servidor SQL de Chat Persistente
 
Você configura as lojas do SQL Server que fornecerão bancos de dados para o servidor de chat persistente ou o pool de servidor de chat persistente.
  
 **Repositório do SQL Server**: selecione um SQL Server existente e, opcionalmente, uma instância para o chat persistente.
  
Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de chat persistente.
  
Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de chat persistente.
  
Selecione na lista **espelhamento do SQL Server Store** uma instância do SQL Server e opcional para atuar como o espelho do SQL Server do SQL Server de chat persistente.
  
Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento de chat persistente do SQL Server.
  
Na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático**, selecione um SQL Server que atuará como o servidor testemunha em cenários de failover. O servidor testemunha não espelha ou hospeda dados para os servidores de chat persistentes, mas garante que apenas um SQL Server em uma configuração espelhada seja o SQL Server ativo a qualquer momento.
  
Clique em **novo** para definir um novo SQL Server testemunha opcionalmente uma instância para a testemunha de espelhamento do chat do SQL Server persistente.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique em **Avançar** depois de terminar de inserir as opções para a configuração do repositório do SQL Server deste pool e para continuar com a definição do pool do servidor de chat persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda contextual, como esta página.
  
## <a name="see-also"></a>Confira também

[Planejar Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Noções básicas de topologia para o Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
