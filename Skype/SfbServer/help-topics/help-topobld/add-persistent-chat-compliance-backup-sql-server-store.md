---
title: Adicionar Repositório de Servidor SQL de Backup de Conformidade de Bate-papo Persistente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Você configura os armazenamentos de conformidade de backup SQL Server que fornecerão bancos de dados de backup para o Servidor de Chat Persistente ou os SQL Server de conformidade do Servidor de Chat Persistente.
ms.openlocfilehash: 8d70a8f82c58d0a66fef00695b3677305e5e6a9e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747857"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Adicionar Conformidade de Backup do Chat Persistente do Repositório do SQL Server
 
Você configura os armazenamentos de conformidade de backup SQL Server que fornecerão bancos de dados de backup para o Servidor de Chat Persistente ou os SQL Server de conformidade do Servidor de Chat Persistente.
  
 **SQL Server:** selecione um SQL Server existente e, opcionalmente, uma instância para Chat Persistente.
  
Clique **em Novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de conformidade de backup de Chat Persistente.
  
Marque a caixa de seleção Habilitar **SQL Server** de espelhamento de armazenamento para configurar um banco de dados SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de conformidade de backup de Chat Persistente.
  
Selecione na lista **Espelhamento** SQL Server armazenar uma instância SQL Server e opcional para atuar como o espelho SQL Server para o aplicativo de conformidade de backup de Chat Persistente SQL Server.
  
Clique **em Novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o SQL Server de Chat Persistente.
  
Selecione na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** um SQL Server que agirá como o servidor testemunha em cenários de failover. O servidor testemunha não espelha nem hospeda dados para os servidores de Chat Persistente, mas garante que apenas um SQL Server em uma configuração espelhada seja o servidor SQL Server a qualquer momento.
  
Clique **em Novo** para definir uma nova testemunha SQL Server, opcionalmente, uma instância para a testemunha de conformidade de backup de Chat Persistente SQL Server espelhamento.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique **em Avançar** depois de inserir as opções para a configuração de armazenamento de backup SQL Server do pool e continuar com a definição do pool do Servidor de Chat Persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Planejar o Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisitos de servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware e software para o Servidor de Chat Persistente Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar o serviço de Conformidade para o Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurar alta disponibilidade e recuperação de desastres para o Servidor de Chat Persistente Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
