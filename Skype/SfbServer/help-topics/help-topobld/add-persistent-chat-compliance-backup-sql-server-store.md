---
title: Adicionar Repositório de Servidor SQL de Backup de Conformidade de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Você configura as lojas de conformidade de backup do SQL Server que fornecerão bancos de dados de backup para o servidor de chat persistente ou para as lojas do SQL Server persistentes da conformidade do servidor de chat persistente.
ms.openlocfilehash: 457874f87266453939c75cdef50d30231d8610bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277703"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Adicionar Repositório de Servidor SQL de Backup de Conformidade de Chat Persistente
 
Você configura as lojas de conformidade de backup do SQL Server que fornecerão bancos de dados de backup para o servidor de chat persistente ou para as lojas do SQL Server persistentes da conformidade do servidor de chat persistente.
  
 **Repositório do SQL Server**: selecione um SQL Server existente e, opcionalmente, uma instância para o chat persistente.
  
Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de conformidade de backup de chat persistente.
  
Marque a caixa de seleção Habilitar o espelhamento da **loja do SQL Server** para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de conformidade de backup de chat persistente.
  
Selecione na lista **espelhar SQL Server Store** uma instância do SQL Server e opcional para atuar como o espelho do SQL Server do SQL Server de conformidade de backup de chat persistente.
  
Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento de chat persistente do SQL Server.
  
Na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático**, selecione um SQL Server que atuará como o servidor testemunha em cenários de failover. O servidor testemunha não espelha ou hospeda dados para os servidores de chat persistentes, mas garante que apenas um SQL Server em uma configuração espelhada seja o SQL Server ativo a qualquer momento.
  
Clique em **novo** para definir um novo SQL Server testemunha opcionalmente uma instância para a testemunha de espelhamento do SQL Server de conformidade de backup de chat persistente.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique em **Avançar** depois de terminar de inserir as opções para a configuração do SQL Server Store de backup do pool e para continuar com a definição do pool de servidores de chat persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda contextual, como esta página.
  
## <a name="see-also"></a>Confira também

[Planejar Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar o serviço de Conformidade para o Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
